# update_wrapper

## Syntax

```python
from functools import update_wrapper

WRAPPER_ASSIGNMENTS = ('__module__', '__name__', '__qualname__', '__doc__','__annotations__')
WRAPPER_UPDATES = ('__dict__',)

update_wrapper(wrapper, wrapped, assigned=WRAPPER_ASSIGNMENTS, updated=WRAPPER_UPDATES)
```

## Description

> Update a wrapper function to look like the wrapped function.
>
> **wrapper** is the function to be updated
>
> **wrapped** is the original function
>
> **assigned** is a tuple naming the attributes assigned directly from the
> wrapped function to the wrapper function
>
> **updated** is a tuple naming the attributes of the wrapper that are updated
> with the corresponding attribute from the wrapped function

---

## Examples

```python
def my_decorator(f):

    def wrapper(*args, **kwds):
        print('Calling decorated function')
        return f(*args, **kwds)

    update_wrapper(wrapper, f)

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
