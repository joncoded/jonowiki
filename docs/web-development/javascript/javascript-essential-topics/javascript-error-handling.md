---
description: how to respond to unsatisfactory data (the "interjections")
---

# JavaScript error handling

Scripts "error out" in two different ways:

* The script would continue running but would yield weird output
  * "silently failing"
* The script would stop running and **throw an error**
  * **error handling** at its best

### `Error` object

To address the latter in JavaScript, we could create an error like this with `new Error(msg)`:

```javascript
const everythingOK = false

function showErrorMessage(customErrorMessage) {

  const ourError = new Error(customErrorMessage)
  
  console.log(ourError.message)
  
}

if (everythingOK == false) {
    showErrorMessage("not everything is OK!")
}

console.log("the script goes on...")
```

Note that the `Error` class of objects contains:

* a built-in property called `message`
  * which got instantiated as `customErrorMessage`
    * when `ourError` got instantiated
      * when `showErrorMessage` was called
        * with `customErrorMessage` passed in

However, _creating an error_ does not _throw the error_, which causes the program to stop running!

### `throw` keyword

We would need to do this instead:

```javascript
const everythingOK = false

function showErrorMessage(customErrorMessage) {

  const ourError = new Error(customErrorMessage)

  // throwing instead of just printing the error to console
  console.log(throw(ourError))
  
}

if (everythingOK == false) {
    showErrorMessage("not everything is OK!")
}

// this really won't print if everythingOK isn't true
console.log("this will not print")
```

Using the `throw` keyword stops the program at that point and any further lines of code will not execute!

### `try` and `catch`

One way to attach an error to a piece of code is to use blocks call `try` and `catch` that work in a similar fashion to `if` and `else:`

* `try` would have the code we want to execute properly
* `catch(error)` would contain the error handling
  * this block would also provide us with an `Error` object to work with

```javascript
try {

    // code we want to execute properly
    if (codeOK) {
        // do stuff
    } else {
        throw new Error("not working!")
    }
    
} catch(e) {

    // handle the error if any
    console.log(e)    
    // Error: not working! ...   

}
```

### `finally`

For whatever reason, if we still want to run code after the error gets thrown, we can use a `finally` block like such:

```javascript
try {

    // code we want to execute properly
    if (codeOK) {
        // do stuff
    } else {
        throw new Error("not working!")
    }
    
} catch(e) {

    // handle the error if any
    console.log(e)    
    // Error: not working! ...   

} finally {

    // this will still print regardless
    console.log("keep the party going!")

}
```

Note that the `catch` and `finally` blocks are each optional if the other block exists, so we can have a:

* `try` and `catch`
* `try` and `finally`
* `try` and `catch` and `finally`

However, `try` must exist and it must exist with at least a `catch` or a `finally`!

#### Further reading

{% embed url="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch" %}
