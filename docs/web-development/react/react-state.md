---
description: storing the current situation of a component
---

# ⚛ React state

In React, **state** refers to a special variable that stores the current situation of a component, especially after the initial `return` render, e.g.:

* A state may contain a user's "wish list of trip destinations" for a travel app
  * During the user's session, a user may add a new location to the bucket list
    * Thus, the _state of the wish list_ changes to reflect that addition

### Implementing state in React

As of now, we implement **state** with a React **hook** (a special built-in function) from the React library, so we begin with an `import` statement:

```javascript
/* src/Component.js */

import { useState } from 'react'
```

Then, we define **state variables** and **state setter functions** by de-structuring the `useState` hook:

```javascript
/* src/Component.js */

import { useState } from 'react'

export default function Component() {

  const [ title, setTitle ] = useState('')  

  return (
    <div>
      <h1>{title}</h1>
    </div>
  )
}
```

Note:

* the **state variable**, `title`, can actually have any legal JavaScript variable name
* the **state setter function**, `setTitle` , typically follows the convention of having `set` at the beginning of its name, plus the state variable to which it refers
  * this typically gets used in a **handler function** (shown below) that gets called upon user interaction, e.g. in a form or button or "link as a button"
* the call to `useState` typically takes on one argument which
  * describes the state's **initial value**
  * can be any primitive (string, number, boolean, object, array)
* the state gets referenced in the `return` statement like any other variable in JSX with the curly braces

### Updating the state in React

As mentioned in the previous section, we would typically update a **state variable** by anticipating an interaction from the user interface; that interaction would then trigger the **handler function** to use the **state setter function:**

```javascript
/* src/Component.js */

import { useState } from 'react'

export default function Component() {

  const [ title, setTitle ] = useState('hello') 

  const handleClick = () => {
     setTitle('goodbye')
  } 

  return (
    <div>
      <h1>{title}</h1>
      <button onClick={handleClick}>change title</button>
    </div>
  )
}
```

There, we added a `<button>` with an `onClick` prop to `handleClick` which calls `setTitle` with an argument to change the `title` from the initial "hello" to "goodbye"!

Note:

* `onClick` exists a pre-determined attribute/prop name for click-type events
  * a `click` is the same thing as `touch` on mobile devices or an `enter` keypress
* `handleClick` can take on any name but we use `handle` as a prefix by convention

### Updating state more dynamically with events

That last example showed a state update for pedagogical purposes but it might look a tad over-simplistic; let's look at another example with a user-driven input text field:

```javascript
/* src/NewComponent.js */

import { useState } from 'react'

export default function NewComponent() {

  const [ title, setTitle ] = useState('hello')  

  const handleChange = (event) => {
    setTitle(event.target.value)
  }

  return (
    <div>
      <h1>{title}</h1>
      <label htmlFor="custom">Customize name: </label>
      <input type="text" name="custom" onChange={handleChange} />
    </div>
  )
}
```

With that, the heading changes based on the user input (still not an amazingly cool example but shows how a seemingly static page can change with the help of state!)

Note:

* an `onChange` **event** triggers the handler `handleChange`
* `<label>` tags must use the attribute `htmlFor` instead of `for` to avoid confusion with the keyword `for` in JavaScript
* we used the `handleChange` following the naming convention in the previous example
  * the `handleChange` takes on a parameter `event` supplied by the input field
  * `event.target` refers to the input field while
    * `event.target.value` refers to the text in that field

We can see this action with a CodeSandbox:

{% embed url="https://codesandbox.io/s/react-002-state-sxpv8n?from-embed=" %}

### Code repo

available on [https://github.com/joncoded/jonotype/tree/002-state](https://github.com/joncoded/jonotype/tree/002-state)
