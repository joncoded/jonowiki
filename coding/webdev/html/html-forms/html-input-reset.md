---
description: allowing the user to reset the entire form
---

# HTML input: reset

### Essentials

For whatever reason, this `<input>` with a `type="reset"` appears as a button and allows a user to return each field in the form back to its blank or default setting:&#x20;

```markup
<form action="destination.html" method="post">

    <div>
        <label for="fname">First name</label>
        <input type="text" name="fname" id="fname">
    </div>
    
    <div>
        <label for="lname">Last name</label>
        <input type="text" name="lname" id="lname">
    </div>
    
    <div>
        <label for="gender">Gender</label>
        <select name="gender" id="gender">
            <option value="m">Male</option>
            <option value="f">Female</option>
            <option value="n">Other</option>
        </select>
    </div>
    
    <!-- ready, reset, go! -->
    <div>
        <input type="reset">
        <input type="submit" value="Go!"> 
    </div>
    
</form>
```

### Example

{% embed url="https://codepen.io/joncoded/pen/GRvPvML" %}

In the example above, if we click "Reset", then:

* The fields for "First name" and "Last name" would become blank
* The select drop-down for "Gender" would revert back to "Male" if we had selected anything other than "Male"&#x20;

### Takeaways

Personally, using a "Reset" button:&#x20;

* feels like a waste of time after filling in a whole form
* feels like over-kill after filling in just one field!&#x20;
* could potentially annoy the user if clicked accidentally

Still, this `input` type remains available for some odd reason...