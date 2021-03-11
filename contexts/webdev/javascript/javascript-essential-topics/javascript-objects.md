---
description: collections of properties and values (the "nouns")
---

# JavaScript objects

So far, we have:

* done some stuff with basic data values called [primitives ](javascript-data-primitives.md)
* assigned those primitives to locations called [variables](javascript-variables.md)
* done things to those variables with [operators](javascript-operators.md)
* done even more things to variables with functions

Now, we take it to another level with **objects:**

* which encapsulate data in pairs called **keys** and **values**
  * the key acts as a sign of meaning for the value 
  * the value can be a _primitive_, another _object_ or even a _function_ 

```javascript
const emptyObject = {}

const oneKeyObject = {
    name: "Jon"
}

const complexObject = {
    key1 : "Hello",
    key2 : "Hey", 
    anotherKey : 42, 
    someOtherKey : true, 
    nestedObject : { 
        nestedObjectKey: true
    },
    method: function () {
        return "Surprise!"
    }
}
```

We can gather from the above that:

* the object has keys separated by commas
* keys can have names similar to variables 
  * but with no declaration keywords \(i.e. `const`, `let`,`var`\) 

More abstractly:

```javascript
keyword anObject = {
    aKey1 : aValue1, 
    aKey2 : aValue2,
    ...
}
```

{% hint style="warning" %}
Recall that objects [copy by reference](javascript-data-primitives.md):

* when we copy an object and we change the original...
  * ... we also make the same changes in the copy!
  * ... because variables store _references to the_ object
    * ...and _not the object_ itself 
{% endhint %}



