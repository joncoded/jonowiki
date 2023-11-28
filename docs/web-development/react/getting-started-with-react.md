---
description: going from nothing to a boilerplate for your future React projects
---

# React setup (from scratch!)

Many tutorials mention `create-react-app` to beginners of React, which often includes redundancies and intimidating stuff on the side ... however, another way exists! For a more bare-bones approach, we can follow this "big bang to life" procedure:

* initialize the project with a `package.json` file
* install a few dependencies (including `react`)
* create the foundational `public/index.html` file
* create our foundational `index.js` **entry point** file
* create our `App` file
* create other component files

### Initializing the project

This applies not only to React projects but to any web project!

On a new folder, e.g. `jonotype`, we will enter this following command on Terminal:

```bash
npm init -y
```

This creates a file named `package.json` that describes our new web app:

```json
// jonotype/package.json

{
  "name": "jonotype",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```

We can do a few modifications:

```json
// jonotype/package.json

{
  "name": "jonotype",
  "version": "1.0.0",
  "description": "",
  /* here */
  "main": "src/index.js", 
  "scripts": { 
    /* here */
    "start": "react-scripts start", 
    "build": "react-scripts build", 
    "test": "react-scripts test --env=jsdom",
    "eject": "react-scripts eject" 
  },
  /* here */
  "browserslist": [
    ">0.2%",
    "not dead",
    "not ie <= 11",
    "not op_mini all"
  ],
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```

#### Updating the entry point

We update the `main` property from `index.js` to `src/index.js` just to keep our files more organized!

#### Adding `npm run` scripts

We then include our `npm run` scripts - these enable us to run a local version of our app (webpage)!

#### Adding `browserslist`

The `browserslist` property just excludes any ancient browsers like Internet Explorer!

### Installing the dependencies

Now, we can install three dependencies (for now) which allow us to use the React library and family of scripts:

```bash
npm install react react-dom react-scripts
```

Upon installation our `package.json` automatically updates to something like this:

```json
// jonotype/package.json

{
  "name": "jonotype",
  "version": "1.0.0",
  "description": "",
  "main": "src/index.js",
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test --env=jsdom",
    "eject": "react-scripts eject"
  },
  "browserslist": [
    ">0.2%",
    "not dead",
    "not ie <= 11",
    "not op_mini all"
  ],
  "keywords": [],
  "author": "",
  "license": "ISC",
  /* this got updated */
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-scripts": "^5.0.1"
  }
}
```

(The `dependencies` property adds in `react` + `react-dom` + `react-scripts` !)

### The foundational HTML file

Once we let those dependencies install, we can create a new folder called `public`, in which we can place our foundational `index.html` file:

```xml
<!-- jonotype/public/index.html -->

<!DOCTYPE html>
<html lang="en">

    <head>
    
    	<meta charset="utf-8">
    	<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    	<title>React App</title>
    
    </head>
    
    <body>
    	
        <noscript>
    		y u no use javascript? 
        </noscript>
    	
        <div id="root"></div>
    	
    </body>

</html>
```

Briefly, this minimal HTML file consists of:

* the `<head>` tag for technical meta data
  * character set
  * browser sizing
  * `<title>` bar text
* the `<body>` tag which has
  * `<noscript>` warning because React apps require JavaScript (which everyone should have enabled on their browsers)
  * `<div id="root"></div>` the most important part here, where the React app lives!

### The foundational index.js file

Now, we will connect the foundational HTML file with a foundational JavaScript file; this `src/index.js` file also happens to import the React scripts:

```javascript
// jonotype/src/index.js

/* dependencies */
import { StrictMode } from "react"
import { createRoot } from "react-dom/client"
import App from "./App"

/* manipulation of the index.html DOM */
const rootElement = document.getElementById("root")
const root = createRoot(rootElement)

/* displaying the React virtual DOM */
root.render(
  <StrictMode>
    <App />
  </StrictMode>
)
```

Note that errors will occur because we have not created the `App` code yet, which will do in the next section!

Also note:

