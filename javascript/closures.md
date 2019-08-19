# JavaScript closures

* [Good tutorial on closures from FCC](https://www.freecodecamp.org/news/learn-javascript-closures-in-n-minutes/)
* [Closures on HackMD](https://hackmd.io/cIFsMAqISHqVHN_-p9hY0Q)


**notes from Makers workshop:**

```
function makeAdder(x) {
  return function(y) {
    return x + y;
  };
}

var add5 = makeAdder(5);
var add10 = makeAdder(10);

console.log(add5(2));  // 7
console.log(add10(2)); // 12
```

`add5` and `add10` are closures - they share the same function body definition but store different lexical environments.

In `add5`s lexical environment `x` is `5`; in `add10`s, it's `10`.

Closures let you associate some data (ie the lexical environment) with a function that makes an operation on it.

Closure can be used analogously to OO-style Object with only a single method (the `add5` object only adds integers to `5`).

Closures are useful for event-based functions, such as this one that converts `rem/em` font sizes to pixel sizes:

```
function makeSizer(size) {
  return function() {
    document.body.style.fontSize = size + 'px';
  };
}

var size12 = makeSizer(12);
var size14 = makeSizer(14);
var size16 = makeSizer(16);

document.getElementById('size-12').onclick = size12;
document.getElementById('size-14').onclick = size14;
document.getElementById('size-16').onclick = size16;
```

One way to make a method private in JS is to put it in a closure.