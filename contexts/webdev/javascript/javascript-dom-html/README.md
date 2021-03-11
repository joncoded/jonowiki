---
description: how to take our logic and put it on a webpage
---

# JavaScript \(to the internet!\)

### DOM \(document object model\)

* **Document** = the webpage \(for example\)
  * A document has object\(s\)
* **Object** = the "stuff" \(content but also other things\) on the webpage 
  * An object may also have its own object\(s\)
* **Model** = the representation of the document and the objects
  * We can represent the documents and objects in a "tree" diagram
    * Objects can have "parents" and "children", e.g.
      * the parent of `<head>` is `<html>`
      * the children of `<head>` are `<title>` and `<meta>`

![the DOM of a webpage depicted as a tree diagram \(from bitsofco.de\)](../../../../.gitbook/assets/image%20%281%29.png)

{% hint style="warning" %}
Do not confuse the DOM with HTML but think of HTML as just _a_ visual _representation_ of the DOM! 

A browser could have simply taken the DOM and displayed it like the diagram above ;\)
{% endhint %}

Every HTML webpage on the internet has a structure based on the DOM and, thus, we can use JavaScript to access and manipulate each the structure of each webpage!

{% page-ref page="javascript-dom-access.md" %}

{% page-ref page="javascript-dom-manipulation.md" %}

{% page-ref page="javascript-dom-traversal.md" %}

{% page-ref page="../javascript-essential-topics/javascript-interactivity-with-the-dom.md" %}





