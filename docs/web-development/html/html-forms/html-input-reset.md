---
description: allowing the user to reset the entire form
---

# HTML input: reset

### Essentials

For whatever reason, this `<input>` with a `type="reset"` appears as a button and allows a user to return each field in the form back to its blank or default setting:

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

### Takeaways

Personally, using a "Reset" button:

* feels like a waste of time after filling in a whole form
* feels like over-kill after filling in just one field!
* could potentially annoy the user if clicked accidentally

Still, this `input` type remains available for some odd reason...
