---
description: getting that first webpage in
---

# ⚙ HTML setup

Let us begin with the creation of a basic HTML file!

### Prerequisites

To create an HTML file, you could use only a **text editor,** like [TextEdit](https://en.wikipedia.org/wiki/TextEdit) or [Notepad](https://en.wikipedia.org/wiki/Microsoft\_Notepad)...

...but a **code editor, like** [Sublime](https://www.sublimetext.org) or [Visual Studio Code](https://code.visualstudio.com), helps a lot!

### The minimal HTML file

If we open the text editor, we can copy and paste the below:

```markup
<!DOCTYPE html>
<html lang="en">

    <head>
        <title>(The title that will show in the browser tab)</title>        
    </head>
    
    <body>
        <p>(The content)</p>
    </body>
    
</html>
```

* The first line tells the browser to expect an HTML document
* The actual HTML begins inside the `<html>` tag which contains an optional `lang` attribute to indicate what human language the page uses
  * the HTML continues with the `<head>` tag&#x20;
    * this contains the HTML page's metadata (data about the page) with `<meta>` tags
  * then the `<body>` tag contains the actual content that the browser displays

### Closing tags

* Most HTML tags come paired with a **closing tag**
  * In the above example, we have `</title>`, `</head>`, `</p>, </body>` and `</html>`
  * Tags close in a nested hierarchy such that we cannot have an outer tag close before an inner tag closes, e.g. `<body><h1></body></h1>` must instead be `<body><h1></h1></body>`

That makes up nearly the barest-bones HTML page; after that, the possibilities become endless:

```markup
<!DOCTYPE html>
<html lang="en">

    <head>
        <meta charset="utf-8" />
        <title>Page's title</title>        
    </head>
    
    <body>
        <h1>Heading 1</h1>
        <p>This forms a pararaph of some sorts. </p>
    </body>
    
</html>
```

### Self-closing tags

* Here, we have introduce a new tag `<meta charset="utf-8" />` which features a tag without a closing tag that self-closes (we can also call this a **self-closing tag**)
  * Other tags that have this feature include
    * `<link href="..." />` for stylesheets (located usually only in the `<head>` tag)
    * `<img src="..." />` for images
    * `<br />`for line breaks (like pressing "shift+return" or "shift+enter" on a word processor)
  * Note that it has become _optional_ to include the **self-closing slash**
    * e.g. it is OK to write just `<br>`

### Finally

* The optional `<meta charset="utf-8" />` tag tells the browser what kind of alphabets (and numbers) the document will use
  * We've included this tag here more to demonstrate self-closing tags than its function
  * We will later look at [meta tags in detail](broken-reference)
* We will go over `<h1>` and `<p>` in the next page about **HTML tags...**
