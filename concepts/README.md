# ![Python Classes - Concepts](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create and use classes in Python.

# Review of OOP

Python is an **object-oriented programming (OOP) language**.

Object-oriented programming is characterized by programming with **objects** that represent the real-world objects of the application.

<details>
<summary>❓ What are classes used for in OOP?</summary>

**Classes are used to create objects.**
</details>
    
A key principle of OOP we discussed during the JS Classes lesson was **encapsulation**…

<details>
<summary>❓ What’s encapsulation?</summary>

**The bundling of related properties (attributes) and methods (behavior) together in an object.**
</details>

Another key principle of OOP we discussed was **inheritance**…

<details>
<summary>❓ What’s inheritance?</summary>

**When a class subclasses/extends another class and thus inherits that parent/superclass’s attributes & methods.**
</details>

## Objects in Python

As you’ve already heard, everything in Python is an object. What this means is that every variable or piece of data has properties and/or methods encapsulated within the object.

Python provides a `dir()` function that can be used to list an object’s members (attributes and methods):

```python
# create a list
nums = [1, 2, 3]
print( dir(nums) )
```

Some of the members like `append` & `pop` might look familiar.

The other methods that start and end with double-underscores, are called *[**magic* (or *dunder*) methods**](https://rszalski.github.io/magicmethods/). They are internal methods most commonly used to *overload* operators. If you would like to learn more about them, be sure to check out the link in the Further Study section.

We’ll be using the `__init__` dunder method shortly.

When we start working with Django, we’ll be defining quite a few classes, so let’s see how to we do it…
