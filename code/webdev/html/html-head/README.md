---
description: the metadata part of a webpage
---

# HTML \<head>

The `<head>` part of an HTML document describes the page but does not itself directly appear on the page:

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
* screen readers (and other [assistive technologies](../../accessibility.md))
* other web developers :smile:
