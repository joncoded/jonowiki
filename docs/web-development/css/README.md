---
description: styling a website using a design language
---

# 🖼 CSS

**Cascading style sheets (CSS)** allows us to "style" a website and its components, in terms of its:

* Backgrounds
* Spacing (margins, borders, paddings)
* Displaying
* Positioning
* Layering ("bring-to-front")
* Visibility (hiding/showing)
* Transforming (rotating/flipping)
* Animating
* Typography

### Example

CSS looks like this:

```css
h1 {
    font-size: 48px;
    color: red;
}

h2 {
    font-size: 24px;
    color: blue;
    margin-bottom: 30px;
}

.overlapping {
    position: absolute;
    top: 0;
    z-index: 10000;
}
```

### Selectors

A **selector** refers to an element in an HTML document (e.g. `h1`)  and has a set of curly braces `{}`:

```css
h1 {}
```

### Declarations

A **declaration** consists of:

```css
[a property]: [a value]
```

Declarations lie inside a **declaration block**, i.e. inside the curly braces `{}`, e.g.:

```css
h1 {
    font-size: 48px; 
    color: red; 
}
```

A group of selectors with declarations can form a **stylesheet** (the "SS" in CSS!)

Whereas:

* **HTML** provides a _rough order and arrangement_ of elements of a webpage...
* ...**CSS** supplies _design details_ with pixel-precision values!

### Cascades

The "C" in CSS refers to "cascading" and, in this context, that simply means that any styling instruction/rule that happens further down the stylesheet, becomes the new rule!

For example, in an HTML document like this:

```xml
<html>
    <body>
        <h1 class="red">Title</h1>
    </body>
</html>
```

The text will appear red if the CSS works like this:

```css
h1 {
    color: green; 
}

.red {
    /* any element with class="red" */
    color: red;
}
```

The second instruction overrides the first because it comes later in the stylesheet!
