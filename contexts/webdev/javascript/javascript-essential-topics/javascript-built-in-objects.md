---
description: specialized objects (the "jargon sets")
---

# JavaScript built-in objects

Sometimes we need specialized objects to help express what we want to do - a specialized "vocabulary" within the programming language \(a jargon!\) ...

... behold, some examples of **built-in objects**: ****

### Date

JavaScript comes with a built-in `Date` object which tells us the current date but in its standard format

```text
const today = new Date()
// Sat Feb 20 2021 10:00:00 GMT -0500 (Eastern Standard Time)
```

There exist many ways to format this date via other functions \(as well as writing our own\) which we can read in the [Mozilla Developer docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)!

### Math

JavaScript comes with a built-in `Math` object that allows us to do essential mathematical functions without having to rewrite them, e.g.:

```javascript
// this gives us a random decimal between 0 and 1
const randomNumber = Math.random() 

// we can multiply that by 100
const someNumber = 100 * randomNumber()

// this would round up the previous random number
const someInteger = Math.floor(someNumber) 

// this would round down
const someIntegerRoundedDown = Math.ceil(someNumber)
```

We can call other functions of `Math` such as: 

* `Math.sin(x)` to get "the sine of x"
* `Math.sqrt(x)` to get "the square root of x"
* `Math.pow(x, y)` to get "x to the power of y"

We can also use its properties such as:

* `Math.PI` to get an approximation of pi \(`3.14159`\)
* `Math.E` to get an approximation of Euler's constant \(`2.718`\)

#### References

* See [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date) and [Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math) as well as [Global Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/) in the Mozilla Developer Docs

