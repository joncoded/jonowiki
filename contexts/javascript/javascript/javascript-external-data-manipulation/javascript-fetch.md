# JavaScript fetch(ing data)

This handy function called `fetch()` allows us to:

* request access to an endpoint
* receive, after the request finalizes,
  * a response (or error) from that endpoint
  * log, if a network error occurred, an error message
* obtain the response _data_ in JSON format
* display the data, if available, on the front-end

### GET requests

```javascript
// fill in endpoint here
const url = ''; 

// GET or send error
// if GET successful, return JSON response
fetch(url)
.then(response => {
  if (response.ok) {
    return response.json();
  }
  throw new Error('Request failed!');
}, networkError => {
  console.log(networkError.message);
})
.then(jsonResponse => {
  return jsonResponse;
});
```

### POST requests

With POST requests, we add one more argument to fetch - the data we will POST:

```javascript
// fill in endpoint here
const url = '';

// provide POSTing data as JSON object here
const dataBody = { whatever: "here" };

// set up the data payload
const data = { method: 'POST', body: dataBody };

// POST or die
// if POST successful, return the confirmation as JSON
fetch(url, data)
.then(response => {
  if (response.ok) {
    return response.json();
  }
  throw new Error('Request failed!');
}, networkError => {
 console.log(networkError.message);
})
.then(jsonResponse => {
  return jsonResponse;
});
```

### Using async and await (ES8)

ES8 allows us to use `async` and `await` keywords:

#### GET requests

Note the `async` before the function declaration and the two uses of \`await\`, one for the fetch response and then another one for the JSON response:

```javascript
// fill in endpoint here
const url = '';

const getData = async () => {
  try {
    const response = await fetch(url);
    if (response.ok) {
     const jsonResponse = await response.json();
    }
    throw new Error('Request failed!');
  } catch (error) {
    console.log(error);
  }
}
```

#### POST requests

The POST request follows the same pattern as the GET but with an additional argument inside the fetch for the data that we will POST:

```javascript
// fill in endpoint here
const url = ''; 
const dataBody = { whatever: "here" };

const getData = async () => {
  try {
    const response = await fetch(url, {
      method: 'POST',
      body: dataBody
    });
    if (response.ok) {
      const jsonResponse = await response.json();
      return jsonResponse; 
    }
    throw new Error('Request failed!');
  } catch (error) {
    console.log(error);
  }
}
```

The `async` keyword creates a function that returns a \`Promise\` to `await` for responses from the API, before we proceed along the code blocks ... then, we can simply handle any errors and place any valid responses into `getData`!
