# Retrieving a query string value from an URL with JavaScript

If for some reason we wish to extract a query string value from an URL with JavaScript, here's the play-by-play: 

```javascript
// get query string parameter's value based on parameter's key
const getURLParam = pKey => {
  
  // declare a container variable for the parameter's value 
  let pValue = ""

  // current URL
  const url = window.location.href

  // does the URL have a ? (i.e. does it have parameters?)
  if ( url.indexOf("?") > -1 ) {

    // if so, take the part of the URL to the right of the ?
    const pString = url.substr(url.indexOf("?"))

    // split that part using & as a separator into an array
    const pArray = pString.split("&")

    // look through that array
    for (let i = 0; i < pArray.length; i++) {

     // look for the query string key in the array 
     if (pArray[i].indexOf(pKey + "=") > -1) {

        // split pKey, =, and pValue
        const pPair = pArray[i].split("=")
        // take the query string value
        pValue = pPair[1]
        // exit loop
        break

     }

   }

  }

  // return the parameter's value
  return pValue

}
```

The above code without the comments: 

```javascript
const getURLParam = pKey => {
  
  let pValue = ""
  const url = window.location.href

  if (url.indexOf('?') > -1) {
    
    const pString = url.substr(url.indexOf('?'))
    const pArray = pString.split('&')

    for (let i = 0; i < pArray.length; i++) {

      if (pArray[i].indexOf(pKey + '=') > -1) {
      
        const pPair = pArray[i].split('=')
        pValue = pPair[1]
        break
      
      }

    }

  }

  return pValue

}
```

