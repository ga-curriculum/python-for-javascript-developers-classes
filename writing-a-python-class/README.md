# ![Python Classes - Writing a Python Class](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to write a Python class with instance methods and default parameters.

In Python, everything is treated as an object, which means that every entity has some attributes and associated behaviors. Python uses classes to define the attributes and behaviors of an object, and instances of these classes are the objects themselves.

For example, here’s how you can see the attributes and methods associated with a list object:

```python
# Create a list
nums = [1, 2, 3]
# Use the dir() function to list all attributes and methods of the list
print(dir(nums))
```

You might recognize methods like `append` and `pop` which are used to add and remove elements from the list, respectively.

In Python, methods that have names beginning and ending with double underscores `__` are known as "magic methods" or "dunder" (double underscore) methods. These are special methods which Python calls internally for certain operations. 

For example, the `__init__()` method is called when an object is created, and `__str__()` is called when an object is converted to a string. 

Magic methods in Python let you customize what happens when you use standard operators like `+`, `-`, or `==` with your own custom objects. This process is called `operator overloading`. It means you can define specific rules for how these operators should work when applied to instances of your classes.

Let's create a new class and see some of these new tools in action! 

## Writing a basic Python `class`

Like probably many of you, I like dogs - let’s define a `Dog` class to create new dogs from:

```python
class Dog():
  def __init__(self, name, age = 0):
    self.name = name
    self.age = age

  def bark(self):
    print(f'{self.name} says woof!')
```

> 💡 The naming convention for Python classes is UpperCamelCasing - just like in JavaScript. 

Python automatically calls the `__init__` magic method when a new dog is created.

`__init__` is short for “initialize” because the method is used to initialize the properties of the new object.

> ❓ What method in JavaScript classes performs the same thing?

The `age = 0` in `__init__`’s parameter list is called a *default parameter* and will be assigned the result of the expression to the right of the `=` if the function is called without an argument for that positional parameter.

The attributes for a dog instance are `name` and `age`.

`bark` is an *instance* method in this Dog class.

> An instance method is a function defined inside a class that operates on instances of that class.All dog objects created from our class will be able to bark. 

## What’s this `self` business?

From previous discussions about `this` in JavaScript, you might recall that every object-oriented programming language has a similar mechanism. This mechanism allows a method within an object to:

Access other properties or methods in the same object.
Use a single copy of a method in memory to interact with any number of object instances.
In languages like JavaScript, Java, C++, and C#, this mechanism is referred to as `this`. In contrast, languages like Ruby and Swift use `self`.

In Python, `self` functions similarly, but with a key distinction — `self` is not a keyword but merely a conventionally used parameter name. 

When defining instance methods in Python, such as `__init__` or any custom method like `bark`, the first parameter is typically named `self`. This parameter refers to the instance on which the method is being called.

When we write code like `newDog.bark()`, the object to the left of the dot is automatically assigned to the method’s first parameter - which should be named `self`. 
This is how Python provides the “context” in both instance and class methods!