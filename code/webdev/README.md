---
description: reviewing web-development concepts
---

# 📖 Docs

### **Introduction**

![](https://images.unsplash.com/photo-1581291518633-83b4ebd1d83e?crop=entropy\&cs=srgb\&fm=jpg\&ixid=MnwxOTcwMjR8MHwxfHNlYXJjaHwxfHx3aXJlZnJhbWV8ZW58MHx8fHwxNjM2ODI4Nzkz\&ixlib=rb-1.2.1\&q=85)

**Web development** comes in two main flavours:

* The **front-end** (presentation-oriented programming, i.e. _what you see_)
* The **back-end** (data and logic-oriented programming, i.e. _what you get_)

We will see later on this page that:

* the line between the front-end and the back-end often blurs
* computer science theory plays a large role in web development in surprising ways

### The front-end

To present data, we connect the following "3 S's":

* **Structuring** (HTML)
  * to enforce the **sensibility (order) of visual components**
  * to ensure that a web resource has [**accessibility to everyone**](accessibility.md)\*\*\*\*
* **Styling** (CSS)
  * to enhance the **visual look-and-feel**
* **Scripting** (e.g. JavaScript, React, Angular, jQuery, etc.)
  * to manage **user input** and **data changes**
  * to connect the front-end with the back-end

{% content-ref url="html/" %}
[html](html/)
{% endcontent-ref %}

{% content-ref url="css/" %}
[css](css/)
{% endcontent-ref %}

{% content-ref url="javascript/" %}
[javascript](javascript/)
{% endcontent-ref %}

{% content-ref url="react/" %}
[react](react/)
{% endcontent-ref %}

Sometimes, front-end developers may have to take part in:

* **Imaging** (e.g. Photoshop or free [Photopea](https://www.photopea.com))
  * to adjust (resize, crop, etc.) visual assets provided by a client
  * to take the load off the design team who might work with more complex imaging and graphics projects

### The back-end

The back-end usually involves:

* **Scripting** (e.g. also JavaScript, with some PHP, Ruby, Perl and older programming languages)
  * to **process the results** from database querying
* **Database querying** (e.g. GraphQL, MongoDB, MySQL)
  * to **get/set data** from a database
* **Authorization** and **authentication**
  * the former refers to allowing a user into a system
  * the latter refers to determining that the user is genuine

### All developers

Each developer may also have to take part in:

* **Versioning** or **version control** (e.g. Git or Mercurial)
  * to not only submit content "to the cloud" but also to ensure backups if something goes wrong
  * to allow for collaboration by multiple developers within the same project(s)

{% content-ref url="git/" %}
[git](git/)
{% endcontent-ref %}

* **Deployment** (e.g. FTP, Jenkins, Netlify, etc.)
  * to get that web project onto the Internet!
    * usually nowadays handled by a specialized team called **development operations** (or **dev ops**)

{% content-ref url="web-operations/" %}
[web-operations](web-operations/)
{% endcontent-ref %}

* **Documenting** (e.g. GitBook!)
  * to communicate cases and learnings for obvious reasons
* **Organizing** (e.g. SCRUM)
  * to ensure that all the programming, layout, look-and-feel, content, images (and any other assets) all come together, so that the development experience goes as smoothly as possible
  * to send completed projects for quality assurance and correct defects
* **Optimizing**
  * for more universal accessibility, better usability, improved speed
  * for enhancing the experience of the "finished" product
    * note: no product ever really gets "finished"

{% content-ref url="accessibility.md" %}
[accessibility.md](accessibility.md)
{% endcontent-ref %}

As one can gather, a lot of web development involves tasks other than simply programming!
