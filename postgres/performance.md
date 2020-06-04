# Query speed

To find out how the query is performed: `User.where(first_name: "Anna").explain` will show what sort of algo is being used and the speed of it.

## Indexing

`add_index` to column will speed up the queries performed on it. However having too many columns indexed isn't great because indexes being refreshed on the regular will be a performance debt.

Only use on queries that are performed a lot (for example, user emails)
