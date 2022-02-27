---
description: going from nothing to a boilerplate for your future React projects
---

# React setup

### Pre-requisites

* Ability to run UNIX commands on a [command-line interface](../workspace/command-line.md)
* You know that `$` means the prompt of a Terminal command line
* You have [npm](https://www.npmjs.com) installed (check by entering `$ npm -v` on Terminal)
  * If it reveals a version number, then you're okay
  * If not:
    * `$ npm install -g n`(let the installation of the installer run)
    * `$ n stable` ( to get the latest stable version of node and npm)

### Installing _create-react-app_

This will create a React app boilerplate creator (yup, they've created a "creator"):

* `$ npm install create-react-app -g`

### Creating the React app

* `$ npx create-react-app appname`
  * you can change `appname` to whatever app name you want
  * this will generate a folder called `appname` and a whole bunch of files within it
  * this `appname` folder therefore makes up your "newborn app"

### Previewing the React app

* `$ npx yarn start`
  * this will run your app on your machine (by default on `localhost:3000`)
  * you can go to your browser, enter `localhost:3000` and see React's atomic logo

![](<../../../.gitbook/assets/ 2020-05-28 at 10.57.49.png>)

### Modifying the React app

We can boil down the default app by modifying the following files:

#### src/App.js

```jsx
import React from 'react';

/* uncomment the line below if you need this later */
/* import './App.css'; */

function App() {
  return (
    <div className="App">
    </div>
  );
}

export default App;
```

#### src/App.css

```jsx
/* make it blank :) */
```

### Cleaning up

To keep things simple, we can also remove all files in the `public` and `src` folders except for the following:

* public/index.html
* src/index.js
* src/index.css
* src/App.js

It is possible to reduce this just down to `public/index.html` and `src/index.js` but that would make our code less maintainable in the long run.

Then, use the following code in each file:

#### public/index.html

You will almost never touch this file because React puts everything inside of the `<div id="root">`via the other files:

```markup
<!DOCTYPE html>
<html lang="en">

  <head>

    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <title>Hello URL</title>

  </head>

  <body>

    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>

  </body>

</html>
```

#### src/index.js

We can boil index.js just down to this:

```jsx
import React from 'react';
import ReactDOM from 'react-dom';

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);
```

#### src/index.css

It can actually remain blank but you may wish to use it to add your own styles:

```jsx
```

#### src/App.js

This is where you will begin extending your app's code:

```jsx
import React from 'react';

import './index.css'; 

function App() {
  return (
    <div className="App">
    </div>
  );
}

export default App;
```

### Moving on!

We will try to make an app that does something real by building upon the things learned from this page ➡️
