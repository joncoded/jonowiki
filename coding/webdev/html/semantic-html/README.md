---
description: more meaningful way to "say" <div>
---

# Semantic HTML

Instead of using `<div>` tags to divide an HTML page up, **semantic HTML** allows us to replace "`div`" with more meaningful names such as:

| Tag                                                                                                                                                                                                            | For                                                            |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| `<header>`                                                                                                                                                                                                     | the top of a page                                              |
| `<nav>`                                                                                                                                                                                                        | ...a menu inside a header                                      |
| `<main>`                                                                                                                                                                                                       | the main content of the page                                   |
| `<section>`                                                                                                                                                                                                    | ...a part of the main content                                  |
| `<article>`                                                                                                                                                                                                    | ...(think of a blog or a news site that show a list of posts!) |
| `<aside>`                                                                                                                                                                                                      | ...related but "optional" content                              |
| `<span>`                                                                                                                                                                                                       | ...differentiating content on the same line as the rest        |
| ``[`<figure>`](html-less-than-figure-greater-than.md)``                                                                                                                                                        | ...encapsulating images/charts/diagrams or similar             |
| `<embed src="...">`                                                                                                                                                                                            | ...animated GIFs (by convention, formerly for videos)          |
| <p><code>&#x3C;audio controls></code></p><p>  <code>&#x3C;source src="..."></code></p><p>  <code>(Browser does not support audio element)</code></p><p><code>&#x3C;/audio></code></p>                          | ...a sound file                                                |
| <p><code>&#x3C;video width="..." height="..." controls></code></p><p>  <code>&#x3C;source src="..."></code></p><p>  <code>(Browser does not support video element)</code></p><p><code>&#x3C;/video></code></p> | ...a video file                                                |
| `<footer>`                                                                                                                                                                                                     | the bottom of a page                                           |

Most of these tags could simply exist as `<div>` tags ... and the HTML would work the same way:

```markup
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

... could look like ...

```markup
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

... but changing `<div>` to something like `<figure>` or `<footer>` gives developers a little more clarity as to the tag's role without excessive commenting!

### Older tags as semantic HTML

Some tags such as `<table>` and `<form>` could be seen as a pre-cursor to semantic HTML:

* their tags say what they mean
* we could use `<div>` tags and [JavaScript](../../../../contexts/javascript/javascript/) to re-create their functionality
* yet, we continue to use the old tags because they still make so much more sense!
