---
description: creating a multi-page static website with Next.js
---

# Next.js routing

Next.js makes it easy to **create sub-pages** for our site ... all we need to do is create a new (React component) file within the `/pages` folder:

```
/pages
    /api
    _app.js
    index.js
    about.js <-- our new page, for example
```

### Creating the subpage

{% code title="/pages/about.js" %}
```jsx
import styles from '../styles/About.module.css'

const about = () => {
  return (
    <div className={styles.container}>
      <h1>About!</h1>
      <p><a href="/">Home</a></p>
    </div>
  )
}

export default about
```
{% endcode %}

### Styling the subpage

We could also create a companion CSS file as discussed in the [last page](next.js-making-a-page.md) - no pun intended!

{% code title="/styles/About.module.css" %}
```css
.container {
  min-height: 100vh;
  padding: 0 0.5rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
```
{% endcode %}

Voilà - the page gets created:

![](../../../.gitbook/assets/next-002.png)

The routing (`/about`) gets auto-magically created by Next.js and we now have our multi-page website!

{% hint style="info" %}
Exercise: "import `Head` from `next/head"` and insert a `<Head>` tag for the about page to improve its SEO :)
{% endhint %}
