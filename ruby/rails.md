# Ruby on Rails setup

### Initialise a postgres Rails app with `rails new my_app_name --database=postgresql`

---
## The structure of a Rails app

File/Directory	| Purpose  
------ | ------  
`app/`	| Core application (app) code, including models, views, controllers, and helpers  
`app/assets`	| Applications assets such as cascading style sheets (CSS), JavaScript files, and images  
`bin/`	| Binary executable files  
`config/`	| Application configuration  
`db/`	| Database files  
`doc/`	| Documentation for the application  
`lib/`	| Library modules  
`lib/assets`	| Library assets such as cascading style sheets (CSS), JavaScript files, and images  
`log/`	| Application log files  
`public/`	| Data accessible to the public (e.g., via web browsers), such as error pages  
`bin/rails`	| A program for generating code, opening console sessions, or starting a local server  
`test/`	| Application tests  
`tmp/`	| Temporary files  
`vendor/`	| Third-party code such as plugins and gems  
`vendor/assets`	| Third-party assets such as cascading style sheets (CSS), JavaScript files, and images  
`README.md`	| A brief description of the application  
`Rakefile`	| Utility tasks available via the rake command  
`Gemfile`	| Gem requirements for this app  
`Gemfile.lock`	| A list of gems used to ensure that all copies of the app use the same gem versions  
`config.ru`	| A configuration file for Rack middleware  
`.gitignore`	| Patterns for files that should be ignored by Git  

[source](https://www.learnenough.com/ruby-on-rails-4th-edition-tutorial/beginning)

---

### View all your routes with `bin/rails routes`

**view all your available rake and rails commands with `$ rails`**  

---

## How to test in Rails

* feature testing - the whole app; the most important testing to be done in a rails app
* controller tests - send request to the controller, receive a response; good for the Rails API.

Controller, model & view - should have as little logic as possible and be v skinny; keep the logic for the /lib.

**acceptable logic to put in views:**

* `if` statements
* loops
* (ok not to unit test views as feature testing should cover the logic)

---

## Rails on Heroku 

run the rails console directly on heroku with `heroku run rails console`  

run the rails console on pry instead of irb using the `pry-rails gem`  

apply migrations to the production db: `heroku run rake db:migrate`  

retrieve the production db to use locally: `heroku db:pull postgres://username:password@localhost/dbname`  

push your local db to production (overwrites prod db): `heroku db:push`  

initialise heroku db: `heroku run rake db:schema:load`

---

* [Setting up Travis for a Rails app](https://medium.com/full-taxx/how-to-setup-travis-ci-for-a-rails-application-78a453963300)
