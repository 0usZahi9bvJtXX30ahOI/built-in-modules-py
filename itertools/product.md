# product

## Syntax

```python
from itertools import product

product(*iterables, repeat=1)
```

## Description

> Cartesian product of input iterables. Equivalent to nested for-loops.
> For example, product(A, B) returns the same as: ((x,y) for x in A for y in B).
>
> The leftmost iterators are in the outermost for-loop, so the output tuples
> cycle in a manner similar to an odometer (with the rightmost element changing
> on every iteration).
>
> To compute the product of an iterable with itself, specify the number of
> repetitions with the optional repeat keyword argument.
> For example, product(A, repeat=4) means the same as product(A, A, A, A).

---

## Examples

```python
>>> a, b = 'ABCD', 'xy'
>>> result = list(product(a, b))
>>> print(result)
[('A', 'x'), ('A', 'y'), ('B', 'x'), ('B', 'y'), ('C', 'x'), ('C', 'y'), ('D', 'x'), ('D', 'y')]
```

```python
>>> result = list(product(range(2), repeat=3))
>>> print(result)
[(0, 0, 0), (0, 0, 1), (0, 1, 0), (0, 1, 1), (1, 0, 0), (1, 0, 1), (1, 1, 0), (1, 1, 1)]
```
