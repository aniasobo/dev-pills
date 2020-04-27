# Calling things on active record models

When you call something on `@thing.something`, here's the order of actions:

1. active record looks at all the methods on `thing.rb` and looks for `something`; if it doesn't find it:
2. it looks at the attributes on the `things` table; if it doesn't find it:
3. returns `method not found`
