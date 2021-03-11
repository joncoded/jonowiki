# JavaScript functions returning multiple values

We can `return` more than one object from a function: 

```javascript
function getPlace() {

 // assume these come from an API or some dynamic source
 let country = 'Canada', city = 'Toronto'
 
 // we can return both variables as such:
 return [country, city] 
 
}

let place = getPlace()
console.log(place[1], place[0])
// "Toronto" "Canada"
```

In ES6, we can use destructuring as such, to make using this array easier: 

```javascript
const [country, city] = getPlace()
console.log(`${city}, ${country}`)
// "Toronto, Canada" 
```



