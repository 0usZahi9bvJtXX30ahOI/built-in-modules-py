# ChainMap

## Syntax

```python
from collections import ChainMap

ChainMap(*maps)
```

## Description

> A **ChainMap** groups multiple dicts (or other mappings) together to create a
> single, updateable view. This is often much faster than creating a new
> **dict** and running multiple `dict.update()` calls.
>
> The underlying mappings are stored in a list. That list is public and can
> be accessed or updated using the **maps** attribute. There is no other
> state.
>
> Lookups search the underlying mappings successively until a key is found.
> In contrast, writes, updates, and deletions only operate on the first
> mapping.

---

## Examples

```python
# define two dictionaries with at least some keys overlapping.
>>> dict1 = {'apple': 1, 'banana': 2}
>>> dict2 = {'coconut': 1, 'date': 1, 'apple': 3}

# create two ChainMaps with different ordering of those dicts.
>>> combined_dict = ChainMap(dict1, dict2)
>>> reverse_ordered_dict = ChainMap(dict2, dict1)

>>> for x in combined_dict.items():
...     x
... 
('coconut', 1)
('date', 1)
('apple', 1)
('banana', 2)

>>> for x in reverse_ordered_dict.items():
...     x
... 
('apple', 3)
('banana', 2)
('coconut', 1)
('date', 1)
```

```python
>>> dict1 = {'a': 1, 'b': 2}
>>> dict2 = {'b': 3, 'c': 4}
>>> dict3 = {'f': 5}

>>> chain = ChainMap(dict1, dict2)
>>> chain.maps
[{'a': 1, 'b': 2}, {'b': 3, 'c': 4}]

>>> chain1 = chain.new_child(dict3)
>>> chain1.maps
[{'f': 5}, {'a': 1, 'b': 2}, {'b': 3, 'c': 4}]

>>> chain1['f']
5
```
