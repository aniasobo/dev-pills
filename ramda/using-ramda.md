# Why use Ramda

Ramda is a utility library like `lodash`, but purely functional.

All functions are curried by default:

> all the functions in Ramda have a signature where the data comes last — so instead of `array.map` for example, you do `R.map(yourMappingFunction, yourArray)`
> and because they’re curried, you can do like…
> `const coolMapFnIWantToReuse = R.map(() => myfunc…)`
> …and then just call it on different arrays:
> `const mapped = coolMapFnIWantToReuse(array1)`
> `const alsoMapped = coolMapFnIWantToReuse(array2)`

Some of Ramda is as performant or faster than using native ES6 functions. Mapping over arrays is faster with native functions but other implementations of Ramda might be more performant.

Distinguishing features of Ramda compared to other libraries like lodash:

* R takes the function first and the data last
* all functions of 2 or more arguments are automatically curried - making it easy to compose functions to create new functions
* 