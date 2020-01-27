# `border-box` vs `content-box`

Do padding and borders count as part of the element's size?

Border box - YES - borders and padding are part of an element's size
Content box - NO - orders and padding are not part of an element's size

Set `box-sizing` to `border-box` on everything (`*`). Always. 
On the rare occasion something needs to be `content-box`, you can override it. 

```
* {
  box-sizing: border-box;
}
```

## More resources:

* [Box Sizing on CSS Tricks](https://css-tricks.com/box-sizing/)
* [Inheriting Box Sizing on CSS Tricks](https://css-tricks.com/inheriting-box-sizing-probably-slightly-better-best-practice/)

