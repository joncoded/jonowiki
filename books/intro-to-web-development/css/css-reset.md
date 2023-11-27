---
description: avoiding browser defaults using the * (global) selector
---

# 🔁 CSS reset

We can use the global sector, `*`, to set our own default values:

```css
* {
    border: 0;
    margin: 0;
    padding: 0;
}
```

...which ensures that we have no borders, margins or paddings for _any_ elements unless we specific them in our CSS!

We can also use this selector to add another important property called `box-sizing`:

```css
* {
    ...
    box-sizing: border-box;
}
```

The `border-box` value ensures that a child element with a `width` of 100% fits entirely within the parent's _borders ..._ (by default, the child element's width would include the borders!)
