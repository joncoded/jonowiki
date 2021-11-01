---
description: splitting function arguments rather than cooking some spicy dish
---

# JavaScript currying

{% hint style="info" %}
The name "currying" is named after the mathematician [Haskell Curry](https://en.wikipedia.org/wiki/Haskell_Curry)
{% endhint %}

**Currying** exists in other programming languages \(as well as in mathematics\) and has to do with splitting the arguments of functions, into functions with one argument each...

...so here we have an example without currying: 

```javascript
// non-curried way
let entity = (attr1, attr2, attr3) =>
  attr1 + ' is the ' + 
  attr2 + ' guy who wears the ' + 
  attr3 + '!'

console.log(entity('Kyle', 'American', 'orange jacket'));
// Kyle is the American guy who wears the orange jacket
```

With currying, we can split the arguments up into smaller functions:

```javascript
// curried way
let curriedEntity = 
    attr1 =>
      attr2 =>
        attr3 =>          
          attr1 + ' is the ' + 
          attr2 + ' guy who wears the ' + 
          attr3 + '!'

/* we can create a person */

let person = curriedEntity('Kyle')
let nationalizedPerson = person('American')
let uniformedPerson = nationalizedPerson('orange jacket')

console.log(uniformedPerson)
// Kyle is the American guy who wears the orange jacket

/* now we can create another person */

person = curriedEntity('Hans')
nationalizedPerson = person('German')
uniformedPerson = nationalizedPerson('tall army boots')

console.log(uniformedPerson)
// Hans is the Germany guy who wears the tall army boots
```

### Another example

Using this dataset:

```text
const entities = [
  { name: 'kyle', jacket: 'orange'},
  { name: 'eric', jacket: 'red'},
  { name: 'stan', jacket: 'brown'},
  { name: 'kenny', jacket: 'orange'},
]
```

Without currying, we can use this way to filter by an attribute: 

```javascript
const filterEntitiesByJacket = (queriedJacket) =>
  entities.filter(queriedEntity => 
    queriedEntity.jacket === queriedJacket
  )

console.log(filterEntitiesByJacket('orange'))

/*
[Object { 
  element: "orange", name: "kyle"
}, Object {
  element: "orange", name: "kenny"
}]
*/
```

With currying, we can do something like this: 

```javascript
const hasJacket = 
  (queriedJacket) => 
    (queriedEntity) => 
      queriedEntity.jacket === queriedJacket

const filterEntitiesByJacket = entities.filter(hasJacket('orange'))

console.log(filterEntitiesByJacket)

/*
[Object { 
  element: "orange", name: "kyle"
}, Object {
  element: "orange", name: "kenny"
}]
*/
```

The currying way seems longer but it enables a greater separation of concerns in the long run!

### Reference

\_\_[_Fun Fun Function_](https://www.youtube.com/channel/UCO1cgjhGzsSYb1rsB4bFe4Q) _explained this way back in 2015 \(although he used dependencies\) but it still remarkably applies today:_ 

{% embed url="https://www.youtube.com/watch?v=iZLP4qOwY8I" %}



