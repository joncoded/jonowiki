---
description: organized and re-usable code (the "set phrases")
---

# JavaScript modules

Organizing JavaScript code into reusable modules allows for:

* **namespace cleanliness**: variable names do not get reused and cause confusion
  * instead of calling doStuff, you would call moduleX.doStuff and ensure that moduleX is unique to the program
* **functional focus:** have one piece of code do one thing and one thing well!
  * this also makes the code more portable and shareable
  * we don't even have to know how they work internally
    * we just care that they do what we want them to do

{% hint style="info" %}
These ways require ES6 (i.e. use Babel if required) and assume that the **imported module** lives in the same folder as the **importing module**
{% endhint %}

### Newer way of doing modules (used in React)

{% code title="moduleToExport.js" %}
```javascript
const moduleToExport = { 
    property1: "hi",
    property2: function() { return true },
    property3: function() { return "hi" }
}

// attention to this
export default moduleToExport
```
{% endcode %}

{% code title="moduleThatImports.js" %}
```javascript
// attention to this
import ImportedModule from ('./moduleToExport.js')

console.log(ImportedModule.property3)
```
{% endcode %}

### Older way of doing modules

{% code title="moduleToExport.js" %}
```javascript
const moduleToExport = { 
    property1: "hi",
    property2: function() { return true },
    property3: function() { return "hi" }
}

// attention to this
module.exports = moduleToExport
```
{% endcode %}

{% code title="moduleThatImports.js" %}
```javascript
// attention to this
const ImportedModule = require('./moduleToExport.js')

console.log(ImportedModule.property3)
```
{% endcode %}
