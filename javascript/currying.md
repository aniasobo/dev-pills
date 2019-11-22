# Currying

* [https://www.yazeedb.com/posts/deeply-understand-currying-in-7-minutes](https://www.yazeedb.com/posts/deeply-understand-currying-in-7-minutes)
* [parts of this explainer](https://medium.com/javascript-scene/the-rise-and-fall-and-rise-of-functional-programming-composable-software-c2d91b424c8c)
* [all functions in the Ramda utility library are curried by default](../ramda/using-ramda.md)

> so, currying is where a function is designed to only take 1 of N arguments at a time — you call it with the first arg, then call that with the 2nd, then call that with the 3rd, etc…
> currying is a strict style of what’s called partial application, where you can call a function with SOME but not all of its args at one point, but it will only be resolved when it’s called with its final argument, otherwise it just gives you back the partially applied result