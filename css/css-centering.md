# Centering in CSS

```
div {
  margin: 0 auto;
}
```

`0` value -> puts no margin on top and bottom  

`auto` -> forces the browser to adjust sides so that content is centred  


**Must** be used with the `width` attribute added - not possible to center a div within an element that fills the page - it can only be centred relative to its width 

## 📐 Calculating the width

Use the `target / context = result` equation to translate the dimensions of your design from px to %, like so:

```
containing-element {
  width: 93.75%; // 900px / 960px
}
```

### Don't forget to use the same formula to add a flexible gutter

```
.gutter {
  padding: 0.8em 5.33%; // 48px / 900px
}
```

(from _Responsive Web Design_ by Ethan Marcotte)

Also: [centering using nested grid](https://www.quackit.com/css/grid/tutorial/create_a_nested_grid.cfm)

Also: [Learn CSS Layout](http://learnlayout.com/)


## Centering using flexbox

```
.vertical-container {
  height: 300px;
  display: -webkit-flex;
  display:         flex;
  -webkit-align-items: center;
          align-items: center;
  -webkit-justify-content: center;
          justify-content: center;
}
```

[SOURCE - Learn CSS Layout](http://learnlayout.com/flexbox.html)
