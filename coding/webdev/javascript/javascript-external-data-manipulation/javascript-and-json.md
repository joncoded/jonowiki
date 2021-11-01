---
description: the preferred data format of the internet
---

# JavaScript and JSON

**JSON** \(**JavaScript Object Notation**\) allows for storing small sets of data in a relatively simple but robust structure:

### The basic structure of a JSON object

The simplest JSON object looks like: 

```text
{ "property" : "value" }
```

In a browser console, let us take the basic JSON object above and assign it a variable called _jsonObject_:

```text
> let jsonObject = { "property" : "value" };
<- undefined
```

It responds with "undefined" but let us enter the following again into the console to confirm that the object exists:

```text
> jsonObject 
<- {property: "value"}
```

### Notations for the notations

We could then use the **dot notation** _object.property_:

```text
> jsonObject.property
<- "value"
```

Or, we could use the **associative array notation** _object\["property"\]_:

```text
> jsonObject["property"]
<- "value"
```

The associative array notation becomes useful when the property names lengthen so much that we would need to use "**kebab-notation**", the stringing of multiple words with dashes!

```text
let obj = { "example-of-a-very-long-property-name" : "its value" }
```

We would then access that property like such:

```text
> obj["example-of-a-very-long-property-name"]
```

### Objects with more than one property

Naturally, an object could have multiple property-value pairs:

```text
{ 
  "property1" : "value1", 
  "property2" : "value2", 
  "property3" : "value3", 
  ... 
} 
```

Calling the above _jsonObject_, we would enter _jsonObject.property2_ or _jsonObject\["property2"\]_ into a console to yield "value2"

```text
> jsonObject["property2"]
<- "value2"
```

### Objects inside of objects

The object could also have properties with values that themselves have sub-objects:

```text
{ 
  "property1" : { 
    "property1A" : "value1A" 
  }, 
  "property2" : { 
    "property2A" : "value2A", 
    "property2B" : "value2B" 
  }, 
  "property3" : "value3" 
}
```

Calling the above _jsonObject_, we would enter _jsonObject.property2.property2B_ or _jsonObject\["property2"\]\["property2B"\]_ \(a two-dimensional array\) into a console to yield "value2B"\)

```text
> jsonObject["property2"]["property2B"]
<- "value2B"
```

We can then infer here that this versatile structure could allow for quite complex objects with many properties and sub-properties to the desired degree!

### Accessing JSON data with JavaScript

If we have a file named `data.json` on the same folder as the JavaScript file: 

```javascript
const request = new XMLHttpRequest()
request.open('GET', 'data.json', true)

request.onload = function() {
  if (this.status >= 200 && this.status < 400) {
    const data = JSON.parse(this.response)      
    // data here
    console.log(data)
  } else {
    // server error
  }
}

request.onerror = function() {
  // connection error
}

request.send()
```

