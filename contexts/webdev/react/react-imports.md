# React imports

**Importing** dependencies \(third-party code\) is a part of life in React programming: 

### Example

[Bootstrap](https://www.getbootstrap.com) consists of pre-packaged HTML and CSS that take care of your structure, styling and responsiveness of a web app, while we focus on programming ... 

...to add it on React via Terminal, let's go to the project folder and then enter:

```bash
$ npm install bootstrap
```

Then, let's open a React .js file where we wish to have Bootstrap:

```jsx
import React from 'react';

...

// bootstrap
import 'bootstrap/dist/css/bootstrap.css';

...
```

\(The `node_modules` folder would include the `bootstrap` folder and it will form a part of the dependencies list in `package.json`\)

Now, we can use Bootstrap classes in JSX `className` attributes!

