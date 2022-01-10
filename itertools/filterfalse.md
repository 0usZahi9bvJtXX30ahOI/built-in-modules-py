# filterfalse

## Syntax

```python
from itertools import filterfalse

filterfalse(predicate, iterable)
```

## Description

> Return those items of iterable for which function(item) is false.
>
> If function is None, return the items that are false.

---

## Examples

```python
>>> result = list(filterfalse(lambda x: x % 2, range(10)))
>>> print(result)
[0, 2, 4, 6, 8]
```

```python
>>> iterable = [False, 'Foo', None, True, 0, 1, '']
>>> result = list(filterfalse(None , iterable))
>>> print(result)
[False, None, 0, '']
```
