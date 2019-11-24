# Functional vs class components

**Class components** 

* are ES6 classes
* use state, `constructor`, `super`, lifecycle methods
* use only when necessary - for example, when you need access to lifecycle methods


**Functional components** 

* are functions
* constrained by having to take `props` as an argument and return valid JSX
* lack state and lifecycle methods (a.k.a stateless components)
* do not bind `this`
* make components more readable
* are easy to test because they have no side effects, can easily be isolated and exported - no need to mock or isolate state as the `html` output will be the same for the same input
* potentially more performant
* easier to debug, with no need to constantly `console.log` the state of the component at different points
* are more reusable than class components
* reduce coupling, making code more maintainable

## When to use each

**Rule of thumb:** if you ever have a class component with only a `render` method – you should always make it a functional component.

**Rule of thumb:** always start with a functional component. It's easier t refactor a functional component to a class component than the othe way round.




[Source](https://programmingwithmosh.com/react/react-functional-components/)