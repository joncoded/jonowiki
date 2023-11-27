---
description: displaying output in Python
---

# Printing

Show output using the `print(...)` function:

```python
print("Hello world")
print('Hello world')
```

In the above, we could use either _single quotes_ or _double quotes_ (just stick to one consistent set!)

### Error!

If we mismatch the quotation marks, an error can happen, e.g.:

```python
print('Let us use mismatched quotation marks")
```

Output:

```
  File "script.py", line 1
    print('Let us use mismatched quotation marks")
                                                    ^
SyntaxError: EOL while scanning string literal
```

While the program yells at us, it also tell us where our code went wrong (the line #)!
