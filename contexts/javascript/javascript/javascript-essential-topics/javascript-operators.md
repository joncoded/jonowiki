---
description: essential math + logic + beyond (the "conjunctions")
---

# JavaScript operators

**Operators** look at data and try to do something with them:

### Arithmetic operators

The mathematical operations we know from grade school (with slight variations in their _symbols_ to avoid confusion with other symbols, such as `x` , or for easy input - because where in heck is the division symbol (÷) key?):

| Operator symbol | Meaning               |
| --------------- | --------------------- |
| +               | add                   |
| -               | subtract              |
| \*              | multiply              |
| /               | divide                |
| %               | modulo (not percent!) |

#### Examples

```javascript
let v = 1
v = v + 1 // 2

let w = 1
w = w - 1 // 0

let x = 2
x = x * 3 // 6

let y = 2
y = 6 / y // 3

let z = 10
z = z % 8 // 2
```

A popular use of modulo determines whether a number `x` is even (0) or odd (1):

```javascript
let x = 200
console.log(x % 2) // 0 i.e. even

let y = 201
console.log(y % 2) // 1 i.e. odd
```

### Comparison operators

As we advanced from second grade, we came across these concepts:

| Operator symbol | Meaning                        |
| --------------- | ------------------------------ |
| >               | greater than                   |
| >=              | greater than or equal to       |
| <               | less than                      |
| <=              | lesser than or equal to        |
| ==              | equal to                       |
| ===             | equal to or equal type to      |
| !=              | not equal to                   |
| !==             | not equal or not equal type to |
| ?               | ternary (see below)            |

A confusing phenomenon for the beginner in JavaScript, we use:

* `=` to mean "assignment" or "re-assignment"
* `==` to mean "equal value"
* `===` to mean "equal value" and "equal type"

So why `==` and `===` ? Well:

* `==` compares a number like `17` regardless if it is a `Number` or a `String`
* `===` ensures that a number like `17` is a `Number` and not anything else

Also, note the amount of equal symbols in `!=` 😩 and `!==` 😩😩

{% hint style="info" %}
Linguistics has a term for "same symbols used, different meaning conveyed": [**false friends**](javascript-operators.md)\*\*\*\*
{% endhint %}

We see comparison operators used mostly in **branching (decision) statements**

#### **Examples**

```javascript
if (x > 100) {
    // do something if x is greater than 100
} else { 
    if (x <= 50) {
        // do something else if x is less than or equal to 50
    }       
}

// ternary operator
(/* comparison */) ? /* one-liner if true */ : /* one-liner if false */
// e.g.
let y = (x > 100) ? "too much" : "too little"
```

### Logical operators

Later on in school, we had concepts like these:

| Operator symbol | Meaning |
| --------------- | ------- |
| &&              | "and"   |
| \|\|            | "or"    |
| !               | "not"   |

#### Examples

```javascript
if (x > 100 || x < 0) {
    // do something if x is greater than 100 or less than 0
} else { 
    if (x >= 25 && x <= 50) {
        // do something else if x is between 25 and 50
    }   
    if (!(x === 17) {
        // do something else if x is not 17 
    }   
}
```

### Increment/decrement operators

| Operator symbol | Meaning                                   |
| --------------- | ----------------------------------------- |
| ++              | increment the existing value (add 1)      |
| --              | decrement the existing value (subtract 1) |

#### Examples

```javascript
let x = 1
x++ // 2

let y = 1
y-- // 0
```

### Assignment operators

These basically function as shorthand to the aforementioned arithmetic operators:

| Operator symbol | Meaning                          |
| --------------- | -------------------------------- |
| +=              | add to the existing value        |
| -=              | subtract from the existing value |
| \*=             | multiply by the existing value   |
| /=              | divide by the existing value     |

#### Examples

```javascript
let x = 1
x += 2 
// 3, same as writing x = x + 2

let y = 1
y -= 2 
// -1, same as writing y = y - 2

let z = "Hello"
z += " World"
// "Hello World" - possible to use with Strings!
```
