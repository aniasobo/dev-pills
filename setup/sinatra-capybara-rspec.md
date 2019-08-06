# Sinatra, Capybara and RSpec Ruby app setup checklist

- `mkdir project-name`  
- `cd project-name`  
- `git init`  
- `bundle init`  
- in Gemfile: 

```
source `https://rubygems.org`  

gem 'sinatra'
gem 'rspec'
gem 'capybara'
```

- `bundle install`  
-  `rspec --init`  (should create a spec folder and `spec_helper.rb`)  
- ` mkdir lib`  
- `touch app.rb`  
- in `app.rb`:  

```
require `sinatra/base'  
class SomeClass < Sinatra::Base

  get '/' do
    'Hello, World'
  end

run! if app_file == $0
```

- in `config.ru` (create if necessary)  

```
require_relative './app'
run SomeClass
```

- in `spec_helper.rb` 

```
ENV['RACK_ENV'] = test

require File.join(File.dirname(__FILE__), '..', 'app.rb')
require 'capybara'
require 'capybara/rspec'
require 'rspec'

Capybara.app = SomeClass
```

- `mkdir spec/features`  
- to run feature tests only: `rspec spec/features`  
- add flags to `.rspec`  

```
--format documentation
--color
```