---
description: adjusting our style sheet for differently-sized screens
---

# 📲 CSS media queries

We can provide differently-sized screens with different CSS (and also customize the size ranges) with `@media` queries:

```css
@media only screen and (max-width: 768px) {
    .card {
        width: 100%;
    }
}

@media only screen and (min-width: 768px) and (max-width: 1024px) {
    .card {
        width: 50%;
    }
}

@media only screen and (min-width: 1024px) {
    .card {
        width: 33%;
    }
}
```

In the example above, we accommodate three different screen sizes:

* **mobile devices** (anywhere up to 767px wide): 1 card (100% width) per row
* **tablets** (768-1024px wide): 2 cards (each 50% wide) per row
* **desktops** (1024+ px wide): 3 cards (each 33% wide) per row
