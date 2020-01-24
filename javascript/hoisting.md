# Hoisting in JavaScript

## Function declaration vs function expression

**function declaration** starts with the word `function`, then assigns it a name; **is hoisted**.

**function expression** starts with a variable declaration, and the variable is assigned to an anonymous function; **is not hoisted**.

```
// Function declaration
function add(num1, num2) {
	return num1 + num2;
}

// Function expression
var add = function (num1, num2) {
	return num1 + num2;
};
```

Function declarations are stored in memory when a JS file is compiled but before it's executed. The code is already aware of those functions when it runs, regardless of their location in code.

```
// This was hoisted, so it works
// returns 6
add(3, 3);
function add(num1, num2) {
	return num1 + num2;
};


// This was not, so it doesn't
// The browser knowns subtract is a variable, but doesn't know it's a function yet
// returns Uncaught TypeError: subtract is not a function
substract(7, 4);
var subtract = function (num1, num2) {
	return num1 - num2;
};
```

**Function expressions** create a more rigid code structure.

## Variables are hoisted but their values are not

Because **function expressions** are variables, the browser knows they already exists but values are assigned to them in order of execution

[Source - Chris Ferdinandi](https://gomakethings.com/what-is-hoisting-in-vanilla-javascript/?mc_cid=1303dffebc&mc_eid=94a14c82aa)
