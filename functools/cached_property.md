# cached_property

## Syntax

```python
from functools import cached_property

cached_property(func)
```

## Description

> Transform a method of a class into a property whose value is computed once and
> then cached as a normal attribute for the life of the instance. Similar to
> property(), with the addition of caching.
>
> Useful for expensive computed
> properties of instances that are otherwise effectively immutable.

### NOTE

> The mechanics of cached_property() are somewhat different from property(). A
> regular property blocks attribute writes unless a setter is defined. In
> contrast, a cached_property **allows writes**.
>
> The cached_property decorator only runs on lookups and only when an attribute
> of the same **name doesn’t exist**. When it does run, the cached_property writes
> to the attribute with the same name. Subsequent attribute reads and writes
> take precedence over the cached_property method and it works like a normal
> attribute.
>
> The cached value can be cleared by **deleting the attribute**. This allows the
> cached_property method to run again.

---

## Examples

```python
class DataSet:

    def __init__(self, sequence_of_numbers):
        self._data = tuple(sequence_of_numbers)

    @cached_property
    def stdev(self):
        return statistics.stdev(self._data)
```

---

> If a **mutable mapping** is not available or if space-efficient key sharing is
> desired, an effect similar to cached_property() can be achieved by a stacking
> property() on top of cache():

```python
class DataSet:
    def __init__(self, sequence_of_numbers):
        self._data = sequence_of_numbers

    @property
    @cache
    def stdev(self):
        return statistics.stdev(self._data)
```
