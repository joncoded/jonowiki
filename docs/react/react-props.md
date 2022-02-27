---
description: passing data from parent to child components
---

# React props

We streamline repetitive code with components, e.g. using subcomponent files:

```jsx
import React from 'react';

class SomeComponent extends React.Component {
  render() {
    return (
      /* repeating code begins */
      <div className="someComponent">            
        <h1 className="component-title">Title</h5>
        <p className="component-text">Text</p>
        <a href="#" className="btn btn-primary component-button">Go!</a>
      </div>
      /* repeating code ends */
    );
  }
}

/* this allows us to use the file wherever we import it */
export default SomeComponent;
```

This allows us to use the subcomponent as a mere JSX tag in the parent component:

```jsx
import React from 'react';
import './App.css';

/* insert this */
import SomeComponent from "./components/someComponent";

class App extends React.Component {
  render() {
    return (
      <div className="App">
        <div className="container">

            /* use the component (and repeat it) here! */
            <SomeComponent />
            <SomeComponent />
            <SomeComponent />
            <SomeComponent />
            <SomeComponent />
            <SomeComponent />

          </div>
        </div>
      </div>
    );
  }
}

export default App;
```

### Making each repetition "unique"

However, we can go one step further and make the code re-use even more dynamic by adding [HTML-like attributes](https://github.com/joncoded/jonsdocs/blob/main/a/1678/README.md) to each instance of `<SomeComponent />`:

```jsx
import React from 'react';
import './App.css';
import SomeComponent from "./components/someComponent";

class App extends React.Component {
  render() {
    return (
      <div className="App">
        <div className="container">
          <div className="row">
            /* behold these similar-but-unique components! */
            <SomeComponent name="Panda" job="President" />
            <SomeComponent name="Frog" job="Vice President" />
            <SomeComponent name="Rabbit" job="Treasurer" />
          </div>
          <div className="row">
            /* behold these similar-but-unique components! */
            <SomeComponent name="Horse" job="Officer" />
            <SomeComponent name="Dog" job="Developer" />
            <SomeComponent name="Snake" job="Analyst" />
          </div>
        </div>
      </div>
    );
  }
}

export default App;
```

### Giving props to the child

We thus pass attributes ("give props!"), like _parameters_, to the (child) component:

```jsx
import React from 'react';

class SomeComponent extends React.Component {
  render() {
    return (
      <div class="col-md-4">
        <div className="card">          
          <div className="card-body">
            /* give props to the child component */
            <h2 className="card-title">{this.props.name}</h2>
            <p className="card-text"><strong>{this.props.job}</strong></p>
            <a href="#" className="btn btn-primary">See more</a>
          </div>
        </div>
      </div>
    );
  }
}

export default SomeComponent;
```

This passing of attributes from the parent class to `{this.props.x}` in the child class would result in repeated components as such:

![subcomponents within components!](https://www.joncoded.com/wp-content/uploads/props-new.png)

...with each repetition having unique details 🐼
