---
description: a framework for React that enables server-side rendering
---

# ➡ Next.js

With a **traditional React app**:

* all the loading and rendering of an application gets done on the client
  * e.g. the browser
* however, this makes it bad for SEO
  * it only sees inside your UI render and not the tags inside `<head>`

With a [**Next.js**](https://nextjs.org) **app**:

* The first page load gets rendered by the server and stays cached there
* Easier page routing and error pages
* Simple page transitions
* Quicker deployment (with [**Vercel**](https://vercel.com/docs))
