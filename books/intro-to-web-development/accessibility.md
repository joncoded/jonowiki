---
description: allowing everyone to use our web projects
---

# 🚧 Accessibility

### Definition

* **accessible web content** as web content available to practically anyone via suitable alternatives, e.g.:
  * hyperlinks with keyboard or other non-mouse methods
  * audio content has a text-based equivalent
  * video content has text-based captions
  * images have alternate text accessible by a screen-reader
  * text customization for font size, high-contrast, etc.
* **disability** as either a permanent or non-permanent, a physical or non-physical (e.g. cognitive), impediment that prevents one from accessing something

#### Principles

* **perceivable** (by more than one sense?)
* **operable** (navigability of current and potential positions?)
* **understandable** (legibility and consistency?)
* **robust** (accessible by different hardware and software?)

### Issues

#### Focus

* a change in appearance of an input item on the screen that shows that it will currently receive input from an input hardware, e.g.
  * **focus ring**, the highlighted border of a text box
  * **text decoration**, the underline of a hyperlink
* if not specified via `tabindex`, non-interactive elements will not have **focus**, e.g.:
  * headings
  * paragraphs
  * images
* the order of elements matters, i.e.:
  * [right-floated](https://developer.mozilla.org/en-US/docs/Web/CSS/float) elements will still focus first

#### Images

* **alternative text** for images that contain information not provided by nearby text&#x20;

#### Headings

* used to help create a outline for a webpage
* **hierarchy** for `<h1>`, `<h2>`, `<h3>`, etc. tags&#x20;
  * a lower level
    * an `<h2>` tag can only follow an `<h1>` or another `<h2>`tag
    * an `<h3>` tag can only follow an `<h2>` or another `<h3>` tag
    * and so on until `<h6>`
  * a higher level can follow any heading tag below it
    * e.g. if there is an `<h5>` tag, an `<h2>` tag can follow it without an `<h3>` and an `<h4>` before it:

```markup
<h1>Heading Level 1</h1>
<h2>Heading Level 2</h2>
<h3>Heading Level 3</h3>
<h4>Heading Level 4</h4>
<h5>Heading Level 5</h5>
<h2>Another Heading Level 2</h2>
<h4>Another Heading Level 4</h4> <!-- This line is not accessible! -->
```

#### Links

* use **offscreen text** to provide additional information for assistive technology users
  * e.g. sighted users will see a "Learn more" link, next to a Google logo
  * however, AT-users will hear "Learn more about Google, opens in a new window"

