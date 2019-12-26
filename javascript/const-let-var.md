# `const`, `let` and `var`

## Pros of the `prefer-const` setting in ESLint

* less mental overhead
* less risk of reassignment-related bugs
* forces you to learn about variable mutation and how that's different from assignment
* speeds up learning about meaningless assignment 
* potential preformance gains with variables that don't undergo reassignment

## Cons of the `prefer-const` ESLint setting

* the intent of forcing something to be constant is lost
* can be confused for immutability
* pressures user to avoid redeclaring
* risk of not causing bugs with reassignment
* no performance benefits

[Source - Dan Abramov](https://overreacted.io/on-let-vs-const/)
