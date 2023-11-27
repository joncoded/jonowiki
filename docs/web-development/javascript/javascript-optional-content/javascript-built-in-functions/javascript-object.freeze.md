---
description: making objects read-only
---

# JavaScript Object.freeze()

Using `freeze()` will ensure that an object and its properties become read-only:

```javascript
const myObject = { myProp1: 2, myProp2: "my value" };
Object.freeze(myObject);

myObject.myProp1 = 3; // myObject and its properties can't change
```

However, if a property contains a (nested) object, then that property can still change:

```javascript
const myObject = { 
    myProp1: 2, 
    myProp2: { 
        myNestedProp: "my value" 
    }
};
Object.freeze(myObject);

myObject.myProp2.myNestedProp = "your value"; // this can change
```
