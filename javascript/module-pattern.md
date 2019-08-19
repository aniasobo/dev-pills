# JavaScript module pattern

_notes from Makers Academy workshop_  

Similar to an IIFE but with export code around:

```
(function(exports) {
  var EXCLAMATION_MARK_COUNT = 5

  function exclaim(string) {
    return string + "!".repeat(EXCLAMATION_MARK_COUNT);
  };

  exports.exclaim = exclaim;
})(this);
```

the above module would be used like this:

```
(function(exports) {
  var EXCLAMATION_MARK_COUNT = 5

  function exclaim(string) {
    return string + "!".repeat(EXCLAMATION_MARK_COUNT);
  };

  exports.exclaim = exclaim;
})(this);

// prints "hi!!!!!"
console.log(exclaim("hi"));

// throws a ReferenceError
console.log(EXCLAMATION_MARK_COUNT);
```

The value of `this` in the export code is `window`, the place where all globals are stored.

The variables that don't get included in the exports stay hidden/private.

**in Node.js**

> The values of `this` in the browser (`window`) and `this` in Node.js (`exports`) are different. But they are similar enough that they can both be massaged by this pattern to let us write code that will work in both environments.


[`This` keyword explainer](https://itnext.io/the-this-keyword-in-javascript-demystified-c389c92de26d)
