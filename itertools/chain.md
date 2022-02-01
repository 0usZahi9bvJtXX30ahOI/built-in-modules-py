# chain

## Syntax

```python
from itertools import chain

chain(*iterables)
```

## Description

> Return a chain object whose `.__next__()` method returns elements from the
> first iterable until it is exhausted, then elements from the next
> iterable, until all of the iterables are exhausted.

---

## Examples

```python
>>> a, b, c = [1, 2], ['a', 'b'], ['foo']
>>> list(chain(a, b, c))
[1, 2, 'a', 'b', 'foo']
```

```python
>>> a = [[1, 2], ['a', 'b'], ['foo']]
>>> list(chain.from_iterable(a))
[1, 2, 'a', 'b', 'foo']
```
