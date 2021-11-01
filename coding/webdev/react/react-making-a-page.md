---
description: Starting with the most basic app (a display of text) and adding more stuff
---

# React making a page

Once we know to add a piece of text to our app, we can then move onto more complicated structures, embed rich media and dynamic content. So, first off: 

{% code title="src/App.js" %}
```jsx
import React from 'react';

import './index.css'; 

class App extends React.Component {
  return (
    <div className="App">
			<h1>Hello URL!</h1>
    </div>
  );
}

export default App;
```
{% endcode %}

In the above example, we've simply included one line \(the `<h1>` inside the `<div>` tag to test our text. If we save, we will see the change on `localhost:3000` in the browser: the words "Hello URL!" in a big bold font. 

Now that we can see that works, we can extend this skill to add any HTML we know: `<p>`aragraphs, `<img>`es, `<table>`s or whatever. That we can leave as an exercise. 

Yet, the real power of React comes with its _**dynamic**_ strength, which we shall hope to understand next.  

