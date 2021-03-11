---
description: surfing through the HTML with JavaScript
---

# JavaScript DOM traversal

We can get the parents and children of each document object with `parentNode` and `children`:

```javascript
let objectsParent = document
    .querySelector('.object')
    .parentNode 
    
let objectsChildren = document
    .querySelector('.object')
    .children 
```

We can also just get the first child of each object with `firstChild`:

```javascript
let objectsFirstborn = document
    .querySelector('.object')
    .firstChild
```



