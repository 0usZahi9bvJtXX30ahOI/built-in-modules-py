# combinations

## Syntax

```python
from itertools import combinations

combinations(iterable, r)

```

## Description

> Return successive **r**-length combinations of elements in the **iterable**.

---

## Examples

```python
>>> list(combinations('abcd', 2))
[('a', 'b'), ('a', 'c'), ('a', 'd'), ('b', 'c'), ('b', 'd'), ('c', 'd')]
```

```python
>>> list(combinations(range(4), 3))
[(0, 1, 2), (0, 1, 3), (0, 2, 3), (1, 2, 3)]
```
