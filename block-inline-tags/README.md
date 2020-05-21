# Display

## Attributes

It'd take a lot of time impossible to go through all CSS attributes, so we'll
only cover the most important ones. The rest is up to you - you should read
about new attribute you encounter and it's possible values on CSS Tricks and/or
MDN.
Many attributes have shorthands. For readability purposes I strongly suggest you
avoid using them. For example compare:

```css
font: 44px/20px Georgia, sans-serif;
```

to:

```css
font-family: Georgia, sans-serif;
font-size: 44px;
line-height: 20px;
```

## Block and inline elements

Demo: https://codepen.io/no-cheating/pen/OJVQBvV?editors=1000

- Blocks take the whole available space (width).
- Inline take only as much space as their content needs.
  List of all block and inline elements:
- https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements
- https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements
- Blocks cannot descend from inline.
  https://validator.w3.org/

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>Test</title>
  </head>
  <body>
    <span>
      <p></p>
    </span>
  </body>
</html>
```

Exercise: https://codepen.io/no-cheating/pen/VwLQVbv?editors=1000
Display

---

Demo: https://codepen.io/no-cheating/pen/XWmpRGL
Being block or inline is controlled by `display` property in CSS. That might
be the most important property in CSS.
Main values:

- block
- inline
- inline-block
- table
- grid
- flex
- none
  Inline block

---

Demo: https://codepen.io/no-cheating/pen/oNjBwbY?editors=1100
Whitespace

---

Demo: https://codepen.io/no-cheating/pen/oNjBwbY?editors=1100

- All whitespace sequences are collapsed into single space.
- Most of whitespace is ignored (exception: inline-block)
- Whitespace also don't matter for CSS
- Still YOU should care about whitespace as in all code you write
  Floats

---

Demo: https://codepen.io/no-cheating/pen/wvKgegE?editors=1100
Standard layout

---

Exercise: https://codepen.io/no-cheating/pen/ZEbLyaY?editors=1100
Additional resources

---

`display` attribute:
https://css-tricks.com/almanac/properties/d/display/
List of all block elements:
https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements
List of all inline elements:
https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements
Fighting space between inline blocks:
