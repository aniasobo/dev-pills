# JS error handling

In a `try-catch` block, the `catch` takes a parameter which stores the exception/error thrown.  
To make a multi-level `try-catch` block, use `try-catch-finally` (also possible to just use `try-finally`).  
With a single `catch`, the `catch` becomes unconditional and it executes when any exception is thrown.  
The caught `exception` is an object with the following (likely) properties:  
`.name`    
`.message`    
`.stack`     

a `try-catch` block with a `catch` for different types of errors:

```
try {
  myroutine(); // may throw three types of exceptions
  testSuccessMessage();
} catch (e if e instanceof TypeError) {
  // statements to handle TypeError exceptions
} catch (e if e instanceof RangeError) {
  // statements to handle RangeError exceptions
} catch (e if e instanceof EvalError) {
  // statements to handle EvalError exceptions
} catch (e) {
  // statements to handle any unspecified exceptions
  logMyErrors(e); // pass exception object to error handler
}
```

same code but ES6:

```
try {
  myroutine(); // may throw three types of exceptions
} catch (e) {
  if (e instanceof TypeError) {
    // statements to handle TypeError exceptions
  } else if (e instanceof RangeError) {
    // statements to handle RangeError exceptions
  } else if (e instanceof EvalError) {
    // statements to handle EvalError exceptions
  } else {
    // statements to handle any unspecified exceptions
    logMyErrors(e); // pass exception object to error handler
  }
}
```

the `finally` clause executes whether or not an exception is thrown!
 
