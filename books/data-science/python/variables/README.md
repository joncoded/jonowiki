---
description: storing values into named spaces
---

# Variables

In mathematics, we learn in algebra that variables are symbols that store values ... the same happens in computer programming!

### Declaring variables

In Python, we simply start with a variable name and attach a value to it, separated by `=`:

```python
meaningful_variable_name = "This is a very meaningful value!"
```

The value would have either a pair of single quotes or double quotes...

... and there we have it: a variable name equivalent to a value!&#x20;

We have no need to place a keyword before the variable name (like in JavaScript or Java) - just declare away!

### Rules for variable names in Python

* must begin with a letter (a-z)
* must not start with a digit (0-9) but may contain them&#x20;
  * e.g. `route66` but not `5alive`
* can include an underscore (\_)
  * e.g. `meal_time`

### Using variables

Let's use the variable by printing its name (without quotation marks) to output its value:&#x20;

```python
meaningful_variable_name = "This is a very meaningful value!"
print(meaningful_variable_name)
```

Output:

```
This is a very meaningful value!
```

{% hint style="warning" %}
Note that if the variable has no value, it will throw an error!
{% endhint %}
