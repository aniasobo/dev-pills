# Debugging JavaScript

## `console` methods:

tba

## Notes from Makers 

- when using the Chrome devtools debugger, hover over variables to see their values
- looking at the value of `this` in different parts of the code with `console.log(this)`
- am I using the correct function? 

```
'console.log(airport.land);'
```

- what is this function returning? 

```
'console.log(airport.land());'
```

- what does this parameter contain? 

```
Airport.prototype.land = function(plane) {
  console.log(plane);
}
```
