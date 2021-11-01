---
description: making changes to the HTML with JavaScript
---

# JavaScript DOM manipulation

### Manipulating text

#### \(innerHTML\)

Finally, now for some interesting stuff: we can use the `innerHTML` property to manipulate the content of each DOM object, for example:

{% code title="index.html" %}
```markup
<html>
    <head>
        ...
        <script src="index.js"></script>
    </head>
    <body>
        <div id="app">hey</div>
        <div id="bar">x</div>        
    </body>
</html>
```
{% endcode %}

{% code title="index.js" %}
```text
document.body.innerHTML = "hi"
```
{% endcode %}

If we load up `index.html` the entire webpage will show just:

```text
hi
```

...as we have just replaced the entire document's body to consist of only that string!

### Manipulating objects

#### \(getElementById\)

Now that we know how to manipulate the document's body, we should know how to manipulate its objects:

{% code title="index.js" %}
```javascript
document.getElementById('app').innerHTML = "hey hey! ho ho!"
```
{% endcode %}

Loading up `index.html` the webpage will display:

```text
hey hey! ho ho!
x
```

Note that it will replace only the first `<div>` because we specified to get the `<div>` with the `id` of `app` and not `bar` 

### Creating and appending objects 

#### \(appendChild and createElement\)

We can: 

* create elements with the `document.createElement` function
* append them using the `document.body.appendChild` function

...and we can chain them as such: 

{% code title="index.js" %}
```text
document.body.appendChild(document.createElement('p'))
```
{% endcode %}

### Selecting and removing objects 

#### \(querySelector and removeChild\)

Likewise, we can:

* point to an element with `document.querySelector`
  * `querySelector` takes one String parameter that resembles the notation of the CSS selector, e.g. `.my-class` , `#anId`, `section.section-blue`
* delete objects from the DOM using `document.body.removeChild`

{% code title="index.js" %}
```javascript
const blueSection = document.querySelector('section.section-blue')
document.body.removeChild(blueSection)
```
{% endcode %}

