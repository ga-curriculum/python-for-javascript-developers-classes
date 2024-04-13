# ![Python Classes - Create a Bank Account Class](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create a class and instantiate objects from it.

## 🎓 You Do: Create a `BankAccount` Class 

Looking for some practice building an object hierarchy in Python? Good!

In a separate Python file:

Create a `BankAccount` class with the following members:

- **`owner`**: (attribute) The owner’s name as a string
- **`balance`**: (attribute) The amount of money in the account
- **`account_no`**: (attribute) A number to be randomly generated and assigned within `__init__` - not passed in at time of instantiation
- **`deposit(amount)`**: (method) When called on an instance, increases the `balance` by the `amount` argument and returns the new balance
- **`withdraw(amount)`**: (method) When called on an instance, decreases the `balance` by the `amount` argument and returns the new balance

Here’s how to generate a random integer for the in Python:

```python
import random

# Use this inside of BankAccount's __init__ to generate
# a random account number from 111111111 to 999999999
self.account_no = random.randint(111111111, 999999999)
```

Create two instances, make both deposits and withdrawals, and print the attributes to test them out.

## Bonus 1

Override the `__str__` method to return the following formatted string:

```python
Account <account_no> - Balance: xxxxx.xx
```
