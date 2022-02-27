---
description: adding extra information about the webpage
---

# HTML \<meta>

Located within the `<head>` tag, each `<meta>` tag usually consists of an attribute that describes the HTML document:

```html
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
* `author` not as important ;)
* `viewport` has recently come on board as it helps adjust the size of everything when viewed on smaller screens such as mobile phones and tablets
