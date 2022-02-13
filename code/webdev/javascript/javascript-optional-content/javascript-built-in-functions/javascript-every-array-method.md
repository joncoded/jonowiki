# JavaScript: every() array method

The `every()` method determines if all elements in an `Array` type meet a specific condition:

```javascript
const myArray = [1, 3, 9, 23, -5]
const yourArray = [2, 3, 4, 5]

// condition
const isPositive = (number) 
    => number > 0

myArray.every(isPositive) 
// false

yourArray.every(isPositive)
// true
```
