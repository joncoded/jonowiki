---
description: allowing the user to input one line of plain text
---

# HTML input labels

Looking closer into the `<form>` at our `<input>` fields:

```html
<form action="destination.html" method="post">

    <label for="fname">First name</label>
    <input type="text" name="fname" id="fname">
    
    <label for="lname">Last name</label>
    <input type="text" name="lname" id="lname">
    
    <label for="gender">Gender</label>
    <select name="gender" id="gender">
        <option value="m">Male</option>
        <option value="f">Female</option>
        <option value="n">Other</option>
    </select>
    
    <input type="submit" value="Go!">
    
</form>
```

On top of most of each the form fields, we have a `<label>` tag that points to the field...

...also note that when the user clicks on a `<labe`l`>` tag, it becomes equivalent to clicking on the field itself!&#x20;

Each `<label>` has a `for` attribute which matches the form field's `name` attribute:

* The "First name" label matches the `<input>` field that has the name `fname`
* The "Last name" label matches the `<input>` field that has the name `lname`
* The "Gender" label matches the `<select>` field that has the name `gender`

However, the `input` with the `type` of submit (i.e. a button)  does not need a label as the value text serves as the label!
