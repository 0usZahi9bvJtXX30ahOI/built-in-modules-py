# singledispatchmethod

## Syntax

```python
from functools import singledispatchmethod

singledispatchmethod(func)
```

## Description

> Single-dispatch generic method descriptor.
>
> Supports wrapping existing descriptors and handles non-descriptor callables
> as instance methods.

---

## Examples

```python
class Negator:
    @singledispatchmethod
    @classmethod
    def neg(cls, arg):
        raise NotImplementedError(f'Type {type(arg)} is unsupported')

    @neg.register
    @classmethod
    def _(cls, arg: int):
        return -arg

    @neg.register
    @classmethod
    def _(cls, arg: bool):
        return not arg

>>> Negator.neg(3)
-3
>>> Negator.neg(True) 
False
```
