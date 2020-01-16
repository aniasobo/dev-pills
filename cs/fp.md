# Functional programming

> Functional programming is programming without assignment statements.

[Source: Uncle Bob](https://blog.cleancoder.com/uncle-bob/2012/12/22/FPBE1-Whats-it-all-about.html)

**Referential Transparency** means that you can replace any function call with the value it returns. It also means that no function can have a side effect. [good explainer here](https://medium.com/@ItizAdz/immutability-2b2f524eafc4)

## FP no-nos:

* assignment statements (see above)
* loops
* mutating data
* impure functions

---

## Resources

* [Composing Software by Eric Elliott](https://medium.com/javascript-scene/composing-software-the-book-f31c77fc3ddc)
* [What I Wish Someone Had Explained About Functional Programming series by James Sinclair](https://jrsinclair.com/articles/2019/what-i-wish-someone-had-explained-about-functional-programming/)
* [How to Deal With Dirty Side Effects in Your Pure Functional JavaScript by James Sinclair](https://jrsinclair.com/articles/2018/how-to-deal-with-dirty-side-effects-in-your-pure-functional-javascript/)

---

## FP libraries for JS

* [Fantasy Land Specification](https://github.com/fantasyland/fantasy-land/tree/v4.0.1) - aka "Algebraic JavaScript Specification"
* [Ramda](../ramda/using-ramda.md)
* [Sanctuary - a JavaScript functional programming library inspired by Haskell and PureScript](https://sanctuary.js.org/); stricter than Ramda
* [Crocks](https://crocks.dev/) - a library/collection of Algebraic Data Types
