---
description: writing notes while coding webpages
---

# 🗣 HTML commenting

**HTML comments** allow us to enter notes in an HTML file and they won't directly affect the run time of a page:

```markup
<!-- this is a comment -->

<!-- here is another comment -->

<!-- 1999-12-31 : TODO don't forget to finish this (you probably won't!) -->
```

In general:

```
<!-- (some one line message) -->
```

Comments can also have multiple lines:

```
<!--

this 
will
work 
too

-->
```

### DOCTYPE: a special kind of comment

These days, you need only place this at the top of any HTML document or template:

```xml
<!DOCTYPE html>
<html>
...
</html>
```

This page will let the browser know that your HTML file uses _HTML 5!_

Note that although the doctype looks like a comment, it differs in that it begins with only`<!` rather than `<!--`

Doctypes used to look more complex, e.g. in HTML 4.01:

```xml

<!DOCTYPE HTML PUBLIC 
 "-//W3C//DTD HTML 4.01 Transitional//EN" 
 "http://www.w3.org/TR/html4/loose.dtd"
>
```

Some code archives and old, under-maintained websites may still have these kinds of DOCTYPES!
