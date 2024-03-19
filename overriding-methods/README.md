# ![Python Classes - tktk Microlesson Name](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to override methods in a class.

## Overriding Methods

As you saw above, when we used print(ruby) to print the ruby object, we got an unfriendly output.

We can change this behavior by overriding the __str__ method that the print function calls automatically to obtain the string to print out.

Let’s modify the Dog class to override the __str__ method:

```python
class Dog():
  def __init__(self, name, age = 0):
    self.name = name
    self.age = age

  def bark(self):
    print(f'{self.name} says woof!')
    
  def __str__(self):
    return f'Dog named {self.name} is {self.age} years old'
​
Let’s try it out:
ruby = Dog('Ruby', 3)

print(ruby) # -> Dog named Ruby is 3 years old
```
