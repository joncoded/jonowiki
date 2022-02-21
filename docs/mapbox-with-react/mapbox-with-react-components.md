# Mapbox with React (components)

To create a component located within [the map from the previous section](https://github.com/joncoded/jonsdocs/blob/main/code/webdev/mapbox-with-react/broken-reference/README.md):

* Continue working inside the `useEffect` function to add new functionality
* Continue working inside the `return` statement to show this new functionality

### Adding new functionality

Let's go back to `src/index.js` continuing off inside the `useEffect` from [this point](https://github.com/joncoded/jonsdocs/blob/main/code/webdev/mapbox-with-react/broken-reference/README.md):

{% code title="src/index.js" %}
```jsx
/* make sure to include omitted code above useEffect */

useEffect(() => {

    const map = new mapboxgl.Map({
        container: mapContainer.current,
        style: 'mapbox://styles/mapbox/streets-v11',
        center: [lng, lat],
        zoom: zoom
    })

    /* new code here */
    map.on('move', () => {
        setLat(map.getCenter().lat.toFixed(4))
        setLng(map.getCenter().lng.toFixed(4))
        setZoom(map.getZoom().toFixed(2))
    })
    /* end of new code */

    return () => map.remove()

}, [])

/* make sure to include omitted code below useEffect */
```
{% endcode %}

We have added a new listener to the `map` , which, when "touched", changes its:

* longitude
* latitude
* zoom level

### Displaying new functionality

Now, we should display the map's changing information in the `return` statement:

{% code title="src/index.js" %}
```jsx
/* make sure to include omitted code above the return */

return (
    <>
        {/* new code here */}
        <div className="sidebar">
            Latitude: {lat} | Longitude: {lng} | Zoom: {zoom}
        </div>
        {/* end of new code */}
        <div className="map-container" ref={mapContainer} />
    </>
)

/* make sure to include omitted code below the return */
```
{% endcode %}

Also in the CSS file:

{% code title="public/index.css" %}
```css
.map-container {

  position: absolute;
  top: 0; right: 0; left: 0; bottom: 0;

}

/* new class */
.sidebar {

  background-color: rgba(35, 55, 75, 0.9);
  border-radius: 4px;

  color: #ffffff;
  font: 18px/27px monospace;

  margin: 15px;
  padding: 7.5px 15px;
  
  z-index: 1;
  position: absolute;
  top: 0;
  left: 0;
  
}
```
{% endcode %}

### Result

The map should have a small "bar" at the top left which displays the latitude, longitude and zoom level:

![](<../../.gitbook/assets/ 2021-03-13 at 14.37.41.png>)

From this, we can then position all sorts of super-imposed component onto the map such as notes, statistics, legends and beyond!
