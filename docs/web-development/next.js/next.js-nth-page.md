---
description: routing to and from the second page (and beyond)
---

# 🔢 Next.js nth page

Websites often have more than one page, so let's have a look at **routing:**

* Routing just means moving from one "view" to another,  most often by:
  * clicking on a link to get to another page
  * changing the URL on the browser's address bar
* With React, we would do this by writing out a whole bunch of JSX to determine which route (URL) goes where
* With Next.js, we create "routes" simply by using _**folders**_ and _**files**_
  * like in the old HTML-only days!

### Next.js routing

* In the `app` folder, we would create a new folder, let's call it `about`
* Then, inside about, we would crate a new file called `page.tsx`
* This will create the `/about` route (😄 does this rhyme for you?)

```
project
- app
- - about
- - - page.tsx
```

{% hint style="warning" %}
Unfortunately, due to Next.js rules, we cannot rename `page.tsx`
{% endhint %}

* In the code editor, open `page.tsx`
* Paste this in and save the file:

{% code title="app/about/page.tsx" %}
```jsx
export default function About() {

  return ( 
    <div>
      <h1>About</h1>
      <p>This is my about page!</p>
    </div>  
  )

}
```
{% endcode %}

#### See this in action

* In Terminal, `npm run dev`&#x20;
* Let's go to `localhost:3000/about`&#x20;
  * (replace the port number 3000 if needed)
* We will see the new page!

### Linking between pages

We can then link between pages by using the `Link` component that comes with Next.js:

* Import `Link` as in line 1
* Add the `Link` tag as in line 9

{% hint style="info" %}
We can use the `<a>` tag but we will find out later why we use `<Link>`&#x20;
{% endhint %}

{% code title="app/about/page.tsx" lineNumbers="true" %}
```jsx
import Link from "next/link"

export default function About() {

  return ( 
    <div>
      <h1>About</h1>
      <p>This is my about page!</p>
      <p><Link href="/">Go back to home page</Link></p>
    </div>  
  )

}
```
{% endcode %}

We can also use the Next.js `<Link>` tag just like HTML `<a>` tag (with the `href` and `target` attributes that we know!)

#### Linking to any page

To link the `about` (or any) page from the home page, we can thus do the same:

{% code title="app/page.tsx" %}
```jsx
import Link from "next/link"

export default function Home() {
  return (
    <div>
      <h1 className="text-2xl">Home</h1>
      <Link href="/about">About</Link>    
    </div>
  )
}
```
{% endcode %}
