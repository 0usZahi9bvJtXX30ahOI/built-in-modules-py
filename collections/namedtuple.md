# namedtuple

## Syntax

```python
from collections import namedtuple

namedtuple(typename, field_name, *, rename=False, default=None, module=None)
```

## Description

> Returns a new tuple subclass named **typename**.
>
> The new subclass is used to create tuple-like objects that have fields
> accessible by attribute lookup as well as being indexable and iterable.
> Instances of the subclass also have a helpful docstring (with typename and
> field_names) and a helpful `__repr__()` method which lists the tuple contents
> in a name=value format.
>
> The **field_names** are a sequence of strings such as ['x', 'y'].
> Alternatively, **field_names** can be a single string with each fieldname
> separated by whitespace and/or commas, for example 'x y' or 'x, y'.
>
> If **rename** is true, invalid fieldnames are automatically replaced with
> positional names.
>
> **default** can be None or an iterable of default values. Since fields with a
> default value must come after any fields without a default, the defaults
> are applied to the rightmost parameters.

---
