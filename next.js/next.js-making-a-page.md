---
description: creating a single-page static website with Next.js
---

# Next.js making a page

### Building the page component

Let's go to the `/pages/index.js` file and reduce the code down to the bare minimum:

{% code title="/pages/index.js" %}
```jsx
import Head from 'next/head'
import styles from '../styles/Home.module.css'

export default function Home() {
  return (
    <div className={styles.container}>
      <h1>The next Next page!</h1>
    </div>
  )
}
```
{% endcode %}

When we run `npm run dev` we will see:

![](../../../.gitbook/assets/docs-next-001.png)

Notice how we used `className={styles.container}` for the root `<div>` - Next.js allows us to use CSS class names in our JSX, through the `styles` variable!

### Using our Head

We imported `Head` which allows us to configure our site's descriptive tags such as `<title>` and `<meta>` for improved SEO, e.g.:

```jsx
import Head from 'next/head'
import styles from '../styles/Home.module.css'

export default function Home() {
  return (
    <div className={styles.container}>
      <Head>
        <title>Custom Next!</title>
      </Head>
      <h1>The next Next page!</h1>
      <p><a href="about">About</a></p>
    </div>
  )
}
```

So instead of the browser tab showing just "localhost:3000" (or whatever the URL is), it will show the contents of our `<title>` tag with such ease!

![](../../../.gitbook/assets/docs-next-003.png)

### Review

So now, with the React JSX knowledge we know, we can pretty much now build out a _static, single-page Next.js website_!
