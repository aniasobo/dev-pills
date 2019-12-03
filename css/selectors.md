# CSS selectors

From least specific to most specific:

```
* {
  /* Universal selector */
}

tag {
  /* Type selector */
}

tag::before {
  /* Type selector (psuedo element) */
}

.class {
  /* Class selector */
}

.class:hover {
  /* Class selector (pseudo class) */
}

[attr] {
  /* Attribute selector */
}

#id {
  /* ID selector */
}
```

Pseudo elements have two colons (`::`, or `::before`) and pseudo classes have one colon (`:`, or `:hover`).
