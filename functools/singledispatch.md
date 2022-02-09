# singledispatch

## Syntax

```python
from functools import singledispatch

singiledispatch(func)
```

## Description

> Transform a function into a single-dispatch generic function.
>
> Transforms a function into a generic function, which can have different
> behaviours depending upon the type of its first argument. The decorated
> function acts as the default implementation, and additional
> implementations can be registered using the register() attribute of the
> generic function.

---

## Examples

```python
@singledispatch
def fun(arg):
    return arg

@fun.register
def _(arg: int):
    print(f'Strength in numbers, eh? {arg}')

@fun.register
def _(arg: list):
    print("Enumerate this:")
    for i, elem in enumerate(arg):
        print(i, elem)

>>> fun(1)
Strength in numbers, eh? 1
>>> fun(['spam', 'spam', 'eggs', 'spam')
Enumerate this:
0 spam
1 spam
2 eggs
3 spam
>>> fun('Foo')
Let me just say, Foo
```
