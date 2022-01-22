
# partial

## Syntax

```python
from functools import partial

partial(func, *args, **keywords)
```

## Description

> Return a new partial object which when called will behave like func called
> with the positional arguments args and keyword arguments keywords.
>
> If more arguments are supplied to the call, they are appended to args.
> If additional keyword arguments are supplied, they extend and override keywords.
>
> The partial() is used for partial function application which “freezes” some
> portion of a function’s arguments and/or keywords resulting in a new object
> with a simplified signature.

---

## Examples

```python
>>> basetwo = partial(int, base=2)
>>> basetwo.__doc__ = 'Convert base 2 string to an int.'
>>> print(basetwo('10010'))
18
>>> print(f'{basetwo.func=}\n{basetwo.args=}\n{basetwo.keywords=}')
basetwo.func=<class 'int'>
basetwo.args=()
basetwo.keywords={'base': 2}
```

```python
def add(a, b):
    return a + b

>>> add_5 = functools.partial(add, 10)
>>> print(add_5(10))
20
```
