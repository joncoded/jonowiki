---
description: what objects listen to and how they respond (the "conversations")
---

# JavaScript event handling

### Event handling with the DOM

These can happen in one of two ways:

* **user interaction** through a keyboard, mouse or some input mechanism
  * including `touch` or `swipe` in the case of a finger on a tablet screen
* changes in the browser 
  * e.g. the website does a `load`  or the `window` experiences a `resize`

### Using `on...` events

Each `querySelector` has properties commonly called **listeners** that 

* **detect** \(listen to\) any **events,** such as:
  * a mouse-click \(`click`\)
  * a change in browser window size \(`resize`\) 
  * a page load \(`load`\)
* in order to **handle** \(respond to\) them 

We would essentially assign an **event handler function** that will happen when an **event triggers:** 

```javascript
let element = document.querySelector('button')

function turnButtonGreen() {
    element.style.backgroundColor = 'green'
    element.style.color = 'white'
}

// event listener <- event handler
document.querySelector('button').onclick = turnButtonGreen;
```

Generalizing the last line above: 

```javascript
// event listener <- event handler
element.onevent = eventHandlerFunction
```

### Using `addEventListener`

Another way of writing the **event handler** uses the `addEventListener(eventType, callback)` format**:** 

```javascript
let eventTarget = document.getElementbyId('targetElement')

let eventType = 'click'
let eventHandler = function() {
    // the thing(s) that happen(s) when #targetElement gets clicked
    // we can even use this as a "handler of handlers"
    // by calling several functions in here
}

eventTarget.addEventListener(eventType, eventHandler)
```

{% hint style="info" %}
For anyone who has used jQuery \(a JavaScript-simplifier library\): 

* `$(element)` replaces`eventTarget`
* `on` replaces `addEventListener`

...and suddenly the syntax looks very familiar :\)
{% endhint %}

### Using `removeEventListener`

Instead of `addEventListener` removing an event listener is simply `removeEventListener`

```text
eventTarget.removeEventListener(eventType, eventHandler) 
```

### Listing the eventTypes

There exist events for the _window_, the _mouse_, the _keyboard_ and as well as many input and output devices listed on the following page:

{% embed url="https://javascript.info/event-details" %}

{% hint style="success" %}
So, JavaScript can pick up on things like:

* a browser window resizing
* a mouse wheel rolling
* a key press of a specific key or "any key"
* a swipe on a mobile screen
{% endhint %}

