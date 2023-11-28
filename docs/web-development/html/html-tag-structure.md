---
description: defining the objects of an web page
---

# 🏷 HTML tag structure

HTML tags follow a basic structure of **definition**, **attributes** and **content:**

* Definition, as the tag/object itself, e.g. `<h1>` for a heading
* Attributes, describe the tag, e.g. `src` for the source of an `<img>` tag
  * `<img src="file.jpg" />`
* Content, which houses additional objects and information

### Content inside HTML tags

If we were to include content inside an HTML tag, the tag would need an opening and closing component, for example:

```xml
<h1>(content)</h1>
```

As in the first-level heading above

* `<h1>` makes up the opening tag
* `</h1>` makes up the closing tag

### Nesting

We could even include tags inside tags! Most commonly, we do this with the `<html>` tag itself:

```xml
<html>
    <body>
        <h1>Heading</h1>
    </body>
</html>
```

When we nest a tag, we must close the innermost tag before closing the outer tag (in the above example, we must close `h1` before `body` before `html`)

### Common HTML tag types

#### Headings

`<h1>` ... `<h6>`

* Headings have a hierarchy from 1 (the top) to 6 (the bottom)
  * `<h1>...</h1>` will lead while `<h2>...</h2>` may or may not follow an `<h1>`
  * All full-sized HTML pages should have an `<h1>...</h1>`
  * As an aside, documents (think legal documents) rarely have a proper `<h5>` and `<h6>` because by the point, the document will have become too difficult to follow: try to not have anything further below the `<h4>` level for simple HTML pages

{% hint style="danger" %}
Do _not_ use these headings as font sizes, as the numbers serve a structural purpose of making "levels" for the document
{% endhint %}

#### Paragraphs

`<p>`

* Exactly as advertised: paragraphs of text
* By default, paragraphs will have dividing spaces between them like in written text

#### Lists

`<ul>` (unordered list) `<ol>`(ordered list) `<li>` (list item)

* An unordered list looks like a list of bullets (like this one!)
* An ordered list has numbers (or numerals)
* There exist many ways to style the bullets of these lists (more on this later)
* A list item appears inside of an unordered or ordered list

#### Importance

`<strong>`

* Usually shows the text in **bold** type
* Conveys the idea of an **important keyword** in the text of a document

#### Emphasis

`<em>`

* Usually shows the text in _italic_ type
* Conveys the idea of _stress_ on a word or phrase

#### Strikeout

`<del>` or `<strikeout>`

* Usually shows the text slashed horizontally
* Conveys the idea of removal of a text while still making the text visible

#### Quotations

`<blockquote>`

* Usually shows the text indented
* Conveys the idea that the text is a reference of some other text

```markup
<html>

    <head>
    
        <title>Page title</title>
        
    </head>
    
    <body>
    
        <h1>Heading 1</h1>
        
        <p>Some <strong>text</strong> to <em>welcome you</em>!</p>
        
        <h2>A list</h2>
        
        <ul>
        
            <li>Item 1</li>
            <li>Item 2</li>
            <li>Item 3</li>
            
        </ul>
        
        <blockquote>We have a dream!</blockquote>
        
        <p>This page has <del>no</del> content!</p> 
        
    </body>

</html>
```
