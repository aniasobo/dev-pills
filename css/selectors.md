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

**Space!**

```
.foo.bar {
  /* without a space */
}

// targets:

<div class="foo bar">I'm targeted</div>

.foo .bar {
  /* with a space */
}

// targets: 

<div class="foo">
  <div class="bar">I'm targeted</div>
</div>
```



[Source](https://www.taniarascia.com/overview-of-css-concepts/)
