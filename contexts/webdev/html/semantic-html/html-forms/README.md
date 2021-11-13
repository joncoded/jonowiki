---
description: adding user interactivity on a webpage
---

# HTML forms

**Forms** give the otherwise static web page a layer of _interactivity ..._

... instead of just the website giving the user data, the user can also give the website data!

### Structure

A simple form in HTML may look like this:

```markup
<form action="destination.html" method="post">

    <label for="fname">First name</label>
    <input type="text" name="fname" id="fname">
    
    <label for="lname">Last Name</label>
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

### Elements

Breaking that into small pieces, let's begin with the parent `<form>` tag:

* `action` refers to where the form will take us once we _submit_ the form
* `method` refers to how the form will submit (and what the URL will look like upon the form's submission)
  * `POST` - submitting data - the URL would have no query strings (the URL would have "?" followed by some text)
  * `GET` - retrieving data - the URL would have query strings (e.g. `index.html?fname=Jon`)

As several input types exist, we can give each standard `input` field type of a form its own page:

* `text`
* `radio`
* `checkbox`
* `password`
* `submit`
* `reset`
* `hidden`

...as well as some newer and more obscure types!

We will also have a look at other form elements:

* `select` (dropdown)
* `textarea`
* `fieldset`
* `legend`
* `datalist`
