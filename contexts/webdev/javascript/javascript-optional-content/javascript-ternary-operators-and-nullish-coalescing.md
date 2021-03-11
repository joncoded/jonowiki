---
description: optional shorthand ways of writing some if/else statements
---

# JavaScript: ternary operators and nullish coalescing

### Introduction

As a beginner, you might write something like this:  

```javascript
function calculatePrice(price, taxes, desc) {

  // using if statements
  
  if (taxes >= 0) {
    taxes = taxes
  } else {
    taxes = 0.05
  }
  
  if (desc || desc == "") {
    desc = desc
  } else {
    desc = "default item"
  }
  
  const total = price * (1 + taxes)
  console.log(`${desc} with tax: $${total}`)
  
}

calculatePrice(100, 0.07, "Item A")
calculatePrice(100, 0, "Item B")
calculatePrice(100, undefined, undefined)

/* output: 
"Item A with tax: $107"
"Item B with tax: $100" 
"Default item with tax: $105"
```

### Ternary operators

To avoid `if { // one liner } else { // one liner }` structures, we can use the **ternary  operator** to put this branching structure in one line, thereby reducing the number of lines of code: 

```javascript
function calculatePrice(price, taxes, desc) {

  // using ternary operators
  
  taxes = (taxes >= 0) ? taxes : 0.05
  desc = (desc || desc == "") ? desc : "Default item"
  
  const total = price * (1 + taxes)
  console.log(`${desc} with tax: $${total}`)
  
}

calculatePrice(100, 0.07, "Item A")
calculatePrice(100, 0, "Item B")
calculatePrice(100, undefined, undefined)

/* output: 
"Item A with tax: $107"
"Item B with tax: $100" 
"Default item with tax: $105"
```

### Nullish coalescing \(??\)

Even better than ternary operators, we have the **nullish coalescing** operator which looks like this, when taking the above example:

```javascript
function calculatePrice(price, taxes, desc) {

  // using nullish coalescing
  
  taxes = taxes ?? 0.05
  desc = desc ?? "default item"
  
  const total = price * (1 + taxes)
    console.log(`${desc} with tax: $${total}`)
  
}

calculatePrice(100, 0.07, "Item A")
calculatePrice(100, 0, "Item B")
calculatePrice(100, undefined, undefined)

/* output: 
"Item A with tax: $107"
"Item B with tax: $100" 
"Default item with tax: $105"
```

{% hint style="danger" %}
**Nullish coalescing** [may not work](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing_operator#browser_compatibility) in some browsers such as Internet Explorer, but **ternary operators** have [greater compatibility](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator#browser_compatibility)
{% endhint %}

Example inspired by this video: 

{% embed url="https://www.youtube.com/watch?v=v2tJ3nzXh8I&t=45s" %}



