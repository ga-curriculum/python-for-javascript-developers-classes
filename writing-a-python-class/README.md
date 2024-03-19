# ![Python Classes - tktk Microlesson Name](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to write a Python class with instance methods and default parameters.

## Writing a basic Python `class`

Like many of you, I like dogs - let’s define a `Dog` class to create doggies from:

```python
class Dog():
  def __init__(self, name, age = 0):
    self.name = name
    self.age = age

  def bark(self):
    print(f'{self.name} says woof!')
```

> 💡 The naming convention for Python classes is UpperCamelCasing.

Python automatically calls the `__init__` magic method when a new dog is created.

`__init__` is short for “initialize” because the method is used to initialize the properties of the new object.

> ❓ What method in JavaScript classes performs the same thing?

The `age = 0` in `__init__`’s parameter list is called a *default parameter* and will be assigned the result of the expression to the right of the `=` if the function is called without an argument for that positional parameter.

The attributes for a dog instance are `name` and `age`.

`bark` is an *instance* method in this Dog class.

> ❓ What’s an instance method?

## What’s this `self` business?

In the JS lesson about `this`, it was mentioned that every OOP language must have the same or similar mechanism as `this` to be able to:

- Enable a method to access the other properties/methods in an object, and
- Enable a single-copy of a method in memory to serve any number of instances.

JavaScript, Java, C++, C#, and others call it `this`.

Ruby, Swift and others call it `self`.

However, in Python, only by convention is it called `self` because it’s just a parameter name…

Take a look at the `__init__` and `bark` method definitions, notice how the first parameter is named `self`. When we write code like `ruby.bark()`, the object to the left of the dot is automatically assigned to the method’s first parameter - which should be named `self`. This is how Python provides the “context” in both instance and class methods!