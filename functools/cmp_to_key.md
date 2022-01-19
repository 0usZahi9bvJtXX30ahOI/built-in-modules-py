# cmp_to_key

## Syntax

```python
from functools import cmp_to_key

cmp_to_key(func)
```

## Description

> Convert a comparison function into a key function.

---

## Examples

```python

def compare(a, b):
    return (a > b) - (a < b)

>>> iterable = ['Foo', 'a', 'b', 'A', 'F', 'Bar']
>>> result = list(sorted(iterable, key=cmp_to_key(compare)))
>>> print(result)
['A', 'Bar', 'F', 'Foo', 'a', 'b']
```
