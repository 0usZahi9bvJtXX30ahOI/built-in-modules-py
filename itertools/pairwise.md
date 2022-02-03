# pairwise

## Syntax

```python
from itertools import pairwise

pairwise(iterable)
```

## Description

> Return an iterator of overlapping pairs taken from the input **iterator**.

---

## Examples

```python
>>> iterable = 'abcdefg'
>>> result = list(pairwise(iterable))
>>> print(result)
[('a', 'b'), ('b', 'c'), ('c', 'd'), ('d', 'e'), ('e', 'f'), ('f', 'g')]
```

```python
>>> result = list(pairwise(range(5)))
>>> print(result)
[(0, 1), (1, 2), (2, 3), (3, 4)]
```
