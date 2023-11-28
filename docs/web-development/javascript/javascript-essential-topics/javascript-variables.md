---
description: the storage locations of data (the "words")
---

# JavaScript variables

**Variables** store data for later use (and to make them more compact/portable):

### Statements

JavaScript statements take on a form similar to a mathematical equation (a **variable** gets a **value**)...

...but in a manner similar to an assignment (see the second line):

```javascript
let x = 2 
x = x + 1
// 3
```

In the example above, we do not mean that `x` is equal to `x+1` which makes no sense but that:

> "x will have a value\
> ... of the _last known value_ of x, which is 2,\
> and then added 1,\
> to make 3!"

Another way of looking at this is by thinking of the single `=` sign as an left-facing arrow:

```
x <- 2
x <- x + 1
```

> "let x be 2, then let x be 2 + 1"

#### Semi-colon at the end

In ES6, semi-colons (`;`) [have become optional](https://flaviocopes.com/javascript-automatic-semicolon-insertion/)

* some programmers prefer to continue using them out of habit
* others just want to keep their a little cleaner!

### Declarations

Indeed, we use the reserved keywords `const` and `let` to **declare** what kind of statement that we wish to make:

* `const` is a variable but up until the point we declare it
  * we can change its value at its line of declaration
  * ...but we cannot re-assign it at any other point in the program
* `let` is a variable in its truest form
  * we can change its value after its declaration

```javascript
// we can change "100" here...
const x = 100 

// ...but we cannot change it here
x = 200 

// we can change "100" here...
let y = 100 

// ...and we can change it here because of let
y = 200
```

### Reserved keywords

When we declare variables, we cannot use some **reserved keywords** as variable names, e.g.:

```
let let = 1
```

...won't work because the language won't let us use the second `let` as a variable name!

For a full list of reserved keywords, we have this _w3schools_ page:

{% embed url="https://www.w3schools.com/js/js:reserved.asp" %}

### Keyword `var`

`var` is a variable like `let` but:

* `let` has **block scope**
  * it exists only within the confines of its closest _curly braces_
* `var` has **function scope**
  * it exists within the confines of its `function`

```javascript
function doSomething() {
// function scope for var

    const x = 10

    if (x > 0) {
    // block scope for let
        let z = 100
        z = 200    // we can change it here
        var t = 1
    }

    // "1" (this call exists inside the function scope)
    console.log(t) 
    
    // undefined (this call exists outside the block scope)
    console.log(z) 

}
```
