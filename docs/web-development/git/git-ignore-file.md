---
description: disallowing files onto the public repo
---

# Git ignore file

In most cases, we do not wish to include some files onto the public repo for at least two reasons:

* a file contains a personal information such as an ID number of API key
* the files are in the `node_modules` folder&#x20;

To prevent git from pushing these files onto the public repo, we create a special `.gitignore` file on the root folder of our projects!

### Files to exclude

Common to most projects and libraries are files containing **environment variables** and **node modules:**

{% code title=".gitignore" %}
```
.env
node_modules
```
{% endcode %}

### Why node\_modules?

We place `node_modules` in `.gitignore` not because we have anything to hide, but because:

* the folder tends to take up a lot of space!
* the `package.json` already lists which `node_modules` to install&#x20;
  * when someone decides to clone the repo and run `npm install`, the `package.json` will automatically unpackage the `node_modules` onto their local machine

### Library-specific .gitignores&#x20;

{% hint style="info" %}
This section is a stub and will expand as I work with other libraries!
{% endhint %}

#### Next.js

Exclude the `.next` folder because it will come with the `npm install`

```
.next
```
