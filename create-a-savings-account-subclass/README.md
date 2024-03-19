# ![Python Classes - tktk Microlesson Name](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create a class and instantiate objects from it.

## Level Up 🚀 

Looking for some MORE practice building an object hierarchy in Python? Good!

Continue in the same Python file…

Add to the `BankAccount` class the following:

## Bonus 1

Override the `__str__` method to return the following formatted string:

```python
Account <account_no> / Balance: xxxxx.xx
```

## Bonus 2

Create a `SavingsAccount` class that subclasses `BankAccount` and specializes it so that the `withdraw` method no longer accepts any argument, does not change the balance, and returns a string of `No withdrawals permitted`.

## Bonus 3

Add an additional `has_overdraft` attribute to the `BankAccount` class that accepts `True` or `False` at the time of instantiation, but defaults to `False` if not passed in (hint: review default parameters discussed above).

When the `withdraw` method is called, do not allow the withdraw if the amount being withdrawn is greater than `balance`, unless `has_overdraft` is `True`. `withdraw` should continue to return the `balance`.
