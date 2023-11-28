---
description: how does this language work?
---

# JavaScript: how it works

{% hint style="info" %}
Before going through the following, [this article](https://medium.com/@misbahulalam/uncover-the-javascript-engine-vs-runtime-6556ef449634) covers&#x20;

* the **JavaScript Engine**
  * the interpreter that compiles JS code into machine language
* the **JavaScript Runtime**
  * the JS Engine user and provider of additional functionalities
{% endhint %}

Let's try to understand how JavaScript works with the help of some very nicely written articles from [JavaScript Tutorial](https://www.javascripttutorial.net):

### Execution context

{% embed url="https://www.javascripttutorial.net/javascript-execution-context/" %}

What actually happens when we declare variables and functions, as well as call them?

When we declare a variable as such:

```
let x = 10
```

...the "JavaScript engine" uses an **execution context** made up of two phases in order to:

* declare the existence of the variable `x` (the **creation phase**)
  * so this variable actually begins with a value of `undefined`
  * setup a space in memory (the **memory heap**) to store this variable
* finally assign `x` a value (in this case, `10` ) (the **execution phase)**

(...the article also explains a smaller-scale version of execution contexts within [local scopes](javascript-how-it-works.md#local-lexical-scoping))

### Call stack

When we have a lot of **execution contexts,** leap-frogging from here to there and everywhere, what gets called first? Well, the JavaScript engine uses the **call stack** to ensure priority:

{% embed url="https://www.javascripttutorial.net/javascript-call-stack/" %}

* When we create a new **local execution context**, we add ("push") it to the call stack
* When we add another context on top of that, we stack that on top of the call stack
* When we finish with the latest context, we remove ("pop") it from the call stack
* The last context on the stack gets popped off first, until all contexts get popped off
  * "Last in, first out" (LIFO)

### Event loop

If everything is all so LIFO in the call stack, then JavaScript can do only one thing at a time! So, how do we get it to _multi-task_? Some functions might take a _very long_ _time_ to execute (think of a file download) and this can cause **blockage**!  _Just_ how do we make things more _efficient_?

{% embed url="https://www.javascripttutorial.net/javascript-event-loop/" %}

By using special functions called **callback functions**, we can&#x20;

* let the web browser make use of other components (e.g. the **Web API** and **callback queue**)&#x20;
* allow some "slower" functions to by-pass the call stack of the JavaScript runtime!

![](../../../../.gitbook/assets/docs-dom.png)

### Hoisting

When we declare global variables, all variables act as though they appeared (**hoisted**) at the top of the code:

{% embed url="https://www.javascripttutorial.net/javascript-hoisting/" %}

Functions then get hoisted _above_ the variables, so the code behaves in a rearranged fashion as such:

* function declarations
* variable declarations
* function calls

### Scoping

So, where does a variable live?

{% embed url="https://www.javascripttutorial.net/javascript-variable-scope/" %}

#### Global scope‌

* A variable not inside any `function` exists in the global scope
  * We can access this variable from anywhere in the script
* On a browser, this scope is the entire browser `window`

#### Local (lexical) scoping‌

* A variable inside a `function` will exist only inside its curly braces
  * We cannot use this variable from outside of the braces!
  * We can only take its value outside if
    * something in the global scope calls the function
    * the function includes the value in its `return` statement
* **Block scoping** occurs when
  * We[ declare a variable ](../javascript-essential-topics/javascript-variables.md#declarations)with the `let` keyword inside curly braces
    * this includes `if` blocks

#### Global scoping versus local scoping

If a variable appears in the global scope and then appears in a local scope, then what happens?

```javascript
let x = 2

function k() {
  let x = 1
  return x
}

console.log(k()) // 1 (local scope)
console.log(x)  // 2 (global scope)
```

* We would expect the first `console.log` to return `1`
  * the `return x` there refers to the x inside the local scope of `k()`
    * the value of `x` inside the brackets!
* We would then expect the second `console.log` to return `2`
  * the console has no idea that the `x` inside of `k()` exists
  * it has no memory of the first log
    * only the global `x` exists!

So, as soon as another `x` gets declared inside a local scope, a variable such as `x` takes on a new context!

#### "Memory leaks"

As discussed in the article, weird stuff happens when we assign a value to a variable that we never declared (or "[declare without a keyword](../javascript-essential-topics/javascript-variables.md#declarations)"):

```javascript
function getCounter() {
    counter = 10
    return counter
}

console.log(getCounter()); // outputs 10
```

In this case, the JavaScript engine:

* looks for the `counter` variable in the _local scope_
  * finds none
* looks for the `counter` variable in the _global scope_
  * finds none
* creates a `counter` variable in the _global scope_ (!!!)

In order to avoid this "weird problem" of memory leaks into the global scope, we would append this even weirder **string literal** at the top of the code, called `use strict`:

```javascript
'use strict'

function getCounter() {
    counter = 10
    return counter
}

console.log(getCounter()); // outputs a ReferenceError
```

### Closuring

Now, another weird thing:

{% embed url="https://spin.atomicobject.com/2014/10/20/javascript-scope-closures/" %}

A function has a **closure** when it can access a variable outside of its scope - in this example, `cat` is available via `this` in `printInfo`:

```javascript
const cat = {
 
   name: "Gus",
   color: "gray",
   age: 15,
   
   printInfo: function() {
      
      console.log("Name:", this.name, "Color:", this.color, "Age:", this.age) 
      // line 1, prints correctly - "this" refers to cat
   
      nestedFunction = function() {
          console.log("Name:", this.name, "Color:", this.color, "Age:", this.age)
          // line 2, loses cat's "this" scope and refers to the global scope
      }
   
      nestedFunction()
   }
   
}

cat.printInfo() // prints Name: window Color: undefined Age: undefined
```

Yet, a nested function within a parent function won't have access to the variables accessible by the parent function! Instead, _the nested function gets bound to the **global scope**_ (!!)

The article then explains a way to mitigate by using a **helper variable**:

```javascript
const cat = {
 
  name: "Gus",
  color: "gray",
  age: 15,
  
  printInfo: function() {
  
    // helper variable
    const that = this;
    
    console.log("Name:", this.name, "Color:", this.color, "Age:", this.age) 
    // line 1, prints correctly - "this" refers to cat
    
    nestedFunction = function() {
      console.log("Name:", that.name, "Color:", that.color, "Age:", that.age)
      // line 2, loses cat's "this" scope but we can use "that"
    }

    nestedFunction()
    
  }
  
}

cat.printInfo() // prints Name: window Color: undefined Age: undefined
```

### apply(), bind() and call()

Of course, the article also lets us know the existence of three other built-in JavaScript functions: `call()`, `apply()` and `bind()` that make the code a little cleaner!

```javascript
const cat = {

   name: "Gus",
   color: "gray",
   age: 15,
 
   printInfo: function() {
   
      console.log("Name:", this.name, "Color:", this.color, "Age:", this.age)
      
      nestedFunction = function() {
         console.log("Name:", this.name, "Color:", this.color, "Age:", this.age)
      }
      
      // instead of just nestedFunction()
      nestedFunction.call(this) // instead of just "nestedFunction();"
      nestedFunction.apply(this) // instead of just "nestedFunction();"
      const storedFunction = nestedFunction.bind(this)

      // allows storage and manipulation of this
      storedFunction()
      
   }
   
}

cat.printInfo() // prints "Name:" "Gus" "Color:" "gray" "Age:" 15 (3 times)
```

So, in the above, `call()`, `apply()` and `bind()` all do the same thing and print out the same result but:

* `apply(thisArg, [var1, var2, ..., varn])`
  * can take on more variables within an array as the second argument
  * `n` is however many arguments the function
* `bind(thisArg, var1, var2, ..., varn)`
  * can take on multiple variables _in multiple arguments_
  * allows the changing of what `this` references
  * allows storage in another variable for use
* `call(thisArg, var1, var2, ..., varn)`
  * takes on multiple variables _in multiple arguments_
  * basically `calledFunction()` becomes `calledFunction.call(this)` with the `this`

In all three functions, the first argument consists of what `this` means, while the other arguments map onto the parametric signature for the nested function!

Let's look at this example for clarity:

```javascript
const data = {
    name: 'Elbonia', 
    cases: 112,
    recoveries: 34,
    deaths: 0
}

function showStatistics(stat1, stat2, stat3) {
    return `${this.name} has 
    ${this[stat1]} ${stat1}, ${this[stat2]} ${stat2} and ${this[stat3]} ${stat3}`
}

let result = showStatistics.apply(data, ['cases', 'recoveries', 'deaths'])
console.log(result) 
/* 
expected output: 
"Elbonia has 
112 cases, 34 recoveries and 0 deaths" 
*/
```

Such a paradigm allows us to create functions in more abstract ways for more robust code re-use!

#### Further reading

{% embed url="https://www.javascripttutorial.net/javascript-apply-method/" %}

{% embed url="https://www.javascripttutorial.net/javascript-bind/" %}

{% embed url="https://www.javascripttutorial.net/javascript-call/" %}

### Conclusion

So those concepts form some of the nuances of how JavaScript works behind the browser window!
