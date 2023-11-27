---
description: doing "what-if" conditionals on Python
---

# Branching

### `if` statements

In Python, we can branch using a relatively understandable syntax:

```python
if myVariable == "value" :
    # do something
```

Keep in mind that:&#x20;

* `==` _compares_ the left side and the right side
* `=` simply _assigns_ the right side to the left side!

```python
# this will work
myVariable = 10 

# this will also work
if myVariable == 10: 
    print("myVariable is 10")
    
# this will not work, will print out a SyntaxError
if myVariable = 10:
    print("myVariable is 10")
```

#### Operators

In place of `==` we can also use `!=` `>=`, `>`, `<` and `<=`:

```python
if temperature >= 100 :
    print("Water will boil!")

if temperature > 0:
    print("Water will melt!")
    
if temperature < 0:
    print("Water will freeze!")
    
if temperature <= -273.15 : 
    print("No such temperature can exist!")
```

#### Logic

We can combine operations with the `and` (as well as the `or` and `not`) keywords:

```python
batting_average = 0.320
home_runs = 25

if (batting_average > 0.300) and (home_runs >= 20):
  print("This batter should be an all-star!")
  
if not (batting_average > 0.300) and not (home runs >= 20):
  print("This batter should not be considered an all-star!")
```

### else statements

For binary (yes-and-no) conditions, we can use the `else` keyword to reduce the number of `if` statements:

```python
if (batting_average > 0.300) and (home_runs >= 20):
  print("This batter should be an all-star!")
else: 
  print("This batter should not be considered an all-star!")
```

### elif statements

For n-ary (more than two) conditions, we can use `if`, `elif` and `else:`

```python
if (screen_size >= 1440):
    print("Large desktop!")
elif (screen_size >= 1024) and (screen_size < 1440):
    print("Small desktop!")
elif (screen_size > 768) and (screen_size < 1024): 
    print("Tablet size!")
else:
    print("Mobile size!")
```
