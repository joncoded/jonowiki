# Mapbox with React (introduction)

[Mapbox](https://www.mapbox.com) allows us to display a customized map on our own websites (provided we stay within limits) - to do so, we need:

### Prerequisites

* [Mapbox access token](https://account.mapbox.com)
* [Mapbox GL](https://docs.mapbox.com/mapbox-gl-js/api/) Javascript library
* Node.js with npm installed
* [GitHub](https://github.com) account (optional for deployment)
* Some React and JavaScript experience

{% hint style="danger" %}
Please ensure that only the desired website URL(s) may use your **Mapbox access token**!
{% endhint %}

### Setup

In your project folder:

* Create a `package.json` file at the root
* Create a `public` folder for the final product and create the files:
  * `index.html` where the final product will display
  * `index.css` to house the styles for index.html
* Create an `src` folder and create the files to compile:
  * `index.js` for all the React logic

#### Setting up `package.json`

* Copy and paste this into `package.json`
  * of course: change any text that includes the (bracketed text):

```javascript
{
    "name": "(project name)", 
    "description": "(the map project's description)",
    "version": "1.0.0",
    "main": "src/index.js",
    "dependencies": {
        "mapbox-gl": "^2.1.1",
        "react": "^17.0.0",
        "react-dom": "^17.0.0",
        "react-scripts": "^4.0.1",
        "worker-loader": "^3.0.7"
    },
    "scripts": {
        "start": "react-scripts start"
    },
    "browserslist": [
        "defaults"
    ],
    "author": "(your name)",
    "license": "MIT",
    "homepage": "(where you will upload this to)"
}
```

{% hint style="warning" %}
Note that the properties of the `dependencies` may require updating for future versions!
{% endhint %}

#### Installing dependencies

* Similar to any node app, we begin by running the command: `npm install`
  * (a `package.json` file will automatically generate)

### Creating the HTML index file

* We'll go into the `public` folder and open the `index.html` file
* The following lines will minimally setup our map interface:

```markup
<!DOCTYPE html>
<html lang="en">

  <head>

    <title>(our map project)</title>

    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    
    <link
    href="https://api.tiles.mapbox.com/mapbox-gl-js/v2.1.1/mapbox-gl.css"
    rel="stylesheet"
    />
    <link href="%PUBLIC_URL%/index.css" rel="stylesheet" />

  </head>

  <body>

    <div id="app"></div>

  </body>

</html>
```

{% hint style="info" %}
If the above looks unfamiliar, please [review the HTML section about the \<head> tag](https://github.com/joncoded/jonsdocs/blob/main/code/webdev/mapbox-with-react/broken-reference/README.md) 👨‍💻
{% endhint %}

React will:

* use Mapbox's `mapbox-gl.css` to provide basic styling for the map (lines 11-14)
* use our `index.css` for any custom styles we may have for the map (line 15)
* render the map all within the `<div id="app"></div>` of the HTML above (line 21)

### Creating the React front-end logic

* We'll now go into our `src/index.js` file:

{% code title="src/index.js" %}
```jsx
import React, { useRef, useEffect, useState } from 'react'
import ReactDOM from 'react-dom'

import mapboxgl from 'mapbox-gl/dist/mapbox-gl-csp'
import MapboxWorker from 'worker-loader!mapbox-gl/dist/mapbox-gl-csp-worker'
mapboxgl.workerClass = MapboxWorker
mapboxgl.accessToken = 'YOUR_MAPBOX_ACCESS_TOKEN'

const Map = () => {
    // map logic goes here
}

ReactDOM.render(<Map />, document.getElementById('app'))
```
{% endcode %}

* Unpacking the above:
  * the first two lines deal with React
  * the next four lines actually deal with Mapbox
    * remember to change `YOUR_MAPBOX_ACCESS_TOKEN`
  * finally, we have our app as the remainder of the file
    * all that React code will export into the `<div id="app"></div>` of the `index.html` file

### Initializing the map defaults

* Now that we have our React Mapbox workspace setup, we still have to give our map with default values for geographical coordinates, zoom level and so on, in `src/index.js`:

{% code title="src/index.js" %}
```jsx
import React, { useRef, useEffect, useState } from 'react'
import ReactDOM from 'react-dom'

import mapboxgl from 'mapbox-gl/dist/mapbox-gl-csp'
import MapboxWorker from 'worker-loader!mapbox-gl/dist/mapbox-gl-csp-worker'
mapboxgl.workerClass = MapboxWorker
mapboxgl.accessToken = 'YOUR_MAPBOX_ACCESS_TOKEN'

const Map = () => {

    /* new code here */
    const mapContainer = useRef()
    const [lat, setLat] = useState(43.6532)
    const [lng, setLng] = useState(-70.9)
    const [zoom, setZoom] = useState(9)
    
}

ReactDOM.render(<Map />, document.getElementById('app'))
```
{% endcode %}

* So, within that Map component, we have just set up our default latitude, longitude and zoom level

### Initializing the map

* We will then kick-start our map, again in `src/index.js`:

{% code title="src/index.js" %}
```jsx
import React, { useRef, useEffect, useState } from 'react'
import ReactDOM from 'react-dom'

import mapboxgl from 'mapbox-gl/dist/mapbox-gl-csp'
import MapboxWorker from 'worker-loader!mapbox-gl/dist/mapbox-gl-csp-worker'
mapboxgl.workerClass = MapboxWorker
mapboxgl.accessToken = 'YOUR_MAPBOX_ACCESS_TOKEN'

const Map = () => {

    const mapContainer = useRef()
    const [lat, setLat] = useState(43.6532)
    const [lng, setLng] = useState(-70.9)
    const [zoom, setZoom] = useState(9)
    
    /* new code here */
    useEffect(() => {

        const map = new mapboxgl.Map({
            container: mapContainer.current,
            style: 'mapbox://styles/mapbox/streets-v11',
            center: [lng, lat],
            zoom: zoom
        })

        return () => map.remove()

    }, [])
    
    /* new code here */
    return (
        <>
            <div className="map-container" ref={mapContainer} />
        </>
    )
    
}

ReactDOM.render(<Map />, document.getElementById('app'))
```
{% endcode %}

* In the above, we implemented two things:
  * a `useEffect` hook that ensures the rendering happens at the right time
  * a `return` statement that will provide a container for the map
    * recall the `useRef` hook at the top of the `Map` functional component

### Styling the map

* Lastly, we just need to add some CSS in `public/index.css`

```css
.map-container {
  position: absolute;
  top: 0; right: 0; left: 0; bottom: 0
}
```

### Running the map

* OK, let's test the map!
* Go back to Terminal into the project folder and type `$ npm start`
* When we see a message that says "Compiled successfully!" we can then:
  * take note of the addresses where we can view in the browser
  * go to the browser and have a look

![](../../../.gitbook/assets/docs-react-mapbox-001.png)

### Deployment

* Please refer to the [previous page](https://github.com/joncoded/jonsdocs/blob/main/code/webdev/mapbox-with-react/broken-reference/README.md) to see how to make this map appear on the Internet:
