---
description: the building blocks of web apps
---

# JavaScript data (primitives)

We can categorize basic forms of **data,** known as **primitives,** as follows:

* `Number` : a value we can **calculate** with another, e.g.
  * an integer like `3`, `-1` or `0`
  * a floating point number like `-273.15`
* `String` : a string of **alphanumeric characters**
  * plain text like `String` or `Hello world!`
  * plain text that has non-calculatable numbers like `Price: $200`
* `Boolean` : a value that is either **true or false**
* `null` : an empty value
* `undefined` : a variable with nothing assigned (not even `null`)
* `Object` : a value with a special structure that organizes a set of properties and their values for a group of similar things
* `Symbol` : (beyond the scope of this introduction)

### Example of `null` and `undefined`

```javascript
let x = null
let y

console.log(x) 
// null

console.log(y) 
// undefined
```

Note that `0` does not mean the same thing as `null` in JavaScript:

* `0` represents a number with which we can do calculations
* `null` represents the intentional absence of a number
* `undefined` represents that we have not yet decided on a value or a `null`

### `typeof` keyword

To see what the type of value a variable has, we use `typeof` before a variable or value:

```javascript
let x = 3.1415;
console.log(typeof x)
// "number"
```

### Copying by value

When we **copy** some primitives, we **copy by value**_:_

```javascript
let x = 20
let y = x
y = 40
console.log(x)
// 20
```

Note that despite setting `y` equal to `x`, then changing `y`'s value - the value of `x` _does not change_!

This happens with:

* a `Number`
* a `String`
* a `Boolean`
* a `null`
* an `undefined`
* a `Symbol`

{% hint style="info" %}
An analogy of **copying by value:** copying an image from the internet and then modifying the copy in an image editing software; the _original_ image does not change!
{% endhint %}

### Copying by reference

However, with:

* an `Object`
* a `function`
* an `Array`

...we **copy by reference**:

```javascript
let object1 = { 
    prop1: 100, 
    prop2: 'ax', 
    prop3: true 
}

let object2 = object1
object2.prop1 = 400

console.log(object1.prop1)
// 400
```

Notice how changing `object2`'s property also changed `object1`'s property automatically!

{% hint style="info" %}
An analogy of **copying by reference**: editing a post on social media (our edit results in changing the original for all to see, as we change the original data!)
{% endhint %}
