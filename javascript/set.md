# The `Set` object

The `Set` object is a collection of values in which you can store _unique_ primitive values or _object references_ (not object values).

Create a new instance with `const mySet = new Set();`

Add to set with `mySet.add(1);`

Check if value is included with `console.log(mySet.has(1));`

This checks for object references, not object keys:

```
const obj = { name: "Daffodil" };
mySet.add(obj);
console.log(mySet.has(obj));
// true

console.log(mySet.has({ name: "Daffodil" }));
// false
```

Check number of elements within a set with `console.log(mySet.size);`

Delete from set with `mySet.delete(1);`

Empty the set of all values with `mySet.clear();`

Iterate over a set with `forEach()`:

```
new Set([1, 2, 3]).forEach(el => {
  console.log(el * 2);
});
// 2 4 6
```

## `Set` is good for:

- [removing duplicate values (that aren't objects) from an array](../tech-interviews/remove-duplicates-from-array.md) - if you initialize a set as an array of values with duplicates, it will remove the duplicates
- finding the union, intersection and difference between two sets of data
- as it's required to be implemented using hash tables, it has superior performance to arrays - lookup is instantaneous, while array needs to be traversed to find the item
- keeping track of binary state associated with an object (for example, state of an accordion slide being closed/open):

```
const isOpen = new Set();

function toggle(menuItem) {
  if (isOpen.has(menuItem)) {
    isOpen.delete(menuItem);
  } else {
    isOpen.add(menuItem);
  }
}
```

## Tradeoffs:

- lacks Array's data manipulation methods such as `sort()`, `map()`, `filter()` and `reduce()`
- set does not have a way to access a value by a key or index
  - `keys()` and `values()` will return the same iterator
  - `entries()` will return the values twice
  - it's customary to only use `values()` for sets

[Source: TypeOfNaN newsletter](https://buttondown.email/typeofnan/archive/the-javascript-set-object/)

[ECMA Set object specification](https://tc39.es/ecma262/?utm_source=typeofnan&utm_medium=email#sec-set-objects)
