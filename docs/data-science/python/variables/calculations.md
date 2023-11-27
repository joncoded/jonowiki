---
description: doing math with Python
---

# Calculations

### Arithmetical operations

We can do arithmetic with Python:&#x20;

```python
print(1 + 2) # 3.0
print(2 - 1) # 1.0
print(3 * 2) # 6.0
print(9 / 3) # 3.0
```

{% hint style="info" %}
Python (version 2.7+) converts all integers to floats!
{% endhint %}

{% hint style="warning" %}
Also, division by zero can result in a `ZeroDivisionError!`
{% endhint %}

### Calculations with variables

Predictably, we can also do mathematics with variables in Python:

```python
speed_limit = 55
my_speed = speed_limit * 2
print(my_speed) # 110.0
```

### Other operators

#### Exponents

To denote "to the power of", we use the notation `**`

```python
print(3 ** 2) # 9.0 (3 squared)
print(2 ** 5) # 32.0 (2 to the power of 5)
print(9 ** 0.5) # 3.0 (square root of 9) 
```

#### Modulo

To denote "the remainder of", we use the notation `%` (as seen as in JavaScript)

```python
print(17 % 4)  # 1.0
print(9 % 9)   # 0.0
print(32 % -7) # -3.0
```

#### Updates (plus-equals)

To write `x = x + 1` to mean "add one to the variable `x` ", we can use the shorthand `+=`:

```python
x = 1
print (x += 1) # aka x = x + 1 = 2.0
```

Predictably, we can combine `-`, `*`, `/`, and `%` with `=` as well:

```python
x = 3
print (x -= 2) # 1.0
print (x *= 2) # 6.0
print (x /= 2) # 1.5
```
