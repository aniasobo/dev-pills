# Heroku setup and deployment

## From the command line:

to initialise your project: `git clone <app url>`  

to create a new heroku project: `heroku create`  

to deploy: `git push heroku main`  

to open your app in browser: `heroku open`  

to view logs: `heroku logs --tail`  (`ctrl + c` to stop the stream)  

check dynos: `heroku ps`  

`heroku ps:scale web=0` - scales the web process down to zero dynos  

`heroku ps:scale web=1` - scales the web process back up to a dyno  

create local db to run the app locally with `bundle exec rake db:create db:migrate`  

launch the app locally with `heroku local web` - open `localhost:5000` in browser  

list your addons with `heroku addons`  

add Papertrail add-on: `heroku addons:create papertrail`  

`heroku addons:open papertrail` displays Papertrail log messages  

run scripts and apps that are part of your project with `heroku run rails console`  

view your config file and vars with `heroku config`  

view your Postgres setup: `heroku pg`  

to connect to your PG db and execute queries: `heroku pg:psql`  

## in Procfile:

`web: bundle exec puma -C config/puma.rb`  

`web:` is the process; `config/` denotes the config file passed to server; `puma.rb` is the server that runs it.

`worker: bundle exec rake my:rake_task`

`release: bundle exec rake db:migrate`

`worker` and `release` are Heroku processes (dyno-dependent)

**[Notes on running Rails apps on Heroku](https://github.com/aniasobo/dev-pills/blob/main/ruby/rails.md)**


