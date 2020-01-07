# CSS custom properties, i.e. CSS variables

Specify the custom property:

```
.some-container {
  --text-color: #FF5B5B;
}
```

Use it like:

```
.some-container__child {
  color: var(--text-color);
}
```

To override for variants:

```
.button {
  --background-color: #16DBC4; /* the default */
  background-color: var(--background-color);
}

.button--blue {
  --background-color: #43CBFF;
}
```
 ---

 ## As a design system

 Specify your custom properties in `root`:

 ```
 :root {
  --primary-background-color: #FFFFFF;
  --primary-text-color: #0E0E0E;
  --secondary-background-color: #EEEEEE;
  --secondary-text-color: #000000;
  --tertiary-background-color: #FF8034;
  --tertiary-text-color: #FFFFFF;
}
 ```

Use them to specify your high-level elements:

```
.paragraph {
  color: var(--primary-text-color);
}

.label {
  color: var(--secondary-text-color);
}

.box {
  background-color: var(--tertiary-background-color);
  color: var(--tertiary-text-color);
}
```

Make a standout section of special styles:

```
.popout-section {
  --primary-background-color: #0E0E0E;
  --primary-text-color: #FFFFFF;
  --secondary-background-color: #000000;
  --secondary-text-color: #EEEEEE;
  --tertiary-background-color: #FFFFFF;
  --tertiary-text-color: #FF8034;

  background-color: var(--primary-text-color);
}
```

You can now wrap anything that you want to stand out in this class:

```diff
- <section>
+ <section class="popout-section">
  <p class="paragraph">This will be black text on white background</p>
  <label for="some-value" class="label">What's your value?
    <input type="number" max="10" min="1">
  </label>
</section>
```

---

## Theming

Specify your global styles for themes:

```
.high-contrast-theme {
  --primary-background-color: black;
  --primary-text-color: white;
  --secondary-background-color: white;
  --secondary-text-color: black;
  --tertiary-background-color: black;
  --tertiary-text-color: yellow;
}
.christmas-theme {
  --primary-background-color: red;
  --primary-text-color: white;
  --secondary-background-color: white;
  --secondary-text-color: red;
  --tertiary-background-color: green;
  --tertiary-text-color: white;
}
```

Single `@media` query can be used to specify the styles of your dark theme:

```
@media screen and (prefers-color-scheme: dark) {
  ::root {
    --primary-background-color: #0E0E0E;
    --primary-text-color: #FFFFFF;
    --secondary-background-color: #000000;
    --secondary-text-color: #EEEEEE;
    --tertiary-background-color: #FFFFFF;
    --tertiary-text-color: #FF8034;
  }
}
```

---

## Inline use

You can use custom CSS properties inline like so:

```
<section class="popout-section" style="--background-color: rebeccapurple;">
  <p class="paragraph">This will be white text on purp' background</p>
  <label for="some-value" class="label">What's your value?
    <input type="number" max="10" min="1">
  </label>
</section>
```

[Source - CSS Christmas 2019](https://css.christmas/2019/2)
