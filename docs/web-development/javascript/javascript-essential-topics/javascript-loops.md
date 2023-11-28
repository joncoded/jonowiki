---
description: making things happen again and again
---

# JavaScript loops

**Loops** allow us to perform the same functions over and over again - in JavaScript (and in programming in general) we have two main types of loops:

* **for loops** - do something for a certain amount of times
* **while loops** - do something until something else happens

### Why loops?

We use loops primarily because we want to **iterate**, or go through, something, such as a list or an array of items, e.g.:

```javascript
const myArray = ["Miami", "Roatán", "Placencia", "Cozumel", "Nassau"]
```

If we wanted to print each item in `myArray` then we _could_ do this:

```javascript
console.log(myArray[0]) // Miami
console.log(myArray[1]) // Roatán
console.log(myArray[2]) // Placencia
console.log(myArray[3]) // Cozumel
console.log(myArray[4]) // Nassau
```

However, that defeats the purpose of programming! We would rather just type the names inside each `console.log()`! What if we had 100 items in that list?

So, instead, we use loops! The general idea, or **pseudocode**:

```plaintext
- console.log myArray[i] (where i is the index)
- do this until myArray has no items left (and increment i)
```

### For loop

We use this loop to iterate (go) through a finite array of items:

#### General structure

```javascript
for (let counter = start; counter < numberOfItems; counter++) {
    // do something here
}
```

#### Specific example

```javascript
const myPlaces = ["Miami", "Roatán", "Placencia", "Cozumel", "Nassau"]

for (let i = 0; i < myPlaces.length; i++) {
    console.log(myPlaces[i])
}
```

Breaking it down:

* `let i = 0` initializes the counter (**index**) variable
* all arrays come with a `length` property
* JavaScript arrays have a quirk where the first item has an index of `0`
  * thus `Miami` would be `myPlaces[0]` followed by `Roatán` for `myPlaces[1]`
* `i < myPlaces.length` thus means stop the loop after `i` is one less than the # of items in `myPlaces`
* `i++` increments `i` by 1 after each turn of the loop
* `console.log(myPlaces[i])` thus runs `myPlaces.length` times (in this case, 5 times)

We would also use the `for` loop if we know the number of times that the loop will run!

As we know by now, JavaScript is quite flexible and you can experiment with what operators and numbers (including negative ones):

```javascript
const myPlaces = ["Miami", "Roatán", "Placencia", "Cozumel", "Nassau"]

for (let i = myPlaces.length - 1; i >= 0; i--) {
    console.log(myPlaces[i])
}
```

Here we will print the list in reverse by:

* initializing the counter variable as one less than the array's length (i.e. 4)
* letting the loop increment by -1
* letting the loop run until the index becomes 0

It will thus print `myPlaces[4]` (Nassau), `myPlaces[3]` (Cozumel) all the way to `myPlaces[0]` (Miami)!

### For ... in ... loop

We use the "for-in" loop to iterate through an object's keys:

#### General structure

```javascript
for (let key in someObject) {
    // do something with someObject[key]
}
```

#### Specific example

```javascript
const myObject = { 
    firstName: "Jon", 
    lastName: "Coded", 
    age: 100 
}

for (let key in myObject) {
    console.log(key + ": " + myObject[key])
}

/* Output: 
firstName: Jon 
lastName: Coded
age: 100
```

Breaking it down:

* we let `key` (the first variable) represent each property name of `myObject`
* then we use `in` to reference `myObject`
* within the loop we access each key's value with `myObject[key]`
* `key` could be any legal JavaScript variable name

### For ... of ... loop

We use the "for-of" loop to iterate through an **iterable**'s values:

#### General structure

```javascript
for (const item of items) {
    // do something with each item
}
```

{% hint style="info" %}
In the above, we could replace `const` with either `let` or `var`
{% endhint %}

#### Specific example

```javascript
// most common iterables are arrays and strings
const myIterable = ['a', 'b', 'c']

for (const item of myIterable) {
    console.log(item)
}

/* Output:
a
b
c
*/

const yourIterable = 'zyxwvuts'
for (const item of yourIterable) {
    console.log(item)
}

/* Output:
z
y
x
w
v
u
t
s
*/

const theirIterable = [1, 2, 3]
for (let item of theirIterable) {
    item++
    console.log(item)
{

/* Output:
2
3
4
*/
```

Breaking it down:

* the variable `item` could exist as a `const` or a `let` or even a `var`
  * in the last example above we used a `let` because we wished to change each item before doing a `console.log` on it
* the iterable can contain either an array, string or some list-like collection
  * each data type will have its own way through which the loop will iterate

### while loop

We use the `while` loop if we want to stop a loop when a certain condition is no longer true:

#### General structure

```javascript
let counter = 0
while (counter < someAmount) {
    // do something 
    ...
    // let the counter increment
    counter++
}

// appreciate the final outcome after the loop
```

#### Specific example

```javascript
let i = 0

while (i < 3) {
    i++
} 

console.log(i)
// output: 3
```

### do ... while loop

We use the `while` loop if we wish to run a loop at least once:

#### General structure

```javascript
let counter = 0

do {

    // increment the counter first
    counter++ 

    // do something 
    
} while (counter < someNumber)

// appreciate the result
```

#### Specific example

```javascript
let i = 0

do {
    i = i + 1
    console.log(i)
} while (i < 5)

/* output:
1
2
3
4
5
```
