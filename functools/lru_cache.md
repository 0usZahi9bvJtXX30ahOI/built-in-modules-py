# lru_cache

## Syntax

```python
from functools import lru_cache

lru_cache(user_function)
lru_cache(maxsize=128, typed=False)
```

## Description

> Least-recently-used cache decorator.
>
> If _maxsize_ is set to None, the LRU features are disabled and the cache
> can grow without bound.
>
> If typed is set to true, function arguments of different types will be
> cached separately. If typed is false, the implementation will usually
> regard them as equivalent calls and only cache a single result.
> (Some types such as str and int may be cached separately even when typed is false.)

---

## Examples

```python
@lru_cache(maxsize=None)
def fib(n):
    if n < 2:
        return n
    return fib(n-1) + fib(n-2)

>>> [fib(n) for n in range(16)]
[0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610]

>>> fib.cache_info()
CacheInfo(hits=28, misses=16, maxsize=None, currsize=16)
```

```python
import urllib.request
import urllib.error

# LRU cache for static web content
@lru_cache(maxsize=32)
def get_pep(num):
    """Retrieve text of a Python Enhancement Proposal"""
    resource = f'https://www.python.org/dev/peps/pep-{num:04d}/'
    try:
        with urllib.request.urlopen(resource) as s:
            return s.read()
    except urllib.error.HTTPError:
        return 0

>>> for n in [8, 290, 308, 320, 8, 290]:
...     pep = get_pep(n)
...     n, len(pep)
(8, 103645)
(290, 59592)
(308, 57934)
(320, 50506)
(8, 103645)
(290, 59592)

>>> get_pep.cache_info()
CacheInfo(hits=2, misses=4, maxsize=32, currsize=4)
```
