# dropwhile

## Syntax

```python
from itertools import dropwhile

dropwhile(predicate, iterable)
```

## Description

> Drop items from the **iterable** while **predicate**(item) is true.
>
> Afterwards, return every element until the **iterable** is exhausted.

---

## Examples

```python
>>> result = list(dropwhile(lambda x: x <= 5, range(11)))
>>> print(result)
[6, 7, 8, 9, 10]
```

```python
>>> iterable = [-1, 3, -4, 10, -1000, 4, 3, -0.1, 0]
>>> result = list(dropwhile(lambda x: x <= 0, sorted(iterable)))
>>> print(result)
[3, 3, 4, 10]
```
