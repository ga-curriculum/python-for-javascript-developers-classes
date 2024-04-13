# ![Python Classes - Class vs. Instance Members](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to compare and contrast class and instance members in Python.

# Class vs. Instance members

In Python, attributes and methods (members) are categorized into two types based on whether they belong to instances of the class or the class itself:

**Instance Attributes and Methods**: These are linked to **individual instances** of a class. Each object created from the class has its own copy of instance attributes. For example, in a `Dog` class, each `dog` object might have its own `name` and `age` attributes.

**Class Attributes and Methods**: These belong to the **class** as a whole, not to any individual instance. All instances of the class share the same class attributes. This means that if one instance changes a class attribute, the change is reflected across all other instances.

To demonstrate class attributes, let’s add a `next_id` class attribute to the `Dog` class that can be used to assign an `id` to each dog instance:

```python
class Dog:
    # Class attribute
    next_id = 1

    # Constructor with instance attributes
    def __init__(self, name, age=0):
        self.name = name
        self.age = age
        self.id = Dog.next_id  # Assign the current value of next_id to this instance
        Dog.next_id += 1  # Increment the class attribute 'next_id' so the next dog gets a new ID

    def bark(self):
        print(f'{self.name} says woof!')

    def __str__(self):
        return f'Dog ({self.id}) named {self.name} is {self.age} years old'

```

Note how the `Dog.next_id` class attribute is being accessed within the `__init__` method.


> 💡 Note: Technically, instances can also access class members via self due to the fact that if the instance does not have an accessed member, Python will check the class and provide the class version of the member if it exists.

Now let’s make sure it worked:

```python
ruby = Dog('Ruby', 2)

print(ruby)

liam = Dog('Liam')

print(liam)
```

Cool, now let’s see how class methods are created by adding a `get_total_dogs` method.

Add this to the bottom of the `Dog` class:

```python
def __str__(self):
	return f'Dog ({self.id}) named {self.name} is {self.age} years old'

# new code below

@classmethod
def get_total_dogs(cls):
	# cls represents the Dog class
	return cls.next_id - 1
```

There’s only two differences when defining a class method:

1. The `@classmethod` *decorator*
2. The naming convention of the first parameter is to use `cls` instead of `self`

> 💡 Decorators in programming are used to implement metaprogramming (when a program has knowledge or manipulates itself). In Python, [decorators](https://www.programiz.com/python-programming/decorator) are used to modify the behavior of a function or class. 

Let’s test out the new class method:

```python
ruby = Dog('Ruby', 2)
pup = Dog('Liam')

# class methods are called on the class, not an instance
print(Dog.get_total_dogs())  # -> 2
```
