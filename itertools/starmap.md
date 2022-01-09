# starmap

## Syntax

```python
from itertools import starmap

starmap(function, iterable)
```

## Description

> Return an iterator whose values are returned from the function evaluated with
> an argument tuple taken from the given sequence.

---

## Examples

```python
>>> values = [(0, 2), (1, 2), (2, 2)]
>>> squares = starmap(pow, values)
>>> print(list(squares))
[0, 1, 4]
```

```python
>>> from functools import reduce
>>> from operator import mul
>>> 
>>> def multiply(*args):
...     return reduce(mul, args)
>>> 
>>> values = [(1, 2, 3), (1, 2, 3, 4), (1, 2, 3, 4, 5)]
>>> multiplications = starmap(multiply, values)
>>> print(list(multiplications))
[6, 24, 120]
```
