# Service objects in rails

Source: Extracting service objects in _Growing Rails Applications in Practice_ by Henning Koch & Thomas Eisenbarth

- use when no need for the restrictions imposed by ActiveModel (validations, callbacks, dirty tracking etc) and no need to tie to ActiveRecord
- extract this code into plain Ruby classes that perform one job - they're called _service classes_

## Benefits of using services:

- less side effects in model's lifecycles
- easier to test the core model with less validations and callbacks - ease of creating sample records
- more readable code
