# zip_longest

## Syntax

```python
from itertools import zip_longest

zip_longest(*iterables, fillvalue=None)
```

## Description

> Return a zip_longest object whose `.__next__()` method returns a tuple where the
> i-th element comes from the i-th iterable argument.
>
> The `.__next__()` method continues until the longest iterable in the argument
> sequence is exhausted and then it raises StopIteration.
>
> When the shorter iterables are exhausted, the fillvalue is substituted in
> their place.
>
> The fillvalue efaults to None or can be specified by a keyword argument.

---

## Examples

```python
>>> a, b = ('a', 'b', 'c'), (1, 2, 3, 4, 5)
>>> for x in zip_longest(a, b, fillvalue='z'):
...     print(x)
... 
('a', 1)
('b', 2)
('c', 3)
('z', 4)
('z', 5)
```

```python
>>> iterable, length = 'abcdefg', 3
>>> args = [iter(iterable)] * length
>>> for x in zip_longest(*args, fillvalue='z'):
...     print(x)
... 
('a', 'b', 'c')
('d', 'e', 'f')
('g', 'z', 'z')
```
