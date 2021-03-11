---
description: getting ourselves ready with Next.js
---

# Next.js setup

### Pre-requisites

* Ability to run UNIX commands on a [command-line interface](../workspace/command-line.md)
* You know that `$` means the prompt of a Terminal command line 
* You have [npm](https://www.npmjs.com/) installed \(check by entering  `$ npm -v` on Terminal\)
  * If it reveals a version number, then you're okay
  * If not:
    * `$ npm install -g n`\(let the installation of the installer run\)
    * `$ n stable` \( to get the latest stable version of node and npm\)
* Knowledge of JavaScript and JSON
* Some knowledge of React will help

### Installation

On **Terminal** try: 

```text
$ npx create-next-app appname
```

...replacing `appname` with the name of our choice...

We may get a prompt to install `create-next-app` \(just enter `y` for yes\) and then the boilerplate app will install!

### Working with Next.js

Let's go into the code: 

```text
$ cd appname
```

We will notice that the folder structure looks like: 

{% tabs %}
{% tab title="root" %}
`package.json` will look something like this: 

```text
{
  "name": "codenext",
  "version": "0.1.0",
  "private": true,
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start"
  },
  "dependencies": {
    "next": "10.0.8",
    "react": "17.0.1",
    "react-dom": "17.0.1"
  }
}
```

Pretty straightforward looking! Looking at the `dependencies` we see that Next.js only really needs React, React-DOM and Next itself!

Other files included are also pretty standard stuff: 

* `README.md`
* `package-lock.json`
* `gitignore`
{% endtab %}

{% tab title="pages" %}
This folder kind of acts like the `src` folder in a traditional React app...

A mock API comes with the sample app in this folder:

* `/pages/api/hello.js`

A boilerplate layout file set in the `/pages/` root:

* `/pages/_app.js` - the **container** for our pages
* `/pages/index.js` - **our home page**!
{% endtab %}

{% tab title="public" %}
The built code as well as any hard assets go here - as the boilerplate has:

* `favicon.ico` - so you don't have to make one if you don't want to
* `vercel.svg` - Next's equivalent of that atomic logo
{% endtab %}

{% tab title="styles" %}
CSS goes here! Next comes with: 

* `/styles/globals.css` - the reset sheet
* `/styles/Home.module.css` - the style sheet for the home page

{% hint style="info" %}
Note that when we import a `styles` file, we must give it the same name as the component + `.module.css,`e.g.

In `pages/index.js` we saw that it had a `Home()` function, so the style file name to import would be `Home.module.css`
{% endhint %}
{% endtab %}
{% endtabs %}

As we can see from the above walkthrough, Next.js starts off pretty minimal and we like minimal!

### Making our first build

To create our deployment-friendly version, we run:

```text
$ npm run build
```

We will then notice that a `.next` folder appears in our project folder, ready for launch!

### Seeing our build

Let's see what the boilerplate app looks like:

```text
$ npm run dev
```

On `localhost:3000` a sample Next.js website will appear!

