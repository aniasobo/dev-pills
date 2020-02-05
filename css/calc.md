# A few uses of the `calc()` method

`calc()` is a native CSS feature that calculates any number value using one of its 4 operators: 

1. add `(+)` 
2. subtract `(-)` 
3. multiply `(*)`
4. divide `(/)`

**The most useful ability of calc() is its ability to mix units, like percentages and pixels** (while preprocessors can't). This happens at render time. 

`calc()` has very good browser support.


## Example syntax

```
.thing {
  width: 90%;                   /* fallback if needed */
  width: calc(100% - 3em);      /* math operator must be spaced */
}
```

[SOURCE AND USE CASES on CSS Tricks](https://css-tricks.com/a-couple-of-use-cases-for-calc/)
