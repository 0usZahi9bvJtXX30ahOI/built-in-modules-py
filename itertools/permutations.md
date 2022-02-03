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
>>> result = list(permutations(iterable))
>>> print(result)
[('a', 'b', 'c'), ('a', 'c', 'b'), ('b', 'a', 'c'), ('b', 'c', 'a'), ('c', 'a', 'b'), ('c', 'b', 'a')]
>>>
>>> result = list(permutations(iterable, 2))
>>> print(result)
[('a', 'b'), ('a', 'c'), ('b', 'a'), ('b', 'c'), ('c', 'a'), ('c', 'b')]
```
