---
description: targeting a group of elements of a webpage
---

# ✅ CSS selectors

### Structure

The template for two CSS selectors and their properties:

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

To update the style for a top-level element, such as an `<h1>` or `<a>` we simply use the element's name as the selector, e.g.:

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

`<section id="war-map">`

...we would use the hashtag notation as such:

```css
#war-map {
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

/* contains "nin" */
[data-status*="nin"] { ... }

/* ends with "ing" */
[data-status$="ing"] { ... }
```

In the example above, any element with a `data-status` value of:&#x20;

* "warning" would take the styles in all three declaration blocks
* "churning" would take the styles in only the last two blocks
* "warsaw" would take the styles in only the first block

### Child selectors

Let us define the parent element and child element as such:

```html
<div> <!-- parent -->
  <p> <!-- child -->
  </p>
</div>
```

Then, to target only the child element, we simply use the "greater than" notation:

```css
div > p {
    ...
}
```

### Descendant selectors

To target grand-children and great-grand-children elements (and so on), we just keep chaining the "greater than" notation:

```css
main > aside > p > span {
    ...
}
```

In order to select descendants of an ancestor element, regardless of "generation", simply place them side by side:

```css
main p {
    ...
}
```

That would apply the rule to any paragraph in the `<main>` tag!

### Sibling selectors

Say that we have an element on the same level as another element in the HTML, e.g.:

```markup
<header>
    <h2>...</h2>
    <p>...</p>
    <aside>...</aside>
</header>
```

#### Adjacent siblings

To reach an adjacent element on the same level as another element, we can use the "plus" notation:

```css
header h2 + p {
    ...
}
```

Note that, in that example, the `<p>` must come after `<h2>`!

#### Non-adjacent siblings

However, to reach a non-adjacent element, we can use the "tilde" notation:

```css
header h2 ~ aside {
    ...
}
```

That about covers most of the selectors we would encounter on a daily basis in front-end web development! Of course, more exist and we would simply search for them when the need arises!
