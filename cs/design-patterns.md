# Design patterns in web dev

## Singleton

- only allows a single instance of an object or class
- uses a global variable to store that instance
- can be lazy loaded to make sure there's only one instance of the class because it will only be created when needed
- usually gets implemented in the constructor
- GOAL: to regulate the global state of the application
- EXAMPLE: logger

## Strategy

- advanced if/else statement
- an interface for a method in your base class, used to find the right implementation of that method in a derived class
- implementation is decided at runtime based on the client
- see metaprogramming in Ruby
- useful for required and optional methods for a class
- commonly used with payment processing systems - decouples the payment methods from the checkout process, adding and updating strategies without changing the shopping cart or checkout process or any underlying code

## Observer

- similar to the V in MVC
- observer gets the data from the subject (M) and the state of that data when it's been updated
- one-to-many relationship between the subject and all its observers
- often used in: sending notifications, updates, filtering, handling subscribers
- EXAMPLE: filter selects populated based on previous filter selection

## Decorator

- adds extra methods and properties to descendant class that aren't present in the base class, and that could mess up the instances
- adds those directly to the instance, without affecting any other instances
- EXAMPLE: additional pizza toppings added at checkout

[SOURCE](https://www.freecodecamp.org/news/4-design-patterns-to-use-in-web-development/)
