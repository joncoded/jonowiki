---
description: how to store lists of data in Python
---

# Listing

### Lists

We might call these _**arrays**_ in other languages but in Python we call them **lists:**

```python
temperatures_this_week = [22, 23, 21, 24, 29, 29, 33]
precipitation_this_week = [0.5, 0.7, 1.2, 0.1, 0.0, 0.0, 0.0]
```

Basically, the square brackets _encapsulate_ the **list** and the commas _separate_ the **items**!

### Items

Lists can contain items of one or a mix of two or more types:

```python
random_data_list = [10, 2.0, "abc", false]
```

Lists can also contain zero items:

```python
empty_list = []
```

### Adding to lists

When we already have a list with items, we can still add additional items with the `append` method:&#x20;

```python
random_data_list = [10, 2.0, "abc", false] 
random_data_list.append(3)
```

{% hint style="info" %}
We call methods like `append` **"built-in" methods** because the programming language supplies them without us having to write them!
{% endhint %}

### Removing from lists

Just as easily as adding an item to a list, we can easily remove an item from a list using `remove`:

```python
random_data_list = [10, 20, "abc", false, 3]
random_data_list.remove(5)
```

### Combining lists

We can combine, or **concatenate**, lists using the familiar `+` operator:

```python
small_list1 = [10, 20]
small_list2 = ["a", "b"]
big_list = small_list1 + small_list2 
# [10, 20, "a", "b"]
```

Note that to add a single item using that syntax, we must put the single item to a one-item list:&#x20;

```python
small_list = [10, 20]
new_list = [10, 20] + [30] 

# not:
# new_list = [10, 20] + 30
```

### Accessing items

To "get" items in a list, we use a syntax similar to arrays in other languages:

```python
seasons = ["Spring", "Summer", "Fall", "Winter"]
print(seasons[0]) 
> "Spring"
```

For this unfamiliar with **zero-indexing**, the first item of a list gets assigned an index of 0, while the second item an index of 1, and so on...

We can also use negative numbers to access a list from its end!

```python
seasons = ["Spring", "Summer", "Fall", "Winter"]
print(seasons[-1]) 
> "Winter"
print(seasons[-2])
> "Fall"
```

### Modifying items

To change items in a list, we use an "access and assign" notation:

```python
seasons[2] = "Autumn"
```

### Removing items

To delete items from a list, we use the `remove` built-in method by passing the _value of the item(s)_ that we wish to remove:

```python
wait_list = ["Joe", "John", "Jose", "Jack", "Jeff"]
wait_list.remove("Joe")
# ["John", "Jose", "Jack", "Jeff"]
```

Please note that if we have two or more identical values, using `remove` will only delete the _first instance_:

```python
wait_list = ["Joe", "John", "Jose", "Jack", "Jeff", "Joe"]
wait_list.remove("Joe")
# ["John", "Jose", "Jack", "Jeff", "Joe"]
```

As a side note, if we try to use `remove` on an item that does not exist in the list, we will get an error!

### Two-dimensional lists

Two-dimensional lists contain items that consists of lists (i.e. lists-in-a-list)!&#x20;

```python
people_bios = [
    ["Joe", "Smith", 38], 
    ["John", "Brown", 39], 
    ["Jose", "Chavez", 40], 
    ["Jack", "London", 41]]
```

Note that each item follows a pattern for the first item and for the second item!

#### Accessing two-dimensional lists

A very intuitive notation, the first set of square brackets refers to the larger list while the second set refers to smaller "list-in-a-list":&#x20;

```python
people_ages[1][0] # "John" 
people_ages[1][1] # "Brown"
people_ages[1][2] # 39 
people_ages[3][1] # "London" (Jack's last name)
```

#### Modifying two-dimensional lists

Similar with one-dimensional lists, changing a two-dimensional list involves the "access and assign" notation, e.g. to modify John's age to 40:

```python
people_ages[1][2] = 40
```
