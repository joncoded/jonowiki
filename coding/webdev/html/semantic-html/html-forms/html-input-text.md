---
description: allowing the user to enter alphanumeric content
---

# HTML input: text

At the minimal, the input field looks like this:

```markup
<form action="destination.html" method="post">

    <label for="fname">First name</label>
    <input type="text" name="fname">

    ...    
    
</form>
```

We can certainly add more attributes:

```html
<form action="destination.html" method="post">

    <label for="fname">First name</label>
    <input type="text" name="fname" id="fname" maxlength="50" required>

    ...    
    
</form>
```

Most of those attributes are self-explanatory and "google-able"; however, the difference between a `name` and `id` lies on the requirement uniqueness of `id` while we can use `name` multiple times in the same HTML document!
