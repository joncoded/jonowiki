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

...we use the dot notation as such:

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

### Attribute selectors

### Partial match selectors

