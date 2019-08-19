# Rake setup and tasks

## 1. Use Rake for database setup & destruction (with and without ORMs)

```
# in Rakefile:

task :setup do
  # Set up development and test databases
end

task :teardown do
  # Destroy development and test databases
end

task :seed do
  # Add some dummy data to the development database
end
```

--- 

## Rails rake tasks:

to view all your rake tasks: `$ rake -T` 

**Resources:**

* [rake documentation](https://www.stuartellis.name/articles/rake/)

* [good guide to rake](https://dev.to/vinistock/customizing-rails-rake-tasks-3bg5) 

* [rake best pracices](https://edelpero.svbtle.com/everything-you-always-wanted-to-know-about-writing-good-rake-tasks-but-were-afraid-to-ask)

* [recent guide to rake](https://www.rubyguides.com/2019/02/ruby-rake/)


**rake generator**

```
$ rails g task my_namespace
$ create lib/tasks/my_namespace.rake
```

this wil generate:

```
namespace :my_namespace do
  desc "TODO"
  task :my_task1 => :environment do
  end

  desc "TODO"
  task :my_task2 => :environment do
  end
end
```

**sample rake tasks:**

`rake -D time` for a list of tasks for finding time zone names. Default is UTC.

`rake my_task` runs the named task (seems to be running the namespace but not the task).  
`rake` runs all .rake files (but not specific tasks? 🤔 )


**rake task definition:** 

1. A description (desc-task-end block)
2. The name that identifies the task (:symbol)
3. The code to be executed by the task
*  optional input parameters and other tasks that are prerequisites.

sample: 
```
namespace :test
	desc "One line task description"
	task :name_of_task do
	  # Your code goes here
	end
end
```

sample task that depends on other tasks:
```
namespace :main do
  task :test do
    if true
      puts "Calling test2 task."
      Rake::Task["main:test2"].invoke #invokes main:test2
    else
      abort()
    end
  end

  task :test2 do
      puts ">Test2 task invoked"
  end
end
```

sample task with parameters:
```
desc "Example of task with parameters and prerequisites"
task :my_task, [:first_arg, :second_arg] => ["first_task", "second_task"] do |t, args|
  args.with_defaults(:first_arg => "Foo", :last_arg => "Bar")
  puts "First argument was: #{args.first_arg}"
  puts "Second argument was: #{args.second_arg}"
end
```

to run the above task you must specify the values: `rake my_task[one,two]`

```
namespace :import do
	desc "imports data from csv file"
	task :data => :environment do
		require 'csv'
		CSV.foreach('path/to/products.csv') do |row|
			name = row[0]
			price = row[1].to_i
			Product.create(name: name, price: price)
		end
	end
end
```

`rake import:data` to run the data task from the import namespace

**one-off tasks:**

keep in tasks without executing.

[option to test any added rake tasks](http://blog.jayfields.com/2006/11/ruby-testing-rake-tasks.html)


**add rake tasks to Procfile for Heroku to execute:**

`worker: bundle exec rake my:rake_task`

`release: bundle exec rake db:migrate`

`worker` and `release` are Heroku processes (dyno-dependent)