---
description: the decision makers (the "case" makers)
---

# JavaScript branches

**Branches** make decisions with data based on cases:

### `if`

Accounting for a situation:

```javascript
if (x == true) {
    // if x is true, do something
}

// if it isn't, do nothing
```

### `if/else`

Accounting for an either-or situation:

```javascript
if (x == true) {
    // if x is true, do something
} else {
    // or else, do something else
}
```

### `if/elseif/else`

Accounting for a non-binary situation:

```javascript
if (x > 100) {
    // if x is above 100, do something
} else if (x > 50) {
    // if x is between 50-100, do something else
} else {
    // otherwise, do something completely different
}
```

### `switch`

A more aesthetically-pleasing "synonym" of the `if/elseif/else` structure:

```javascript
switch (x) {
    case (x > 100):
        // do something
        break;
    case (x > 50):
        // do something else
        break;
    default:
        // do something completely different
}
```

Compare the keywords from the `if/elseif/else` and the `switch`
