# 🚧 CSS selectors

### Structure

A template for two CSS selectors and their properties:&#x20;

```css
(selector1) {
    (property1) : (value1); 
}

(selector2) {
    (property2) : (value2);
}

...
```

For example, to make a link red with no underline:

```css
a {
    color: red;
    text-decoration: none;
}
```

### Element selectors

To update the style for a top-level element, such as an `<h1>,`we simply use the element's name as the selector, e.g.:

```css
h1 {
    ...
}
```

### Class selectors

To update the style for any element that has a specific class, e.g.

`<h1 class="red">`

...we would use the dot notation as such:

```css
.red {
    color: red;
}
```

Note that we can have more precision with this notation:

```css
h1.red {
    color: red;
}
```

...which would mean only the `<h1>` on a page with the class of `red` would get that style!

### ID selectors

To update the style for a unique element on the page, e.g.

`<section id="toronto-map">`

...we would use the hashtag notation as such:

```css
#toronto-map {
    ...
}
```

Recall that such an `id` should appear only once per HTML page!

### Attribute selectors

To update the style for any element that has a specific attribute, e.g.

`<span data-status="...">`

...we would use the square bracket notation:

```css
[data-status] {
    ...
}
```

Note that we could also specify attributes with certain values too:

```css
[data-status="warning"] {
    color: red;
}
```

### Partial match selectors

Looking at the attribute selectors above, we can see this has many fine-grained implications:

```css
/* starts with "war" */
[data-status^="war"] { ... } 

/* contains "war" */
[data-status*="war"] { ... }

/* ends with "war" */
[data-status$="war"] { ... }
```

