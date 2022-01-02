# zip_longest

```python
from itertools import zip_longest
```

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
