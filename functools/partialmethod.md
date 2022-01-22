# partialmethod

## Syntax

```python
from functools import partialmethod

partialmethod(func, *args, **keywords)
```

## Description

> Return a new partialmethod descriptor which behaves like partial except that
> it is designed to be used as a method definition rather than being directly
> callable.
>
> *func* must be a descriptor or a callable (objects which are both, like normal
> functions, are handled as descriptors).

---

## Examples

```python
class Cell:
    def __init__(self):
        self._alive = False

    @property
    def alive(self):
        return self._alive

    def set_state(self, state):
        self._alive = bool(state)

    set_alive = partialmethod(set_state, True)
    set_dead = partialmethod(set_state, False)


>>> c = Cell()
>>> c.alive
False
>>> c.set_alive()
>>> c.alive
True
```
