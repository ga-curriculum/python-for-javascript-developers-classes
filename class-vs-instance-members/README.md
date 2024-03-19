# ![Python Classes - tktk Microlesson Name](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to compare and contrast class and instance members in Python.

# Class vs. Instance Members

In Python, **instance** attributes & methods (members) are intended to be accessed/invoked by instances of the class, whereas, **class** members are intended to be accessible on the class only, not an instance.

Each object instance has its own copy of its attributes, e.g., `name`. However, all instances share class attributes.

To demonstrate class attributes, let’s add a `next_id` class attribute to the `Dog` class that can be used to assign an `id` to each dog instance:

```python
class Dog():
  # class attribute
  next_id = 1

  # updated __init__
  def __init__(self, name, age = 0):
    self.name = name
    self.age = age
    self.id = Dog.next_id
    Dog.next_id += 1

  def bark(self):
    print(f'{self.name} says woof!')

  # updated __str__
  def __str__(self):
    return f'Dog ({self.id}) named {self.name} is {self.age} years old'
```

Note how the `Dog.next_id` class attribute is being accessed within the `__init__` method.


> 💡 Note: Technically, instances can also access class members via self due to the fact that if the instance does not have an accessed member, Python will check the class and provide the class version of the member if it exists.

Now let’s make sure it worked :)

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

> 💡 Decorators in programming are used to implement metaprogramming (when a program has knowledge or manipulates itself). In Python, decorators are used to modify the behavior of a function or class. They are not very common, but there’s a link in the Further Study section if you’d like to learn more about decorators in Python.

Let’s test out the new class method:

```python
ruby = Dog('Ruby', 2)
pup = Dog('Liam')

# class methods are called on the class, not an instance
print(Dog.get_total_dogs())  # -> 2
```
