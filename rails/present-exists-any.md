# Using `.present?`, `.exists?` and `.any?`

`.present?` is slow because it loads all of the project's tasks to check for presence. It initializes ActiveRecord for each record found - so it's slow when used to look through more than one record.

An object is `present` if it’s not `blank?`. An object is `blank` if it’s `false`, empty, or a whitespace string - this might be the key reason for using it on object attributes? Therefore -> use `.present?` on object when checking for attributes to make sure they aren't empty, NOT to search through objects and relations??

`.any?` is slightly faster because it uses `SQL COUNT` instead of loading each task. It's not fast enough because it gets us the count, when what we want is just to check if there's at least one record of something within our scope.

`.exists?` is the best solution because it applies `LIMIT` of `1` to the `SQL COUNT` 

`.exists?` asserts the existence of a resource, returning `true` if the resource is found.

[SOURCE](https://www.ombulabs.com/blog/benchmark/performance/rails/present-vs-any-vs-exists.html)
