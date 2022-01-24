# wraps

## Syntax

```python
from functools import wraps

WRAPPER_ASSIGNMENTS = ('__module__', '__name__', '__qualname__', '__doc__', '__annotations__')
WRAPPER_UPDATES = ('__dict__',)

wraps(wrapped, assigned=WRAPPER_ASSIGNMENTS, updated=WRAPPER_UPDATES)
```

## Description

> Decorator factory to apply update_wrapper() to a wrapper function.
>
> Returns a decorator that invokes update_wrapper() with the decorated
> function as the wrapper argument and the arguments to wraps() as the
> remaining arguments. Default arguments are as for update_wrapper().
> This is a convenience function to simplify applying partial() to
> update_wrapper().

---

## Examples

```python
def my_decorator(f):

    @wraps(f)
    def wrapper(*args, **kwds):
        print('Calling decorated function')
        return f(*args, **kwds)

    return wrapper

@my_decorator
def example():
    """Docstring"""
    print('Called example function')

>>> example.__doc__
'Docstring'
>>> example.__name__
'example'
```
