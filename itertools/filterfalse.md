# filterfalse

## Syntax

```python
from itertools import filterfalse

filterfalse(predicate, iterable)
```

## Description

> Return those items of **iterable** for which **function**(item) is false.
>
> If function is **None**, return the items that are false.

---

## Examples

```python
>>> list(filterfalse(lambda x: x % 2, range(10)))
[0, 2, 4, 6, 8]
```

```python
>>> iterable = [False, 'Foo', None, True, 0, 1, '']
>>> list(filterfalse(None , iterable))
[False, None, 0, '']
```
