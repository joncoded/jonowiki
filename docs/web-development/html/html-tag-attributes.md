---
description: giving information to objects on a webpage
---

# 🏷 HTML tag attributes

We can add information about the objects of a webpage (i.e. headings, paragraphs, images, etc.) onto the objects themselves!

If tags were physical objects, think of the **attribute** as a _dimension_ like `height` and `width`:

* For an object with a height of 120 pixels, think of
  * `height` as the **attribute**
  * `120` as the **value**

```markup
<img src="image.jpg" height="120">
```

Also, coming from other backgrounds:

* We may know the attribute as a **property** in other programming languages and in science
  * e.g. "the properties of helium" in chemistry
* In linguistics, attributes resemble _**adjectives**_ as they _describe_ the object (i.e. the HTML tag)

### Universal HTML attributes

Some attributes can appear on almost any tag, such as:

* `id` whose value can only appear once per page&#x20;
  * of course, to uniquely identify one element!
* `class` whose value usually describes a quality
  * ...and possibly its membership in a group of related elements

```markup
<section id="chapter-12">
<!-- "chapter-12" can appear only once per page -->

    <div class="container-sized">
    <!-- "container-sized" can appear again on the same page -->
    
        <h1>Row 1</h1>
        
    </div>
    
    <div class="full-width">
    
        <h1>Row 2</h1>
    
    </div>
    
    <div class="container-sized">
    
        <h1>Row 3</h1>
        
    </div>
    
</section>
```

### Special HTML attributes

The following tags have nearly inalienable and specialized attributes:

#### `<a>` (links)

This tag introduces us to **tag attributes** because it almost always has an attribute:

* The most common attribute for the link, `href` , means "hypertext reference"

In this example, the `href` attribute consists of the full URL of the page to which we want to link:

```markup
<a href="https://www.google.com">Google</a> 
```

* Another useful attribute for this tag called `target` involves opening the link in a new tab

```markup
<a href="https://www.google.com" target="_blank">Google</a>
```

By specifying the value `"_blank"` for the `target` attribute, we specify that the link will open in a new window (or, in most modern browsers, a new tab!)

#### `<img>` (images)

Another tag that will almost always have an attribute, as it relies on outside information:

* The most common attribute for the image, `src` means "source"

In this example, the `src` consists of the full URL of the page to which we want to use:

```markup
<img src="https://www.placehold.it/300x300.jpg" />
```

(Any tag that has to do with a media file usually has an attribute that indicates the filename!)
