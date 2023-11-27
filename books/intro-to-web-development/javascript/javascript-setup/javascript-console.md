---
description: how to look at our variables without affecting anything
---

# JavaScript console

In the `console` we can output any processed data without directly affecting the program ... in our `app.js`:

```javascript
const aVariable = "Application ready"
// a piece of text 

console.log(aVariable) 
// outputs "Application ready" 
```

In a browser, we would right-click, then _Inspect_, then go to _Console_ to see the `log` print out `Application ready` ... but this would not change the program in any way:

![](../../../../.gitbook/assets/docs-console-log.png)

Instead, it works as a debugging tool where we can see what happens to our code without directly displaying it on the browser :)

### Another example

In `app.js` once again, we could use `console.log` as a calculator:

```javascript
const aVariable = 2 + 3
// an assignment to a variable

console.log(aVariable) 
// outputs 5
```

...checking a variable made of other variables:

```javascript
const firstNumber = 2     
// this could come from user input
const secondNumber = 3    
// this could come from an external file

const aVariable = firstNumber + secondNumber
// adding the above two together

console.log(aVariable) 
// outputs 5
```

...and then we can see how `console.log` enables us to see outputs of sensitive calculations without showing them on the webpage!

### Related

{% content-ref url="../javascript-optional-content/javascript-console-styling.md" %}
[javascript-console-styling.md](../javascript-optional-content/javascript-console-styling.md)
{% endcontent-ref %}
