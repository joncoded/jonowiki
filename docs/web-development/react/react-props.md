---
description: passing data from parent to child components
---

# React props

To make a parent component "talk" to a child component:

* the parent component will use a special kind of attribute or _property_ known as `props`
  * this consists of an attribute in a JSX tag
  * the attribute can take on any _key name_ with any _value_
* the child component function will receive these `props` in its parameters
  * its `return` JSX can then use it like a variable

For example, with an `App.js` we would introduce a `someData` attribute, or `props` :

```javascript
/* jonotype/src/App.js */

import { Component } from './Component.js'

export default function App() {
  return (
    <div>
      <h1>Hello!</h1>
      <h2>Let's begin our React App!</h2>
      <Component someData="hello component" />
    </div>
  )
}
```

Then, in the `Component.js` we would bring the `props` in as a **parameter**:

```javascript
/* jonotype/src/Component.js */

export function Component(props) {
  return (
    <div>
      <h3>{props.someData}</h3>
      <p>A child component!</p>      
    </div>
  )
}
```

To access `someData` we would simply use `props.someData` as shown above!

#### Alternate syntax

We could make things more concise in the component (let's make a separate `ComponentAlternate.js` file for clarity's sake):

```javascript
/* jonotype/src/Component.js */

export function Component({someData}) {
  return (
    <div>
      <h3>{someData}</h3>
      <p>A child component!</p>      
    </div>
  )
}
```

Notice that:

* the `{someData}` parameter now has curly braces
* the keyword `props` has become redundant via JavaScript destructuring

Moving this over to `App.js`

```javascript
/* jonotype/src/App.js */

import { Component } from './Component.js'
import { ComponentAlternate } from './ComponentAlternate.js'

export default function App() {
  return (
    <div>
      <h1>Hello!</h1>
      <h2>Let's begin our React App!</h2>
      <Component someData="hello component" />
      <ComponentAlternate someData="alternate component" />
    </div>
  )
}
```

The output for `Component` and `ComponentAlternate` will look essentially identical (except for the value passed into the `someData` prop):

<figure><img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1700771240407/63ce5e04-6608-4efc-a840-6267e6e89393.png" alt=""><figcaption></figcaption></figure>

#### Passing in more than one parameter

We could also pass in another parameter (let's use our `ComponentAlternate.js` file):

```javascript
/* jonotype/src/ComponentAlternate.js */

export function ComponentAlternate({someData, otherData}) {
  return (
    <div>
      <h3>{someData} #{otherData}</h3>
      <p>A child component!</p>      
    </div>
  )
}
```

Then, in the `App.js` file:

```javascript
import { Component } from './Component.js'
import { ComponentAlternate } from './ComponentAlternate.js'

export default function App() {
  return ( 
    <div>
      <h1>Hello!</h1>
      <h2>Let's begin our React App!</h2>
      <Component someData="hello component" />
      <ComponentAlternate 
          someData="alternate component" 
          otherData={100} 
      />
    </div>
  )
}
```

Note how we simply added an extra JSX attribute/prop called `otherData` in the `ComponentAlternate` tag!

The output will look like this:

<figure><img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1700771990849/2a127b14-b450-4094-a0d9-ea187a46da09.png" alt=""><figcaption></figcaption></figure>

### **Code repo**

available on [https://github.com/joncoded/jonotype/tree/001-props](https://github.com/joncoded/jonotype/tree/001-props)
