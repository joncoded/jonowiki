---
description: allowing the user to choose from one out of several options
---

# HTML input: radio

The `<input>` field for `type="radio"` looks like this:

```html
<form action="destination.html" method="post">

    <p>Select your language:</p>

    <input type="radio" name="language" id="form-lang-en" value="en">
    <label for="form-lang-en">English</label>

    <input type="radio" name="language" id="form-lang-is" value="is">
    <label for="form-lang-is">Icelandic</label>
    
    <input type="radio" name="language" id="form-lang-jp" value="jp">
    <label for="form-lang-jp">Japanese</label>
    
    <p>Select your gender:</p>
    
    <input type="radio" name="gender" id="form-gender-m" value="m">
    <label for="form-gender-m">Male</label>
    
    <input type="radio" name="gender" id="form-gender-f" value="f">
    <label for="form-gender-f">Female</label>
    
    <input type="radio" name="gender" id="form-gender-x" value="x">
    <label for="form-gender-x">Other</label>
    
</form>
```

Things we can take away:

* Unlike `type="text"` each `type="radio"` button must have the same `name` if it belongs to a set of related options&#x20;
  * (we would have a different value for the `name` attribute if we have another set of related options elsewhere on the same form, as in the case with `gender`)
* The `value` attribute does not need to have the same value as the text in the `<label>`
  * i.e. the form will submit `"en"` even though the user may see `English` on the form
* The `<label>` corresponds with each radio button not via the button's `name` attribute but via the `id` since that provides the unique identifier in this case
* The `<label>` also allows greater accessibility as a user can now click on the label instead of just the button itself!
