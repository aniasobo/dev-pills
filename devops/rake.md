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