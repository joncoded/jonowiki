---
description: getting that HTML
---

# JavaScript DOM access

### The `document` object

* In JavaScript we can access the document (global) object simply with the reserved keyword `document`

### The `getElement...` properties

* Then, we can access DOM elements, such as all `<h1>` tags like this:

```javascript
let h1 = document.getElementsByTagName('h1')
```

Note that would grab the _object representation_ and _not the content_ of the `<h1>` tags!

* `getElementById(...)`
  * returns the tag object with an `id` attribute of `...`
* `getElementsByClassName(...)`
  * returns a list of any element(s) with a `class` attribute of `...`
* `getElementsByTagName(...)`
  * returns a list of any element(s) with that tag of `...`
  * e.g. `getElementsByTagName('h1')` for `<h1>` tags
