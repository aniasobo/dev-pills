# Remove duplicate values from array question

## JavaScript

NOTE - does not work on objects!

```
const withDuplicates = ["dog", "cat", "dog", "cow", "dog", "cat"]

const uniqueValues = [...new Set(withDuplicates)]
// ["dog", "cat", "cow"]
```

JavaScript `Set` data structure contains values that can't be repeated.

> By initializing a Set with a destructured array (the ... operator before new Set()), we pass the actual values the Set will automatically remove the duplicates. Finally, we convert it back to an array by wrapping it into square brackets.

[source](http://www.js-craft.io/blog/js-interview-question-removing-duplicates-from-an-array/)
