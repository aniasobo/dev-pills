# Using `.present?`, `.exists?` and `.any?`

`.present?` is slow because it loads all of the project's tasks to check for presence.

`.any?` is slightly faster because it uses `SQL COUNT` instead of loading each task. It's not fast enough because it gets us the count, when what we want is just to check if there's at least one record of something within our scope.

`.exists?` is the best solution because it applies `LIMIT` of `1` to the `SQL COUNT` 

[SOURCE](https://www.ombulabs.com/blog/benchmark/performance/rails/present-vs-any-vs-exists.html)
