---
description: applying more of our knowledge of Next.js layout files
---

# Next.js headers

Instead of "hard-coding" things into `/components/Layout.js`  we could better apply our knowledge by **building more sub-components** to replace what we see here:

```jsx
import Navigation from './Navigation'
import styles from '../styles/Layout.module.css'

const Layout = ({children}) => {
  return (
    <>
      <Navigation />
      <div className={styles.container}>
        <main className={styles.main}>
          <h1>welcome to CODENEXT</h1>
          {children}
        </main>
        <footer className={styles.footer}>
          &copy; current year
        </footer>
      </div>

    </>

  )
}

export default Layout
```

We might easily see that the `<h1>welcome to CODENEXT</h1>` part deserves its own component - just to make our code that much cleaner!

### Creating the header component

{% code title="/components/Header.js" %}
```jsx
import headerStyles from '../styles/Header.module.css'

const Header = () => {
  return (
    <>
      <h1>Welcome to CodeNEXT</h1>
    </>
  )
}

export default Header
```
{% endcode %}

As we can see, having this in a separate file brings focus and concentration to this part of the layout!

### Styling the header component

Let's just take a part of the Layout.module.css that has to do with `.title` and `.description` and create a new CSS module:

{% code title="/styles/Header.module.css" %}
```css
.title a {
  color: #0070f3;
  text-decoration: none;
}

.title a:hover,
.title a:focus,
.title a:active {
  text-decoration: underline;
}

.title {
  margin: 0;
  line-height: 1.15;
  font-size: 4rem;
}

.title,
.description {
  text-align: center;
}

.description {
  line-height: 1.5;
  font-size: 1.5rem;
}
```
{% endcode %}

### Using the header component

Back to the Layout:

{% code title="/components/Layout.js" %}
```jsx
import Navigation from './Navigation'

// remember to import the header
import Header from './Header'

import styles from '../styles/Layout.module.css'

const Layout = ({children}) => {
  return (
    <>
      <Navigation />
      <div className={styles.container}>
        <main className={styles.main}>
          {/* replaced the h1 tag! */}
          <Header />          
          {children}
        </main>
        <footer className={styles.footer}>
          &copy; current year
        </footer>
      </div>

    </>

  )
}

export default Layout
```
{% endcode %}

Hurray! We have successfully added a new sub-component to our layout!

![](../../../.gitbook/assets/next-007.png)

So we can see a recurring pattern:

* We **create** a sub-component in the `/components` folder
* We **style** the sub-component with its own `.module.css` file
* We **use** the sub-component in `/components/Layout.js`

Intuitive, isn't it?

