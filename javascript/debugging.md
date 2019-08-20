# Debugging JavaScript

## `console` methods:

`console.log('%c some text', 'background: red;');` will apply this style to this string in console

`console.warn('warning text');`  

`console.error('error text');`  

`console.info('info string');`  

`console.assert(1 === 1, 'that is not ok');` - only displays the string if assertion is false  

`console.assert(p.classList.contains('className'), 'it does not check out');`  will display nothing if class exeist in `p` element 

`console.clear();`  

`console.dir(p);` - opens up the `p` element  

`console.group()` - grouping iterable objects with their properties  

`console.count('stuff to count')` - good for flagging console printouts  

**timing JS actions**  

```
console.time('fetching data');
fetch('source url')
  .then(data => data.json())
  .then(data => {
    console.timeEnd('fetching data');
    console.log(data);
  })
```

`console.table();` - displays an array of objects with properties as a table


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

### More resources

* [Reasoning about async javascript using frames](https://hackmd.io/cnH7BqucQ7yzqnLiqmizXw)