---
description: getting started with JavaScript on a webpage
---

# JavaScript and HTML

We can include Javascript in an HTML page in one of three ways:

### JavaScript inline

One might see JavaScript placed inside HTML tags like this:

```markup
<a href="..." onClick="alert('hey')">Link</a>
```

...where the value of the `onClick` attribute would contain Javascript!

We will see this later in React when HTML takes on the form of something called "JSX" ;)

### JavaScript encapsulated

A more contained form of JavaScript would enter via a `<script>` tag in an HTML file:

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

So, even better, we could place JavaScript in a file like this:

{% code title="app.js" %}
```javascript
const aVariable = true;
```
{% endcode %}

Then, we would load the file by placing an `src` attribute in the `<script>` tag instead:

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

Note two things:

* the _order_ of the `<script>` tags does matter:
  * if `thirdpartycode2` depends on `thirdpartycode1`
    * `thirdpartycode1` should appear higher up in the HTML
* in older HTML, the `<script>` tag might have the optional `type` attribute, which has become optional

### JavaScript deferred

If a `<script>`tag has to appear in the `<head>` tag, we can use the `defer` keyword:

* this ensures that the rest of the HTML file gets loaded _before_ the execution of this head script!

```xml
<html>

    <head>
        ...
        <script src="deferred.js" defer></script>
        ...
    </head>

    <body>

        <!-- all the tags here get loaded before deferred.js takes effect -->

    </body>

</html>
```
