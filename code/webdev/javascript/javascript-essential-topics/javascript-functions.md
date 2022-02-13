---
description: grouping code into actionable chunks (the "verbs")
---

# JavaScript functions

**Functions** organize a bunch of statements into chunks:

```javascript
function doStuff(passedInVariable1, passedInVariable2, ...) {

    let task1 = passedInVariable1
    let task2 = passedInVariable2
    
    const addendum1 = 'and then go to sleep'
    const addendum2 = 'and then go to work'
    
    task1 += ' ' + addendum1
    task2 += ' ' + addendum2
    
    return task1 + ', then later: ' + task2
    
}
```

We can then call them and call them again without having to re-write all the code in the function:

```javascript
console.log(doStuff('eat dinner', 'eat breakfast'))
/* 
eat dinner and then go to sleep, 
then later: eat breakfast and go to work
*/

console.log(doStuff('take a bath', 'skip breakfast'))
/*
take a bath and then go to sleep, 
then later: skip breakfast and go to work
*/
```

Functions thereby allow for **code re-use!**

### The `return` keyword

Inside the aforementioned function `doStuff` we see this new `return` keyword which simply means this:

* When we make a call to `doStuff` the call becomes the `return` value

It would help us to understand this if we put the function call into a variable:

```javascript
const regime = doStuff('eat dinner', 'eat breakfast')
console.log(regime)
/* 
eat dinner and then go to sleep, 
then later: eat breakfast and go to work
*/
```

{% hint style="info" %}
A function does not need a `return` keyword but try to avoid that practice!
{% endhint %}

### Function as an object

```javascript
// ES6+ shorthand ("fat arrow notation")

const doStuff = (task1, task2) => {
    // function content
}

// or without shorthand

const doStuff2 = function(task1, task2) => {
    // function content
}

// or (older way)

const doStuff3 = function(task1, task2) {
    // function content
}
```

### Function as a property of an object

**Methods** are functions that are properties of an object:

```javascript
const myObject = {
    someKey: "someValue",
    doStuff: function() {
        // function content - no declaration keyword required
    }
}
```

We will look objects in more detail [soon](javascript-objects.md)!
