# compress

## Syntax

```python
from itertools import compress

compress(data, selectors)
```

## Description

> Return **data** elements corresponding to true **selector** elements.
>
> Forms a shorter iterator from selected **data** elements using the
> **selectors** to choose the data elements.

---

## Examples

```python
>>> data = ['a', 'b', 'c', 'd', 'e', 'f']
>>> selectors = [True, 1, False, 0, 'A', '']
>>> result = list(compress(data, selectors))
>>> print(result)
['a', 'b', 'e']
```
