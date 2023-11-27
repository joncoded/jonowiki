---
description: determining how we arrange something on screen
---

# 📍 CSS layout properties

Five main CSS properties that determine the arrangement of layouts on a webpage:

* `position`
* `display`
* `z-index` (overlap)
* `float`
* `clear`

### Position

The `position` property determines where and how an element appears on the entirety of the page, and can take on the following values:

* `static`
  * the default position, i.e. after the last element
* `relative`
  * positions the element relative to its _static_ positioning
  * does not affect the positioning of other elements
  * used in conjunction with `top`,`bottom`, `left` and `right` co-properties
    * each will have 0 by default (and when not mentioned)
* `absolute`
  * positions the element relative to its _parent_ element
  * does not affect the positioning of other elements
  * used in conjunction with `top`,`bottom`, `left` and `right` co-properties
    * each will have 0 by default (and when not mentioned)
* `fixed`
  * positions the element relative to the _screen_ or _viewport_
* `sticky`
  * positions the element relative to the _document_ until the user scrolls past a specified threshold
    * e.g. if we have `top: 200px` on a sticky element, then the sticky element will stop scrolling upwards, _once_ it reaches 200 pixels from the top of the document!

```css
div.example {
    position: static | relative | absolute | fixed | sticky
}
```

### Display

The `display` property determines if and how an element appears relative to its preceding (sibling) element, and can take on the following values:&#x20;

* `none`
  * the element disappears&#x20;
  * this differs from `visibility: hidden` in that `display: none` _does_ _not take up space_
* `block`
  * the element appears as it should on its own new line
* `inline`
  * the element appears on the same line as its preceding element, regardless
* `inline-block`
  * the element appears on the same line as its preceding element, but allows it to appear on a new line when necessary

There also exist newer values such as `flex` and `grid` which will have their own pages further on in this book!

```css
div.example {
    display: none | block | inline | inline-block;    
}
```

### Z-index (overlap)

The `z-index` property allows an element to overlap another element if it has a `position` value of `absolute`, `fixed` or `sticky` : the higher the z-index number (an integer), the more "on top" the element will become:

```css
div.example1 {
/* this will get overlapped by both of the below */
    position: absolute;
    top: 0;
    z-index: 1;
}

div.example2 {
/* this will overlap example1 only */
    position: absolute;
    top: 0
    z-index: 10;
}

div.example3 {
/* this will overlap both example1 and example2 */
    position: absolute;
    top: 0;
    z-index: 100;
}

```

### Float

The `float` property ensures that the element will appear _beside_ rather than _below_ its preceding sibling element, and can take on the following values:

* `none`
  * the default value; the element will appear accordingly to its position in the DOM
* `left`
  * the element will appear beside its _preceding_ element, to the left
* `right`
  * the element will appear beside its _subsequent_ element, to the right

This will result in the image appearing to the _left_ of the text, despite its position in the DOM:&#x20;

```html
<div>
    <p>Some text</p>
    <img style="float: left" src="...">
</div>
```

This will result in the image appearing to the _right_ of the text, despite its position in the DOM:&#x20;

```html
<div>
    <img style="float: right" src="...">
    <p>Some text</p>
</div>
```

### Clear

The `clear` property specifies what should happen when the next element appears after an element with `float`

```css
<div>
    <p>Some text</p>
    <img style="float: left" src="...">
    <p style="clear: both">Some more text</p>
</div>
```

In the example above, the second paragraph would appear on a new line under the first paragraph and image! The `clear` property can also take on values of `left` and `right` if there exists the desire to clear the float of only the elements with a `float: left` or `float: right`
