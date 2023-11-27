---
description: promising to do one thing before another
---

# 🚧 JavaScript promises

{% hint style="warning" %}
cleanup needed
{% endhint %}

### **Promises made and kept!**

```javascript
const getYouTubeVideoPromiseMaker = () => new Promise (resolve => {
  /* irl, imagine this to be some function that grabs popular videos
  and then sees in the next Promise if they are being tweeted
  on YouTube */
  setTimeout(() => {
    console.log("videos found!")
    // videos returned
    resolve({ videos: ['video1', 'video2', 'video3'] })
  }, 2000)
})

const getTweetPromiseMaker = (videos) => new Promise ((resolve, reject) => {
  setTimeout(() => {
    
    if (videos.length > 0) {        
    /* irl, this block would check if there are videos
        that appear on tweets (or something like that) 
        and then grab those tweets but we'll just 
        resolve those tweets for simplicity's sake */
      // tweets returned
      resolve({ tweets: ['text1', 'text2', 'text3'] })
    } else {
      // no tweets, obviously, if there are no videos
      reject(console.log('no tweets'))
    }

  }, 1000)
})

// async because we want things to await!
async function displayTweetsWithVideos() {
  // get videos and put them into yt variable
  const yt = await getYouTubeVideoPromiseMaker()
  // use yt's resolved object's "videos" property
  const tw = await getTweetPromiseMaker(yt.videos)
  // if tw resolved, show tweets
  console.log(tw.tweets)
}

displayTweetsWithVideos()
```

In the above, we can refactor the code further and make a variable like this:

```javascript
const getYouTubeVideoPromiseExecutor = () => resolve => {
  /* irl, imagine this to be some function that grabs popular videos
  and then sees in the next Promise if they are being tweeted
  on YouTube */
  setTimeout(() => {
    console.log("videos found!")
    // videos returned
    resolve({ videos: ['video1', 'video2', 'video3'] })
  }, 2000)
}
```

So then we have the expressive:

```javascript
const getYouTubeVideoPromiseMaker = () 
=> new Promise (getYouTubeVideoPromiseExecutor)
```
