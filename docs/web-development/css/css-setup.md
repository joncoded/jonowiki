---
description: 3 ways (and the best way) to add styling to an HTML page
---

# ⚙ CSS setup

How we can add CSS to an HTML page:

### Prerequisites

* Code editor
* HTML file
* Web browser

### Methods of adding CSS

For an HTML-only page, we have three ways to add CSS:

* In-line (`style` attribute within an HTML tag)
* `<style>` tags (anywhere on an HTML page)
* External **style sheets** (outside of the HTML page)

### In-line styles

Although not the best practice (or even a good practice), we can learn how CSS works when we write our HTML, by using the `style` attribute within each HTML tag:

```markup
<html>

    ...
    
    <body>
    
        <h1 style="font-size: 128px">Big Heading!</h1>
        
    </body>

</html>
```

During development, we can use these in-line styles mainly for testing out a specific styling!

### Style tags

We could also use HTML `<style>` tags:

```markup
<html>

    ...
    
    <body>
    
        <style>
        h1 { font-size: 128px }
        </style>
    
        <h1>Big Heading!</h1>
        
    </body>

</html>
```

However, with more styling rules, this can easily become messy and lengthy!

### Style sheets

The "SS" in "CSS" allows us to separate the styling concerns from the HTML file, by placing them into a **style sheet**:

{% code title="style.css" %}
```css
h1 { 
    font-size: 128px
}
```
{% endcode %}

We then reference the above `style.css` file in the HTML page...

* using a special `<link>` tag within the `<head>` tag
  * which itself lives in the `<html>` tag:

{% code title="index.html" %}
```markup
<html>

    <head>
    
        ...
        
        <link rel="stylesheet" href="style.css">
    
    </head>
    
    <body>
    
        <h1>Big Heading!</h1>
        
    </body>

</html>
```
{% endcode %}

Next, we shall learn how to connect those styles in our HTML with [CSS selectors](css-selectors.md)...
