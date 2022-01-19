# cmp_to_key

## Syntax

```python
from functools import cmp_to_key

cmp_to_key(func)
```

## Description

> Convert a comparison function into a key function.

### NOTE

> A comparison function is any callable that accept two arguments, compares
> them, and returns a negative number for less-than, zero for equality,
> or a positive number for greater-than.
>
> A key function is a callable that accepts one argument and returns another
> value to be used as the sort key.

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
