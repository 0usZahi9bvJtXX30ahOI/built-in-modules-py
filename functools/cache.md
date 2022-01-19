# cache

## Syntax

```python
from functools import cache

cache(user_functions)
```

## Description

> Simple lightweight unbounded cache. Sometimes called "memoize".

### NOTE

> Returns the same as lru_cache(maxsize=None), creating a thin wrapper around a
> dictionary lookup for the function arguments.
>
> Because it never needs to evict
> old values, this is smaller and faster than lru_cache() with a size limit.

---

## Examples

```python
@cache
def factorial(n):
    return n * factorial(n - 1) if n else 1

>>> print(factorial(10))         # no previously cached result, makes 11 recursive calls
3628800

>>> print(factorial(5))          # just looks up cached value result
120

>>> print(factorial(12))         # makes two new recursive calls, the other 10 are cached
479001600
```
