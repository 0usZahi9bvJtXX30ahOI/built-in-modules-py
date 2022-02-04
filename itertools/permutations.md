# permutations

## Syntax

```python
from itertools import permutations

permutations(iterable, r=None)
```

## Description

> Return successive **r**-length permutations of elements in the **iterable**.

---

## Examples

```python
>>> iterable = 'abc'
>>> list(permutations(iterable))
[('a', 'b', 'c'), ('a', 'c', 'b'), ('b', 'a', 'c'), ('b', 'c', 'a'), ('c', 'a', 'b'), ('c', 'b', 'a')]

>>> list(permutations(iterable, 2))
[('a', 'b'), ('a', 'c'), ('b', 'a'), ('b', 'c'), ('c', 'a'), ('c', 'b')]
```
