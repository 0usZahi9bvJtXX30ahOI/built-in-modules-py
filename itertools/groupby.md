# groupby

## Syntax

```python
from itertools import groupby

groupby(iterable, key=None)
```

## Description

> Make an iterator that returns consecutive keys and groups from the iterable.

---

## Examples

```python
def print_groupby(iterable, key=None):
    for key, group in groupby(iterable, key):
        print(f'{key=} --> group={list(group)}')

>>> iterable = 'BCAACACAADBBB'
>>> 
>>> # group consecutive occurrences
>>> print_groupby(iterable)
key='B' --> group=['B']
key='C' --> group=['C']
key='A' --> group=['A', 'A']
key='C' --> group=['C']
key='A' --> group=['A']
key='C' --> group=['C']
key='A' --> group=['A', 'A']
key='D' --> group=['D']
key='B' --> group=['B', 'B', 'B']
>>>
>>> # group all occurrences
>>> print_groupby(sorted(iterable))
key='A' --> group=['A', 'A', 'A', 'A', 'A']
key='B' --> group=['B', 'B', 'B', 'B']
key='C' --> group=['C', 'C', 'C']
key='D' --> group=['D']
>>> 
>>> iterable = 'bCaAdDBaacCCbDD'
>>> 
>>> # group by a key function
>>> print_groupby(sorted(iterable), lambda x: x.islower())
key=False --> group=['A', 'B', 'C', 'C', 'C', 'D', 'D', 'D']
key=True --> group=['a', 'a', 'a', 'b', 'b', 'c', 'd']
```
