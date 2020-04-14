# `&&` and `||` operators in JS

## Falsy values

```
Boolean(false);     // => false
Boolean(0);         // => false
Boolean('');        // => false
Boolean(null);      // => false
Boolean(undefined); // => false
Boolean(NaN);       // => false
```

## Truthy values

```
Boolean(true);             // => true
Boolean(4);                // => true
Boolean('Hello');          // => true
Boolean({ name: 'John' }); // => true
```

## The `&&` operator

This operator chain: `operand1 && operand2 && ... && operandN` evaluates to:

> Starting from left and moving to the right, return the first operand that is falsy. If no falsy operand was found, return the latest operand.

Evaluation stops as soon as a falsy value is encountered.

Example: `3 && 1 && 0 && 10; // => 0` (because `0` is falsy)

## The `||` operator

This operator chain: `operand1 || operand2 || ... || operandN` evaluates to:

> Starting from left and moving to the right, return the first operand that is truthy. If no truthy operand was found, return the latest operand.

Evaluation stops as soon as a truthy value is found.

`0 || -1 || 10; // => -1` because `0` is falsy and the next operand is truthy, so it gets returned and evaluation stops.

### Default value with `||`

The side effect of how `||` evaluates is that it's perfect for setting default/fallback values for when a property is missing.

[SOURCE](https://dmitripavlutin.com/javascript-and-or-logical-operators/)