* `StrictMode` is a **built-in component** of React which outputs errors in the browser's console concerning any problems inside the `<StrictMode></StrictMode>` tag
* `createRoot` builds upon the DOM in `index.html`

### The App.js file

Finally, let's get some real visible code going by starting a new file `src/App.js`:

```javascript
/* jonotype/src/App.js */

export default function App() {
  return (
    <div>
      <h1>Hello!</h1>
      <h2>Let's begin our React App!</h2>
    </div>
  );
}
```

Breaking that down:

* `export` means we can use this file in other files
* `default` means that when we `import` this file elsewhere we do not have to call it `App` :

```javascript
/* jonotype/src/index.js */

import { StrictMode } from "react"
import { createRoot } from "react-dom/client"

/* instead of */
// import App from "./App"

/* we can do this because we used "default" in App.js */
import Whatever from "./App"

const rootElement = document.getElementById("root")
const root = createRoot(rootElement)

root.render(
  <StrictMode>
    <Whatever />
  </StrictMode>
)
```

### Other component files

Creating child components keeps our code more organized and "modular", so let's give this a try with `src/Component.js`, with `CamelCase` as the convention for component files:

```javascript
/* jonotype/src/Component.js */

export function Component() {
  return (
    <div>
      <p>A child component!</p>
    </div>
  );
}
```

Notice how we did not say `export default function Component()` there!

Then, going back to `src/App.js` we then `import` and render `Component.js`:

```javascript
/* jonotype/src/App.js */

import { Component } from './Component.js'

export default function App() {
  return (
    <div>
      <h1>Hello!</h1>
      <h2>Let's begin our React App!</h2>
      <Component />
    </div>
  );
}
```

Some things to notice here:

* We use curly braces for `{ Component }` to extract the function `Component` from `src/App.js`
* We cannot replace `Component` with another name because we did not specify it as an `export default` back in `src/Component.js`
* Sometimes, specifying a `default` in a child component helps if we wish to rename the child component later on

#### Aliasing the imported component

If we want an imported component to have a different name, then we could still give it an **alias** using the `as` operator in the `import` statement:

```javascript
/* jonotype/src/App.js */

import { Component as Whatever } from './Component.js'

export default function App() {
  return (
    <div>
      <h1>Hello!</h1>
      <h2>Let's begin our React App!</h2>
      <Whatever />
    </div>
  );
}
```

Oftentimes, we would need to do this if there exist **naming conflicts**!

### Running our app

Finally, we can run our app! In Terminal, we would simply run the following command:

```bash
npm start
```

We should see something like:

```plaintext
Compiled successfully!

You can now view jonotype in the browser.

  Local:            http://localhost:3000
  On Your Network:  http://192.168.0.153:3000

Note that the development build is not optimized.
To create a production build, use npm run build.

webpack compiled successfully
```

Then, from our browser, we go to `localhost:3000` and we should see something like:

<figure><img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1700765925923/c806aa85-22ad-4b1e-bf67-dc2cabaea693.png" alt=""><figcaption></figcaption></figure>

#### Notice the relationship of components

* "A child component!" lives in `src/Component.js`
* `src/Component.js` gets imported by `src/App.js`
* `src/App.js` gets imported by `src/index.js`
* `src/index.js` builds upon `public/index.html`

Clearly, the powerful implications of React components already appear in this very basic static "app" in terms of:

* _re-usability_
  * we could include `<Component />` as many times in as many places as we wish, in `src/App.js`
* _division of labour_
  * if we want to expand upon `src/Component.js` we could do so without affecting the rest of `src/App.js`
* _portability_
  * keeping things in smaller components makes code easier to read

### Moving on

We have covered quite a bit here, starting from nothing and ending with a basic static app - but more exciting topics lie ahead! More, such as:

* **building** the app
* **deploying** the app to the internet
* creating **dynamic components**
* building the illusion of a multi-page website through **routes**

Developers _never_ get bored!

{% hint style="info" %}
By the way, you can see the final product in [https://github.com/joncoded/jonotype](https://github.com/joncoded/jonotype)
{% endhint %}
