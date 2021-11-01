# CSS setup

### Prerequisites

* Code editor
* HTML file
* Web browser

When using only HTML, we can use CSS in three ways:

* In-line
* Style tags
* Style sheets

### In-line styles

Although not the best practice \(or even a good practice\), we can begin using CSS when we write our HTML, by using the `style` attribute within each HTML tag:

```markup
<html>

    ...
    
    <body>
    
        <h1 style="font-size: 128px">Big Heading!</h1>
        
    </body>

</html>
```

During development, we can use these in-line styles mainly for testing something out - or if we get really desperate!

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

However, this can get messy easily so...

### Style sheets

The "SS" in "CSS" allows us to separate the styling concerns from the HTML file altogether - permitting us to focus on these details in another file: 

{% code title="style.css" %}
```css
h1 { 
    font-size: 128px
}
```
{% endcode %}

We then include that `style.css` file in the HTML using a special `<link>` tag within `<head>`: 

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

Next, we should learn how to connect those styles in our HTML with [CSS selectors](css-selectors.md):

