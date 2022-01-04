# starmap

```python
from itertools import starmap

starmap(function, iterable)
```

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
