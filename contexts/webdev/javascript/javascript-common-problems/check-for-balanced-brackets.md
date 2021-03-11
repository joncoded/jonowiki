# Check for balanced brackets with JavaScript

### Input

* should use only the following characters: `[ ( { } ) ]`

### Output expected

* `true` if the brackets are balanced
* `false` if not

### Stack-based solution

This is one possible solution that makes use of an array-based stack: 

```javascript
function isBalanced(exp) {
// given an expression as an argument
  
  let openings = []
  
  // special cases
  if (exp.length == 0) return true;
  if (exp.length == 1) return false;
  
  // go thorugh the expression
  for (let i=0; i<exp.length; i++) {
    // if current character is an opening bracket, push it to the stack
    if (exp[i] == '{' || exp[i] == '[' || exp[i] == '(') {
      openings.push(exp[i])
    } else {
      // if current character is not an opening bracket...
      // ...check if the character matches the top of the stack
      switch (exp[i]) {
        case ')':
          if (openings[openings.length - 1] === '(')
            openings.pop()
          else 
            return false
          break;
        case ']':
          if (openings[openings.length - 1] === '[')
            openings.pop()
          else 
            return false
          break;
        case '}':
          if (openings[openings.length - 1] === '{')
            openings.pop()
          else 
            return false
          break; 
        // add more bracket cases if necessary 
        default:
          // if the character is not relevant, false
          return false
      }
    }    
  }
  
  // return true if all of the characters are good
  return true;
  
}

console.log(isBalanced('')) // true
console.log(isBalanced('{')) // false
console.log(isBalanced('{}')) // true
console.log(isBalanced('{()}')) // true
console.log(isBalanced('{([)}')) // false
console.log(isBalanced('{([])()}')) // true
console.log(isBalanced('{([{[]}])()}[]')) // true
```

This solution looks clunky but "it works" :P

{% hint style="success" %}
As an exercise, you may "simplify it" 😉
{% endhint %}

