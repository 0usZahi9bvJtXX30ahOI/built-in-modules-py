# repeat

## Syntax

```python
from itertools import repeat

repeat(object, times=None)
```

## Description

> Create an iterator which returns the object for the specified number of times.
>
> If not specified, returns the object endlessly.

---

## Examples

```python
>>> word, times = 'Foo', 3
>>> list(repeat(word, times))
['Foo', 'Foo', 'Foo']
```

```python
>>> list(map(pow, range(10), repeat(2)))
>>> for x in map(pow, range(10), repeat(2)):
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
