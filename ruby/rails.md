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

## Rails on Heroku 

run the rails console directly on heroku with `heroku run rails console`  

run the rails console on pry instead of irb using the `pry-rails gem`  

apply migrations to the production db: `heroku run rake db:migrate`  

retrieve the production db to use locally: `heroku db:pull postgres://username:password@localhost/dbname`  

push your local db to production (overwrites prod db): `heroku db:push`  

initialise heroku db: `heroku run rake db:schema:load`

