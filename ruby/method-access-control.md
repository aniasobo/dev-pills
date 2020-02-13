# Access Control - Difference Between `public`, `private` and `protected` Methods

## `private` 

* can only be used within the class definition 
* for internal usage - basically internal helper methods
* the only way to call a `private` method is from within a `public` method
* cannot be called with an explicit receiver (including `self` - the receiver is always implicitly `self`) 
* must always be called with an implicit receiver 
* can be called from within the class in which it is declared as well as its subclasses

## `protected` 

* for internal usage in other classes whenever inheritance isn't set up
* can be called with or without an explicit receiver, but that receiver is always `self` (its defining class) or an object that inherits from `self`
* the "fat model, skinny controller" paradigm of Rails - bulk up your non-response related logic in your models using `def self.method_name` protected methods

## `public` 

* default
* describe the outside behaviours of an object

[SOURCE](https://medium.com/@tjoye20/ruby-access-control-basics-public-vs-private-vs-protected-methods-7788b26e04a7)
