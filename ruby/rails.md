# Ruby on Rails setup

### Initialise a postgres Rails app with `rails new my_app_name --database=postgresql`

### View all your routes with `bin/rails routes`

## How to test in Rails

* feature testing - the whole app; the most important testing to be done in a rails app
* controller tests - send request to the controller, receive a response; good for the Rails API.

Controller, model & view - should have as little logic as possible and be v skinny; keep the logic for the /lib.

**acceptable logic to put in views:**

* `if` statements
* loops
* (ok not to unit test views as feature testing should cover the logic)