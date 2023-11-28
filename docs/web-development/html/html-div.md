---
description: dividing up a webpage with "container tags" + other names for <div>
---

# HTML \<div> tag

The `<div>` tag, as its name implies, can divide an HTML document into more organized sections as such:

```html
<html>

...

    <body>
    
        <div id="header">
        
            <h1>Welcome to HTMLville</h1>
        
        </div>
        
        <div id="main">
        
            <p>Here you will find resources about our great virtual city!</p>
        
        </div>
        
        <div id="footer">
        
            <p>(c) 202X HTMLville Developers, thanks for visiting!</p>
            
        </div>
        
    </body>

</html> 
```

However, we will see in the following sections that we can do even better than this!

### Semantic HTML

Instead of using `<div>` tags to divide an HTML page up, **semantic HTML** allows us to replace "`div`" with more meaningful names such as:

| **Tag**     | **For**                                                        |
| ----------- | -------------------------------------------------------------- |
| `<header>`  | the top of a page                                              |
| `<nav>`     | ...a menu inside a header                                      |
| `<main>`    | the main content of the page                                   |
| `<section>` | ...a part of the main content                                  |
| `<article>` | ...(think of a blog or a news site that show a list of posts!) |
| `<aside>`   | ...related but "optional" content                              |
| `<figure>`  | ...encapsulating images/charts/diagrams or similar             |
| `<footer>`  | the bottom of a page                                           |

Note that we could use each of those tags to contain any content, but your fellow developers might not enjoy that! The tags above keep markup organized:

```xml
...
<section>
    <article>
        <h2>Blog post for January 2</h2>
        <p>Except for that blog post...</p>
    </article>
    <article>
        <h2>Blog post for January 1</h2>
        <p>Except for that blog post - happy new year!</p>
    </article>
    <aside>
        <p>Don't forget to wish your co-workers a happy holiday!</p>
    </aside>
</section>
...
```

looks a lot more readable than:

```xml
...
<div>
    <div>
        <h2>Blog post for January 2</h2>
        <p>Except for that blog post...</p>
    </div>
    <div>
        <h2>Blog post for January 1</h2>
        <p>Except for that blog post - happy new year!</p>
    </div>
    <div>
        <p>Don't forget to wish your co-workers a happy holiday!</p>
    </div>
</div>
...
```

#### Older tags as semantic HTML

We could see tags such as `<table>` and `<form>` as a pre-cursor to semantic HTML:

* their tags say what they are
* we could use `<div>` tags and JavaScript to re-create their functionality
  * obviously, in good practice, we do not!

#### A note about \<figure> and \<figcaption>

A `<figure>` would contain media (usually an image), while a `<figcaption>` to describe that media:

```xml
<figure>
    <img src="..." alt="">
    <figcaption>A caption for the image, of course!</figcaption>
</figure>
```

These tag names still confuse me (I have worked with HTML for a long time _and_ I also speak English natively) so have patience with them!

