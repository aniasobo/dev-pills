# CSS font sizing

```
body {
  font: normal 100% Cambria, serif;
}
```

`normal` is the weight of the font  

`100%` - browser default (16px); lets you size the rest of fonts with ems, so proportionally (see [CSS units](units.md))


## 💫 Calculating font size in `em`

Target font size in `px` divided by the font size of parent element:

> target / context = result

**To set an `h1` to `24px`:** `24 / 16 = 1.5`, therefore: 

```
h1 {
  font-size: 1.5em; // 24 px divided by 16px
}
```

(from _Responsive Web Design_ by Ethan Marcotte)