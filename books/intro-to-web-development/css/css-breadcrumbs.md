---
description: creating a kind of secondary navigation
---

# 🍞 CSS breadcrumbs

**Breadcrumbs** enable a user to see the "forest for the trees" by having a one-liner navigation that shows where the current page lies, relative to the home page ... the breadcrumbs thus provide a hierarchical "trail" back to the home page:

```
Home > Level 1 > Level 2 > Current 
```

To implement this, we use an unordered list:&#x20;

{% code title="index.html" %}
```markup
<body>

...

<ul class="breadcrumb">
    <li><a href="/">Home</a></li>
    <li><a href="/level-1">Level 1</a></li>
    <li><a href="/level-2">Level 2</a></li>
    ...
    <li>Current</li>
</ul>

...

</body>
```
{% endcode %}

To style this, we make that unordered list, an _inline_ list, then place a separator using the `::before` pseudoclass:&#x20;

{% code title="style.css" %}
```css

.breadcrumb li {
  display: inline;
}

.breadcrumb li+li::before {
  /* most commonly ">" or "/" to separate the levels */
  content: ">"; 

}
```
{% endcode %}
