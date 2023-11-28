---
description: allowing the user to write text without anyone else looking
---

# ✴ HTML input: password

### Essentials

The `<input>` field for `type="password"` can look something like this:

```html
<form action="destination.html" method="post">

    <label for="passwort">Passwort</label>
    <input type="password" name="user-password" id="passwort" 
        minlength="8" placeholder="make it hard to guess!" required> 
    
</form>
```

It essentially looks like an `<input>` field with the `type="text"` except that the user only sees dots instead of the text!

{% embed url="https://codepen.io/joncoded/pen/PoKxaYN" %}
a demo of a password field above
{% endembed %}

### Takeaways

* The `id` for a `type="password"` field corresponds with the `<label>`'s `for` attribute
* The `name` can differ from the `id`

### Options

* The `minlength` and `maxlength` (an integer) restrict the length of user input
  * We can use none, one or both of those attributes
* The `placeholder` offers a hint that will disappear on user input (and reappear if reset)
