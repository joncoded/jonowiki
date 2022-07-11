---
description: arranging components
---

# Next.js layouts

So now we have got the hang of creating pages in Next.js!

In order to avoid a lot of repetitive code, e.g. show a navigation bar, how do we abstract the layout? By creating layout files!

### Creating a layout

We begin by creating a new folder called `components` on the root of our project folder:

```
/ourapp
    /components <-- here we go
        Layout.js <-- and here we go
    /node_modules
    /pages
    /public
    /styles
    etc.
```

In that `components` folder we add a new file called `Layout.js`

{% code title="/components/Layout.js" %}
```jsx
const Layout = () => {
  return (
    <div>
      
    </div>
  )
}

export default Layout
```
{% endcode %}

{% hint style="info" %}
The file naming convention suggests that we use

* all lowercase letters for our **page file names**
* a first letter capital for our **component file names**
{% endhint %}

### Styling the layout

To appreciate the one-for-all purpose of the Layout, let's use one CSS file for the entire layout - we can:

* duplicate `/styles/Home.module.css` and rename it to `/styles/Layout.module.css`
* import `Layout.module.css` into `/components/Layout.js`
* use the class names in the CSS in the JS, like we did previously, for all pages on the site!

Let's change up the styles a bit so that we can see that our Layout will have worked:

{% code title="/styles/Layout.module.css" %}
```css
.container {
  background: rgb(255, 255, 0);
  min-height: 100vh;
  padding: 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.main {
  padding: 5rem 0;
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.footer {
  width: 100%;
  height: 100px;
  background: #000;
  color: #fff;  
  display: flex;
  justify-content: center;
  align-items: center;
}

/* as an exercise we can change the rest of the file */
```
{% endcode %}

The layout should have a brighter yellow background and a black footer ;)

#### Using the styles

```jsx
import styles from '../Layout.module.css'

const Layout = ({children}) => {
  return (
    <div className={styles.container}>
      <main className={styles.main}>
        <h1>welcome to CODENEXT</h1>
        {children}
      </main>
      <footer className={styles.footer}>
        &copy; current year
      </footer>
    </div>
  )
}

export default Layout
```

Notice how the `Layout` component takes in one parameter called `children` and then:

* this way, any page (i.e. `children`) can pass a lot of useful data up to the `Layout`
* the page's content will automatically populate in the `Layout` render
* we can also add in more JSX that will appear on every page that uses this Layout
  * ...much like server-side includes in PHP - but better!

### Using the layout

Finally, we go over to `/pages/_app.js`:

```jsx
import Layout from '../components/Layout'
import '../styles/globals.css'

function MyApp({ Component, pageProps }) {
  return (
    <Layout>
      <Component {...pageProps} />
    </Layout>
  )
}

export default MyApp
```

So, we:

* imported the `Layout`
* circumscribed the `Component` tag with the `<Layout>` tag

Also, we can simplify our index.js by removing the styles:

{% code title="/pages/index.js" %}
```jsx
import Head from 'next/head'

export default function Home() {
  return (
    <div>
      <Head>
        <title>Custom Next!</title>
      </Head>
      <h1>The next Next page!</h1>   
      <p>About</p>   
    </div>
  )
}
```
{% endcode %}

As well, our about.js can do without the styles:

{% code title="/pages/about.js" %}
```jsx
import Head from 'next/head'

const about = () => {
  return (
    <div>
      <Head>
        <title>About!</title>
      </Head>
      <h1>About!</h1>
      <p>Home</p>
    </div>
  )
}

export default about
```
{% endcode %}

Let's run it and see our pages have this wonderful uniformity!

![the root (home) page](../../../.gitbook/assets/docs-next-004.png)

![the "about" page](../../../.gitbook/assets/docs-next-005.png)

Now, we can almost _just build_ that dynamic multi-page website!
