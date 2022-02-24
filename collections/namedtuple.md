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

## Examples

```python
>>> House = namedtuple('House', ['city', 'country', 'year', 'area', 'num_rooms'])
>>> 
>>> house1 = House('New York', 'United States', 2022, 2018, 4)
>>> house2 = House('Sydney', 'Australia', 1900, 1000, 2)
>>> 
>>> house1
House(city='New York', country='United States', year=2022, area=2018, num_rooms=4)
>>> house2
House(city='Sydney', country='Australia', year=1900, area=1000, num_rooms=2)
>>>
>>> house1.city
'New York'
>>> house2.country
'Australia'
>>> house2[1]
'Australia'
>>> 
>>> house1.area + house2.area
3018
```
