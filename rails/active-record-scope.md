# Active Record `scope`

- define and chain reusable queries with `scope` class method
- pass it a name as a symbol
- include a query criterion (`where`, `limit`, `order` etc)
- invoke scopes as you would class methods
- can be chained together to create complex queries
- append `.to_sql` when calling a scope to debug the whole query in SQL

```
class User < ActiveRecord::Base
  scope :delinquent, -> { where('timesheets_updated_at < ?', 1.week.ago) }

// equivalent to:

def self.delinquent
  where('timesheets__updated_at < ?', 1.week.ago)
end

// both called like:

User.delinquent // [#<User. id: 1, timesheets_updated_at: "Date"...]
```

### add parameters to scope

- add parameters to the proc you use to define scope query:

```
class BillableWeek < ActiveRecord::Base
  scope :newer_than, ->(date) { where('start_date > ?', date) }

// call with arg:

BillableWeek.newer_than(Date.today)
```

### cross-model scopes with `joins`

- add `joins(:model_name)` to scope query
- debug the query by appending `.to_sql` after calling scope
- best practice is to use with `.merge(ModelName.scope_to_merge_name)` at the end of scope query

### `default_scope`

- applied to all instances of model on creation
- use `.unscoped` to exclude default scoped items from query
