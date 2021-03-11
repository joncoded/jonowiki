# JavaScript string interpolation

{% hint style="warning" %}
This requires JavaScript ES6 and beyond
{% endhint %}

When concatenating strings with variables in old JavaScript, we can encounter things like this:

```javascript
var x = 'something'
var y = 'another thing'
var z = 'yet another thing'

var sentence = 'We would like' + x + 'and then' + y + 'and also' + z + '!';
```

Obviously, this can become very error-prone with all these 'plusses' and 'quotations'!

However, in ES6, we could use something called **string interpolation** to make it more readable:

```javascript
const x = 'something'
const y = 'another thing'
const z = 'yet another thing'

const sentence = `We would like ${x} and then ${y} and also ${z}!`
```

Note the one key thing of using backticks \(the ````` symbol\) instead of quotations when using string interpolation! The sentence variable now reads more like a sentence!



