# ![Python Classes - tktk Microlesson Name](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create a class and instantiate objects from it.

## Creating Objects by Instantiating a Class

By defining the Dog class, we now know the structure that each of the pooches will have!
Let’s make a doggie:

```python
ruby = Dog('Ruby', 3)

print(ruby) # -> similar to <__main__.Dog object at 0x7f27bad2c208>

# print the name and age attributes of the ruby object
print(ruby.name, ruby.age) # -> Ruby 3

# invoke the ruby object's bark instance method
ruby.bark() # -> Ruby says woof!
```

Let’s try out the default parameter for a new dog’s age:

```python
liam = Dog('Liam')

print(liam.name, liam.age) # -> Liam 0
```
