# combinations_with_replacement

## Syntax

```python
from itertools import combinations_with_replacement

combinations_with_replacement(iterable, r)
```

## Description

> Return successive **r**-length combinations of elements in the **iterable**
> allowing individual elements to have successive repeats.

---

## Examples

```python
>>> result = list(combinations_with_replacement('abc', 2))
>>> print(result)
[('a', 'a'), ('a', 'b'), ('a', 'c'), ('b', 'b'), ('b', 'c'), ('c', 'c')]
```

```python
>>> result = list(combinations_with_replacement(range(2), 3))
>>> print(result)
[(0, 0, 0), (0, 0, 1), (0, 1, 1), (1, 1, 1)]
```
