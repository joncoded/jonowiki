---
description: letting the browser know the version of HTML used
---

# HTML doctype

These days, you need only place this at the top of any HTML document or template:

```markup
<!DOCTYPE html>
<html>
...
</html>
```

This page will let the browser know that your HTML file uses _HTML 5!_

{% hint style="info" %}
Note that although the doctype looks like a comment, it differs in that it begins with only`<!` rather than `<!--`
{% endhint %}

### Past doctypes

HTML 4.01:

```markup
<!DOCTYPE HTML PUBLIC 
 "-//W3C//DTD HTML 4.01 Transitional//EN" 
 "http://www.w3.org/TR/html4/loose.dtd"
>
```

Almost nobody uses that these days but you may see it in some code archives!
