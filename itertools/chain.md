# chain

```python
from itertools import chain

chain(*iterables)
```

```python
>>> a, b, c = [1, 2], ['a', 'b'], ['foo']
>>> for x in chain(a, b, c):
...     print(x)
... 
1
2
a
b
foo
```

```python
>>> a = [[1, 2], ['a', 'b'], ['foo']]
>>> for x in chain.from_iterable(a):
...     print(x)
... 
1
2
a
b
foo
```
