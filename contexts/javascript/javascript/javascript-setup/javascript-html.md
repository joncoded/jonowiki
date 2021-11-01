---
description: get started with JavaScript on a webpage
---

# JavaScript and HTML

### JavaScript inline

In the early days or in very bad practices, once might see JavaScript placed inside HTML tags like this: 

```markup
<a href="..." onClick="alert('hey')">Link</a>
```

{% hint style="danger" %}
I'd strongly discourage this because it departs from the good practice of _separating concerns_!
{% endhint %}

### JavaScript encapsulated

To begin working with JavaScript, we could start with a plain HTML file like `index.html`:

```markup
<html>
    <head>
        <title>a page</title>
    </head>
    <body>
        <h1>a page</h1>
    </body>
</html>
```

We could add JavaScript like this:

```markup
<html>
    <head>
        <title>a page</title>
    </head>
    <body>
        <h1>a page</h1>
        <script>
            // our script here - this is a basic true/false variable: 
            const aVariable = true
        </script>
    </body>
</html>
```

{% hint style="warning" %}
Yet, this sets us up to use that piece of code in that page and only that page - not very friendly for reuse!
{% endhint %}

### JavaScript from an external file

So, preferably, we could place JavaScript in a file like this:

{% code title="app.js" %}
```javascript
const aVariable = true;
```
{% endcode %}

Then, load the file by placing an `src` attribute in the `<script>` tag instead:

{% code title="index.html" %}
```markup
<html>
    <head>
        <title>a page</title>
    </head>
    <body>
        <h1>a page</h1>
        <script src="app.js"></script>
    </body>
</html>
```
{% endcode %}

This makes for a more modular approach; then, we could even add files from other sources like such:

{% code title="index.html" %}
```markup
<html>
    <head>
        <title>a page</title>
    </head>
    <body>
        <h1>a page</h1>
        <script src="thirdpartycode1/app.js"></script>
        <script src="thirdpartycode2/app.js"></script>
        <script src="app.js"></script>
    </body>
</html>
```
{% endcode %}

With this, we can reuse code more easily and keep the HTML structure clean and clear! 

{% hint style="warning" %}
Note that in the code directly above, the _order_ of the `<script>` tags does matter: if `thirdpartycode2` depends on `thirdpartycode1` then they should appear in the order as listed above!
{% endhint %}

{% hint style="info" %}
In the `<script>` tag, we might see some people add a `type` attribute but this has become optional for JavaScript in most **modern browsers**:

```markup
<script type="text/javascript" src="app.js"></script>
```
{% endhint %}

### JavaScript deferred

{% hint style="warning" %}
If a `<script>`tag has to appear in the `<head>` we can use the `defer` keyword to ensure that the entire HTML file gets loaded _before_ the execution of this head script:

```markup
<head>
    ...
    <script src="deferred.js" defer></script>
    ...
</head>
```
{% endhint %}



