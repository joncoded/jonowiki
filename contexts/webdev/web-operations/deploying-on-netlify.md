# Deploying on Netlify

Other ways exist to **deploy** a web app \(such as Heroku and GitHub pages\) but let's use [Netlify](http://netlify.com/)...

### Installing Netlify

* Install Netlify on the same folder as your app's folder on Terminal

```text
$ npm install netlify-cli
```

### "Building" the app before deployment

* If we have not created a "build" \(the compiled version\) for our app yet:

```text
$ npm run build
```

### Deploying the app

* Then we deploy by simplying entering the command \(notice the [npx](https://stackoverflow.com/questions/50605219/difference-between-npx-and-npm)\)

```text
$ npx netlify deploy
```

* This will open up Netlify on the browser asking for Authorization: 
  * grant the access and close the browser tab
* Go back to the Terminal and answer Netlify's questions with the following:

```text
? What would you like to do? + Create & configure a new site
? Team: (username)'s team
? Site name (optional): (App's name)
? Publish directory build
```

Check the app in the URL in "Website Draft URL"

* If all looks good then:

```text
$ npx netlify deploy --prod
```

* Finally, the deployment will happen on a "Website URL"
* Check out that Website URL and see if it worked!

Furthermore, you could go to:  

https://app.netlify.com/sites/{your app-url here}/overview 

...to _**set up a custom domain**_ and _**secure your site with HTTPS!**_

To **re-deploy** an app, repeat these steps starting from the _second_ step of this article!

### Review <a id="block-3981a9a5-5fcd-47d1-a49b-93c867e5d9fe"></a>

We can sum up the Netlify deploy process as the following:

* npm run build
* npx netlify deploy
* npx netlify deploy --prod

![What the Netlify deployment process actually looks like in Terminal!](https://www.joncoded.com/wp-content/uploads/netlify.jpg)

### References <a id="block-639d2aeb-ff73-44b3-8a02-1bb6f12a9fc2"></a>

* [Chris Dixon](https://www.youtube.com/watch?v=QnNdneKQR9M) \(YouTube\)

