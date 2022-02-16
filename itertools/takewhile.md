# takewhile

## Syntax

```python
from itertools import takewhile

takewhile(predicate, iterable)
```

## Description

> Return successive entries from an **iterable** as long as the **predicate**
> evaluates to true for each entry.

---

## Examples

```python
>>> iterable = [1, 4, 6, 4, 1]
>>> list(takewhile(lambda x: x < 5, iterable))
[1, 4]
```

```python
>>> list(takewhile(lambda x: x <= 5, range(11)))
[0, 1, 2, 3, 4, 5]
```

```python
>>> iterable = [-1, 3, -4, 10, -1000, 4, 3, -0.1, 0]
>>> list(takewhile(lambda x: x <= 0, sorted(iterable)))
[-1000, -4, -1, -0.1, 0]
```
