---
description: positioning layouts into rows and columns
---

# 🌐 CSS grid

### grid

By default, the `display: grid` works quite like `display: block`:

```css
.grid {
    display: grid;
}
```

```markup
<body>

    <div class="grid">
        <div class="card">a</div>
        <div class="card">b</div>
        <div class="card">c</div>
        <div class="card">d</div>
    </div>

</body>
```

The code above would simply display four card-like containers on top of each other:

\[ a ]\
\[ b ]\
\[ c ]\
\[ d ]

### grid-template-columns

However, if we were to introduce another property into `.grid` called `grid-template-columns` we could create an layout in a much easier fashion, without having too many class names:

```css
.grid {
    display: grid;
    grid-template-columns: 100px 200px 100px;
}
```

This would simply create a grid of three columns:&#x20;

* first column: 100px wide
* middle column: 200px wide
* last column: 100px wide&#x20;

(more to come)
