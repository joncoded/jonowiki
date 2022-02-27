---
description: allowing the user to select one or more out of several options
---

# HTML input: checkbox

### Essentials

The `<input>` field for `type="checkbox"` looks like this:

```markup
<form action="destination.html" method="post">

    <p>Select your toppings:</p>
    
    <input type="checkbox" name="cheese" id="toppings-cheese" checked>
    <label for="toppings-cheese">Cheese</label>
    
    <input type="checkbox" name="pepperoni" id="toppings-pepperoni" checked>
    <label for="toppings-pepperoni">Pepperoni</label>

    <input type="checkbox" name="ham" id="toppings-ham">
    <label for="toppings-ham">Ham</label>

    <input type="checkbox" name="peppers" 
        id="toppings-green-peppers" value="green">
    <label for="toppings-green-peppers">Green peppers</label>

    <input type="checkbox" name="pineapple" id="toppings-pineapple">
    <label for="toppings-pineapple">Pineapple</label>

</form>
```

### Takeaways

* Unlike `type="radio"` the checkboxes do not need the same value in the `name` attribute
* The checkbox does have an optional `value` attribute which will submit along with the `name` which will act as a "key" or property name
  * When the checkbox _does not_ have a `value` then the value would simply be `on`
* The `checked` attribute makes the checkbox checked by default
  * We can do this for more than one checkbox
* The `<label>` for each `type="checkbox"` corresponds with each checkbox's `id` value (not the `name`)
* The `<label>` also allows the user to click on the label instead of the checkbox for greater accessibility
