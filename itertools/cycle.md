# cycle

## Syntax

```python
from itertools import cycle

cycle(iterable)
```

## Description

> Return elements from the iterable until it is exhausted.
> Then repeat the sequence indefinitely.

---

## Examples

```python
>>> for x in cycle('Foo'):
...     print(x)
... 
F
o
o
F
o
o
F
o
o
... 
```

```python
>>> for x in cycle(['On', 'Off']):
...     print(x)
... 
On
Off
On
Off
On
... 
```
