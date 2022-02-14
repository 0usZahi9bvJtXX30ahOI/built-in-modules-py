# total_ordering

## Syntax

```python
from functools import total_ordering

total_ordering()
```

## Description

> Given a class defining one or more rich comparison ordering methods,
> this class decorator supplies the rest.
>
> The class must define one of `__lt__()`, `__le__()`, `__gt__()`, or
> `__ge__()`.
>
> In addition, the class should supply an `__eq__()` method.
---

## Examples

```python
@total_ordering
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def _is_valid_operand(self, other):
        return hasattr(other, "name") and hasattr(other, "age")

    def __eq__(self, other):
        if not self._is_valid_operand(other):
            return NotImplemented
        return self.age == other.age

    def __lt__(self, other):
        if not self._is_valid_operand(other):
            return NotImplemented
        return self.age < other.age

>>> student1 = Student("xyz", 23)
>>> student2 = Student("abc", 25)
>>> 
>>> print(student1 == student2)
False
>>> print(student1 > student2)
False
>>> print(student1 < student2)
True
```

```python
@total_ordering
class BankAccount:
    def __init__(self, balance=0):
        self.balance = balance

    def __lt__(self, other):
        return self.balance < other.balance

    def __eq__(self, other):
        return self.balance == other.balance

>>> account1 = BankAccount(500)
>>> account2 = BankAccount(300)
>>> print(account1 > account2)
True
>>> print(account1 < account2)
False
>>> print(account1 == account2)
False
```
