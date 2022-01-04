# cycle

```python
from itertools import cycle

cycle(iterable)
```

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
