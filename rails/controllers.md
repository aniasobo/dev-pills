# Writing better rails controllers

Source: Beautiful Controllers in _Growing Rails Applications in Practice_ by Henning Koch & Thomas Eisenbarth

- the less business logic the better
- use _standard controller design_ for every single user interaction by **reducing every user interaction to a Rails CRUD resource**
- make them short, DRY and easy to read
- they should only provide the _minimum amount of glue code_ to negotiate between request and model
- use [this standard implementation of CRUD](controller_template.rb) unless there's a good reason not to
- controller actions delegate most of the work to helper methods to keep code DRY
- `note_scope` method guards access to the `Note` model - good way to implement access control
- `note_params` whitelists the attributes that the user is allowed to change (strong parameters); authorisation **does not belong on the model**
- every action reads or changes **a single model**

## Responsibilities of a controller:

1. security - authentication, authorization
2. parsing and whitelisting parameters
3. loading and instantiating the model
4. deciding which view to render

## Control flow:

1. Instantiate an object
2. Assign attributes from params
3. Try to `save` the object
4. Render a view or redirect

## Refactoring bad controllers

- use ActiveModel-based model classes
- move code from controller into class inheriting from ActiveType
