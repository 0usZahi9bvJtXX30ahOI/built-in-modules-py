# repeat

## Syntax

```python
from itertools import repeat

repeat(object, times=None)
```

## Description

> Create an iterator which returns the object for the specified number of times.
>
> If not specified, returns the object endlessly.

---

## Examples

```python
>>> word, times = 'Foo', 3
>>> for x in repeat(word, times):
...     print(x)
... 
Foo
Foo
Foo
```

```python
>>> for x in map(pow, range(10), repeat(2)):
...     print(x)
... 
0
1
4
9
16
25
36
49
64
81
```
