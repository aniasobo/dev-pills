# The CSS Cascade

1. Importance
   1. transition
   2. `!important`
   3. animation
   4. normal
2. Origin
   1. Website
   2. User
   3. Browser (i.e. browser defaults, except for browser `!important`s which beat website `!important`s)
3. Specificity
   1. inline styles
   2. `#id`
   3. `.class` / `[attribute]` / `:pseudoclass` (pseudo classes are states)
   4. tag type / pseudo-selectors (pseudo selectors are elements added to the document)
4. Position
   1. last definition within the same ruleset wins

[SOURCE](https://wattenberger.com/blog/css-cascade)
