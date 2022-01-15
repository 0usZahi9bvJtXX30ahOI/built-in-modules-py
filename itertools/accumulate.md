# accumulate

## Syntax

```python
from itertools import accumulate

accumulate(iterable, func=operator.add, *, initial=None)
```

## Description

> Return series of accumulated sums (or other binary function results).

---

## Examples

```python
>>> result = list(accumulate(range(5)))
>>> print(result)
[0, 1, 3, 6, 10]
```

```python
>>> import operator
>>> result = list(accumulate(range(1, 5), operator.mul))
>>> print(result)
[1, 2, 6, 24]
```

```python
>>> data = [3, 4, 6, 2, 1, 9, 0, 7, 5, 8]
>>> result = list(accumulate(data, max))
>>> print(result)
[3, 4, 6, 6, 6, 9, 9, 9, 9, 9]
```

```python
>>> # Amortize a 5% loan of 1000 with 4 annual payments of 90
>>> cashflows = [1000, -90, -90, -90, -90]
>>> result = list(accumulate(cashflows, lambda bal, pmt: bal * 1.05 + pmt))
>>> print(result)
[1000, 960.0, 918.0, 873.9000000000001, 827.5950000000001]
```
