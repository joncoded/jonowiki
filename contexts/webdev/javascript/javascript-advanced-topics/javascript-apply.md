# JavaScript apply\(\)

### Structure

`functionFilledObject  
.someFunction  
.apply(toThisObject, [arg1, arg2, ..., argn])`

### Example

Say we have a "function-filled object" and at least one of its properties consists of a desirable function:

```javascript
const phone = {
    name: 'Google Pixel 3',
    hasNotificationsOn: false,
    turnNotificationsOn() {
        this.hasNotificationsOn: true;
        return `Notifications on for ${this.name}`
    }
    ...
}
```

Then we have another object:

```javascript
const anotherPhone = {
    name: 'iPhone',
    hasNotificationsOn: false
}
```

To use the `turnNotificationsOn()` function in the `phone` object for `anotherPhone`, we would need to call a special built-in JavaScript function known as `apply()` , on `phone` , in order to provide the function for `anotherPhone`

As well, `this` inside the desired function would mean any object that appeared as the `toThis` object in the call to `apply()`

```javascript
let result = phone.turnNotificationsOn.apply(anotherPhone)
console.log(result)
// Notifications on for iPhone
```

### Uses

#### Applying a function to an object that does not have it

As shown above!

#### Combining arrays

A special use case for `apply()` can go as follows:

```javascript
let originalArray = [1, 2, 3]
let anotherArray = [4, 5, 6]

originalArray.push.apply(originalArray, anotherArray);

console.log(originalArray);
// [1, 2, 3, 4, 5, 6]
```

Thus, the `thisArg` object in the first parameter could be the same array that calls `apply()`!

