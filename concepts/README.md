# ![Python Classes - Concepts](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create and use classes in Python.

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
