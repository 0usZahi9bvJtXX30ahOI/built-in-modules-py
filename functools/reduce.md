# reduce

## Syntax

```python
from functools import reduce

_initial_missing = object()
reduce(function, sequence, initial=_initial_missing)
```

## Description

> Apply a function of two arguments cumulatively to the items of a **sequence**,
> from left to right, so as to reduce the sequence to a single value.
>
> For example, `reduce(lambda x, y: x+y, [1, 2, 3, 4, 5])` calculates
> `((((1 + 2) + 3) + 4) + 5)`.
>
> If **initial** is present, it is placed before the items of the **sequence**
> in the calculation, and serves as a default when the **sequence** is empty.

---

## Examples

```python
>>> from operator import add
>>> reduce(add, range(10))
45
```

```python
>>> iterable = [1, 3, 5, 7]
>>> reduce(lambda x, y: x - y, iterable, 100)
84
```
