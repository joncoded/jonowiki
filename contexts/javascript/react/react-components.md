# React components

In the last page we had:

{% code title="index.js" %}
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

To add a sub-component, let's add a folder in `src` called `Components`, then add a sub-folder in `Components` called `Subcomponent` and then finally add a file called `Subcomponent.js` (by convention, we would name this .js file the same as its folder):

* src
  * Components
    * Subcomponent
      * Subcomponent.js

Then:

{% code title="Subcomponent.js" %}
```jsx
import React from 'react'

function Subcomponent() {
    render() {
        return(<div>I am a Subcomponent!</div>)
    }
}

export default Subcomponent
```
{% endcode %}

To use the new `Subcomponent`, we would add lines into index.js:

{% code title="index.js" %}
```jsx
import React from 'react'
import './index.css'

// Subcomponent
import './Components/SubComponent';

class App extends React.Component {
  return (
    <div className="App">
			<h1>Hello URL!</h1>
			{/* Subcomponent */}
			<SubComponent />
    </div>
  );
}

export default App;
```
{% endcode %}
