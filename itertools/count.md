# count

```python
from itertools import count

count(start=0, step=1)
```

```python
>>> start, step = 3, 2
>>> counter = count(start, step)
>>> for x in counter:
...     print(x)
... 
3
5
7
9
... 
```

```python
>>> start, step = 1., 0.1
>>> for x in count(start, step):
...     print(x)
... 
1.0
1.1
1.2000000000000002
1.3000000000000003
1.4000000000000004
1.5000000000000004
1.6000000000000005
1.7000000000000006
... 
```

```python
>>> start, step = 1., 0.1
>>> for x in (start + step * i for i in count()):
...     print(x)
... 
1.0
1.1
1.2
1.3
1.4
1.5
1.6
1.7000000000000002
... 
```

```python
>>> from decimal import Decimal
>>> start, step = Decimal(1), Decimal('0.1')
>>> for x in count(start, step):
...     print(x)
... 
1
1.1
1.2
1.3
1.4
1.5
1.6
1.7
... 
```
