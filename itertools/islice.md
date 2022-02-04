# islice

## Syntax

```python
from itertools import islice

islice(iterable, stop)
islice(iterable, start, stop, step=None)
```

## Description

> Return an iterator whose **next()** method returns selected values from an
> **iterable**.
>
> If **start** is specified, will skip all preceding elements; otherwise,
> **start** defaults to zero.
>
> **Step** defaults to **1**. If specified as another value, **step** determines
> how many values are skipped between successive calls.
>
> Works like a **slice()** on a **list** but returns an iterator.

---

## Examples

```python
>>> list(islice(range(1000000), 4))
[0, 1, 2, 3]
```

```python
>>> list(islice(range(1000000), 1000, 10000, 1000))
[1000, 2000, 3000, 4000, 5000, 6000, 7000, 8000, 9000]
```
