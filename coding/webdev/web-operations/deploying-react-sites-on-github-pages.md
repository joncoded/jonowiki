# Deploying React sites on GitHub pages



### Connecting the local repository with the remote

If we have not yet already, let us run these commands in **Terminal**:&#x20;

* `$ git init`&#x20;
* `$ git remote origin add (remote url on github)`
* `$ git add -A`
* `$ git commit -m "pushing initial version"`
* `$ git push origin master`

### Installing the gh-pages utility

Then, let's set up the `gh-pages` package as a "dev dependency":

* `$ npm install gh-pages --save-dev`

### Editing package.json for deployment

* Add this property to the `package.json` file, replacing `yourname` and `yourrepo` with the obvious:

```
"homepage" : "https://yourname.github.io/yourrrepo"
```

* Then, within the `scripts` property:

```
"scripts" : {
    "predeploy" : "npm run build", 
    "deploy" : gh-pages -d build",
    ...
}
```

Overall, the `package.json` file should look something like:&#x20;

```
{
  "homepage": "https://joncoded.github.io/whatever", 
  "name": "reactetc",
  "description": "some react stuff",
  "version": "1.0.0",
  "main": "src/index.js",
  "dependencies": {
    "react": "^17.0.0",
    "react-dom": "^17.0.0",
    "react-scripts": "^4.0.1",
  },
  "scripts": {
    "predeploy" : "npm run build", 
    "deploy" : gh-pages -d build",
    "start": "react-scripts start",
    "build": "react-scripts build"
  },
  "browserslist": [
    "defaults"
  ],
  "author": "joncoded",
  "license": "MIT"
}
```

### Deploying

* In Terminal, we can run just one-liner command:&#x20;

```
$ npm run deploy
```

### Setting up the remote repository for GitHub pages

On GitHub:

* Create a new remote repository (and note down its URL)
* Go into the repository's **Settings**
  * Go to the section **GitHub Pages**
  * Under **Source**
    * Pick** "Branch: gh-pages" **
      * leave the folder at** **/(root)
    * Save

Wait a few seconds or a few minutes to see the page live on yourname.github.io/yourrepo

### **Re-deployment**

For every time that we wish to re-deploy, we just run these commands:

* `$ git add -A`
* `$ git commit -m "pushing another version"`
* `$ git push origin master`
* `$ npm run deploy`

{% hint style="success" %}
With [command aliasing](broken-reference) we can turn those four commands into probably just one or two commands!
{% endhint %}
