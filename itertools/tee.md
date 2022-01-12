# tee

## Syntax

```python
from itertools import tee

tee(iterable, n=2)
```

## Description

> Returns a tuple of n independent iterators.

### NOTE

> Once tee() has made a split, the original iterable should not be used anywhere
> else; otherwise, the iterable could get advanced without the tee objects being
> informed.
>
> tee iterators are not threadsafe. A RuntimeError may be raised when using
> simultaneously iterators returned by the same tee() call, even if the
> original iterable is threadsafe.
>
> This itertool may require significant auxiliary storage (depending on how
> much temporary data needs to be stored). In general, if one iterator uses
> most or all of the data before another iterator starts,
> it is faster to use list() instead of tee().

---

## Examples

```python
>>> iterable = [3, 'Foo', None, 4, True]
>>> iterator1, iterator2 = tee(iterable, 2)
>>> print(list(iterator1))
[3, 'Foo', None, 4, True]
>>> print(list(iterator1))
[]
>>> print(list(iterator2))
[3, 'Foo', None, 4, True]
```

```python
>>> iterable = [1, 2, 3, 4, 5, 6]
>>> iterator1, iterator2 = tee(iterable, 2)
>>> first_half = islice(iterator1, 3)
>>> second_half = islice(iterator2, 3, None)
>>> print(list(chain(second_half, first_half)))
[4, 5, 6, 1, 2, 3]
```
