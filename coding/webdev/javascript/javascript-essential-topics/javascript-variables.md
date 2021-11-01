---
description: the storage locations of data (the "words")
---

# JavaScript variables

**Variables** store data: 

### Statements

JavaScript statements take on a form similar to a mathematical equation \(a **variable** gets a **value**\)... 

...but in a manner similar to an assignment \(see the second line\):

```javascript
let x = 2 
x = x + 1
// 3
```

In the example above, we do not mean that `x` is equal to `x+1` which makes no sense but that:

> "x will have a value   
> ... of the _last known value_ of x, which is 2,   
> and then added 1,   
> to make 3!"

Another way of looking at this is by thinking of the single `=` sign as an left-facing arrow:

```text
x <- 2
x <- x + 1
```

> "let x be 2, then let x be 2 + 1"

#### Semi-colon at the end

{% hint style="info" %}
In ES6, the semi-colon \(`;`\) [has become optional](https://flaviocopes.com/javascript-automatic-semicolon-insertion/) but some programmers prefer to continue using it out of habit and/or clarity of code \(I prefer not to!\)
{% endhint %}

### Declarations

Indeed, we use the reserved keywords `var` ,`const` and `let` to **declare** what kind of statement that we wish to make:

* `const` is a variable but up until the point we declare it
  * we can change its value at its line of declaration
  * ...but we cannot re-assign it at any other point in the program
* `let` is a variable in its truest form
  * we can change its value after its declaration
* `var` is a variable like `let` but: 
  * `let` has **block scope**
    * it exists only within the confines of its closest _curly braces_
  * `var` has **function scope** 
    * it exists within the confines of its `function`
* declaring a variable _without a keyword_ and _without_ `use strict` 
  * makes it a _global variable_ in JavaScript!

```javascript
const x = 100 // change it here 
x = 200 // but we can't do this

let y = 100 // change it here
y = 200 // and we can do this

function doSomething() {
// function scope for var

    if (x > 0) {
    // block scope for let
        let z = 100
        z = 200    // we can change it here
        var t = 1
    }
    
    console.log(z) // undefined error as z is outside scope
    console.log(t) // 1 as var is still in function scope
    
    w = 1000 // note: no keyword declaration

}

doSomething()
console.log(w) 
// 1000 because it got declared as a global variable
// undefined error if using `use strict` on top of file
```

### Reserved keywords

When we declare variables, we cannot use some **reserved keywords** as variable names, e.g.:

```text
let let = 1
```

...won't work because the language won't let us use the second `let` as a variable name!

A full list of reserved keywords: 

{% embed url="https://www.w3schools.com/js/js\_reserved.asp" %}

