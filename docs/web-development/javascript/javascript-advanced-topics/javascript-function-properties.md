---
description: looking at the details of a JavaScript function
---

# JavaScript function nuances

### Function's built-in properties

Every function (also an object) has two properties:

* `length` refers to the amount of arguments
  * e.g. `function myFunction(x,y,z)` has a `length` of 3
* `prototype` refers to all the properties and methods that the object can use

### Functions that return multiple values

We can `return` more than one object from a function:

```javascript
function getPlace() {

 // assume these come from an API or some dynamic source
 let country = 'Canada', city = 'Toronto'
 
 // we can return both variables as such:
 return [country, city] 
 
}

let place = getPlace()
console.log(place[1], place[0])
// "Toronto" "Canada"
```

In ES6, we can use **destructuring** as such, to make using this array easier:

```javascript
const [country, city] = getPlace()
console.log(`${city}, ${country}`)
// "Toronto, Canada" 
```

### Functions that do recursion

**Recursive functions** can call themselves:

```javascript
function recursiveFunction() {    
    // assume playSound(file) is defined 
    playSound('ding.wav')
    recursiveFunction()
}

recursiveFunction()
```

We can easily see that this would result in an endless loop - like a dog chasing its tail!

#### Exit conditions of a recursive function

So, to work like a (sane) normal function, a recursive function must have an **exit condition**:

```javascript
function recursiveFunction() {
    // assume minuteNow and secondNow come from a clock
    // assume playSound(file) is defined 
    playSound('ding.wav')
    if (minuteNow > 0 && secondNow > 0) {
        recursiveFunction()
    }    
}    

recursiveFunction()
```

The exit condition in the above is the silent `else` branch which lets the function not call itself again :)
