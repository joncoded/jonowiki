---
description: getting ourselves ready with Next.js
---

# ⚙ Next.js setup

On this page, we will have Next.js setup with only&#x20;

* **npm commands** on the Terminal
* [**VS Code**](../../workspace/)

### Installation

* Create a new folder on your local machine
* In Terminal, enter the following:

{% code fullWidth="false" %}
```bash
npm init -y
```
{% endcode %}

* Then, install [**React**](../) + [**TypeScript**](../../typescript.md) + **Next**:

{% code fullWidth="false" %}
```bash
npm install --save react react-dom typescript next
```
{% endcode %}

* Then, in `package.json`:

{% code fullWidth="false" %}
```json
...
"scripts": {
    "dev": "next dev",
    "build": "next build", 
    "start": "next start",
    "lint": "next lint"
}
...
```
{% endcode %}

### Folders

* Create a folder called `app` at the root level of the project folder

#### Public folder (optional)

* Create a folder called `public` also at the root level to store static assets
  * we can then refer a file such as `public/logo.png` as simply `/logo.png`

### Tailwind (optional)

* _Optionally_, we could also install **Tailwind CSS**, a styling framework with [these instructions](https://tailwindcss.com/docs/guides/nextjs), i.e.

```
npm install -D tailwindcss postcss autoprefixer
```

* Configure Tailwind with the file:&#x20;

{% code title="tailwind.config.js" %}
```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./app/**/*.{js,ts,jsx,tsx,mdx}",
    "./app/*.{js,ts,jsx,tsx,mdx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
{% endcode %}

* In the `app` folder, add a `global.css` file:

{% code title="app/global.css" %}
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```
{% endcode %}

* Start the Tailwind CLI build process in Terminal

```
npx tailwindcss init -p
```

We will test the Tailwind styles in the next page when we build our first page!
