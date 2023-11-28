---
description: checking the validity of JavaScript types with a library
---

# 🟦 TypeScript

**TypeScript** extends JavaScript to ensure that a variable's data conforms to a certain form, or "**type"**!

### Why TypeScript?

TypeScript allows for easier debugging and prevents bad data from circulating through an app:

* also, all JavaScript works in TypeScript
* however, TypeScript must transpile into JavaScript to work on the web

### The essence of TypeScript

We use TypeScript to validate variables by assigning each variable in TypeScript a **type**:

```javascript
function myFunction(
    yearRound: boolean, 
    cost: number,
    destination: { name: string }
) {
    ...
}
```

Breaking that down:

* the `yearRound` variable has a primitive type of `boolean`
  * thus, `yearRound` can only be either `true` or `false`
* the `cost` has a type of a `number`
  * (JavaScript has no integers or floats; all numeric data are just `number`s)
  * thus, `cost` cannot have symbols other than digits and legal operators
* the `destination` has the type of an object `{}`
  * this object, in turn, contains a property called `name`
    * the `name` has a type of `string`

Abstracting that further:

```javascript
function myFunction(
    propertyX: type,
    ...
) {
    ...
}
```

* `type` can take on any of the following (with a few more others):
  * `string`
  * `number`
  * `boolean`
  * `Date`
  * `unknown`
  * `void`
  * `never`
* the `type` can also be _arrays_ of each of the above, e.g.
  * `string[]`
  * `number[]`
* as shown in the earlier top snippet, the `type` can also be an _object_
  * the properties in that object would also get their own `type`s
