# Setting up RSpec

1. following `bundle init`, add `gem "rspec"` to your Gemfile and `bundle install`  
2. `rspec --init`
3. create your lib folder (subdivided into features and unit if necessary)
4. add requisite requires
5. add [flags](#.rspec-flags) to `.rspec`
6. if using SimpleCov, add the [SimpleCov code block](#simplecov) in `.spec_helper`, above the `RSpec.configure` block




## .rspec flags

```
--color --format documentation
```

## SimpleCov

```
SimpleCov.formatter = SimpleCov::Formatter::MultiFormatter.new([
  SimpleCov::Formatter::Console,
  # Want a nice code coverage website? Uncomment this next line!
  # SimpleCov::Formatter::HTMLFormatter
])
SimpleCov.start
```