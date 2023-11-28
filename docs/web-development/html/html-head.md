---
description: the metadata (background information) container of a webpage
---

# HTML \<head> and \<meta> tags

The `<head>` part of an HTML document describes the page:&#x20;

* it does not itself directly appear on the page!

```markup
<html>

    <head>
        
        <title>My home page</title>
        <meta name="description" content="Just got started with making a website">
        <meta name="keywords" content="HTML, web development, programming">
        <meta name="author" content="Jon">
    
    </head>
    
    <body>
    
        <p>Where the content actually appears!</p>
    
    </body>
    
</html>
```

The `<head>` may assist:

* search engines list your page
* screen readers (and other [assistive technologies](../accessibility.md))
* other web developers :smile:

### The \<meta> tag

The `<meta>` tag, within the `<head>` tag, each consists of a `name` attribute that describes the HTML document (the webpage):

```xml
...
<head>
  <meta charset="UTF-8">
  <meta name="description" content="My website about anything I like">
  <meta name="keywords" content="programming, management, hacking tips">
  <meta name="author" content="Jon C">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
...
```

In the above example note that:

* `charset` has no `name` attribute but simply describes what "character set" the page is using
  * usually just has a value of `UTF-8` since nowadays that set contains _most_ of the alphabets and writing systems of the world's human languages
* `description` for search engines to show a small blurb under your page's `<title>`
* `keywords` to help the search engine lead users to your page if they type in these keywords
* `author` not as important 😉
* `viewport` has recently become important as it helps adjust the size of everything when viewed on smaller screens such as mobile phones and tablets
