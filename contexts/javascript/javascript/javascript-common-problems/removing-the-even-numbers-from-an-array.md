# Removing the even (or odd) numbers from an array with JavaScript

### Higher-order function

This solves it nice and neat but obscures "the work":

```javascript
// make some array with all sorts of valid values
let someArray = [1,8,2,-2,4,5,10,6,-7,3,12,0]

// assumptions: each element is an integer number
let removeEven = (anArray) => 
  anArray.filter(element => element % 2 !== 0)

console.log(removeEven(someArray))
// [1, 5, -7, 3]
```

* Replace `element % 2 !== 0` with `element % 2 === 0` to remove odd numbers

### Iterative function

This shows more of "the work" via iteration:

```javascript
let someArray = [1,8,2,-2,4,5,10,6,-7,3,12,0]

function removeEven(anArray) {
  var newArray = []
  for (let number of anArray) {
    if (number % 2 !== 0) {
      newArray.push(number)
    }
  }
  return newArray
}

console.log(removeEven(someArray))
```
