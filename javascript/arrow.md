# Arrow functions basics

Arrow functions have an implicit `return`!
```
var funcName = (params) => params + 2
funcName(2);
// 4
```

This is particularly useful in React components - when functional components just immediately `return`, use `()` to wrap your function; if additional `const`s or functions are needed inside the functional component, wrap the function in `{}`.

if only one parameter:

```
var double = num => num * 2
```

syntax:

```
(parameters) => { statements }
```

syntax for no parameters:

```
() => { statements }
```

syntax for a single parameter:

```
parameters => { statements }
```

if only returning an expression, remove the curly bracket:

```
parameters => expression
// is equivalent to:
function (parameters){
  return expression;
}
```

**arrow functions do not bind `this`**

instead, `this` keeps its meaning from the original context (its lexical binding).

example of `this.` changing context to `window`:

```
function Counter() {
  this.num = 0;
  this.timer = setInterval(function add() {
    this.num++;
    console.log(this.num);
  }, 1000);
}
```

same function, refactored to work due to keeping the scope of `this`:

```
function Counter() {
  this.num = 0;
  this.timer = setInterval(() => {
    this.num++;
    console.log(this.num);
  }, 1000);
}
```

[Old school but thorough article about arrow functions](https://2ality.com/2012/04/arrow-functions.html)
