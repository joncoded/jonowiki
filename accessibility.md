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
