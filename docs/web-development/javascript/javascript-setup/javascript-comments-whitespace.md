---
description: documenting the script
---

# JavaScript comments and whitespace

Here we will outline two handy concepts regarding documentation in JavaScript: &#x20;

### **Comments**

**Comments** allow us to place notes inside the code, without affecting how the program runs:

```javascript
// this is a comment in JavaScript

/* 

this is also a comment in JavaScript

when we want to write something 

longer than one line

*/
```

However, we do hope to write our JavaScript clearly enough so that we can avoid **excessive commenting**!

### Whitespace

To a certain extent, whitespace does not affect the running of JavaScript past the first space, e.g.:

```javascript
let x = 1
```

We cannot write the following, for example, and expect the code to behave in the same fashion as the above:

```
letx=1
```

JavaScript allows us to do things like this:

```
let x=1
```

However, let's stick with this as a good practice of readability:

```
let x = 1 
```

We could still do more than one space like this:

```
let x      =       1  
```

...but why? Let's just stick to this kind of convention:

```javascript
let x = 1
```
