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

Let's break that down ... the **selector** (h1) sits before an empty **declaration block** (curly braces)**:**&#x20;

```css
h1 {}
```

Meanwhile, a **declaration** consists of:

```css
[a property]: [a value]
```

e.g.:&#x20;

```css
h1 {
    font-size: 48px; /* a comment about a font-size of 48 pixels */
    color: red; /* a comment about its font color being red */
}
```

### Essence

Whereas HTML provides a _rough order and arrangement_ of elements of a webpage, CSS supplies _design details_ with pixel-precision values!

So let's get started with CSS:

{% content-ref url="css-setup.md" %}
[css-setup.md](css-setup.md)
{% endcontent-ref %}
