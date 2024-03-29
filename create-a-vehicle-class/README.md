# ![Python Classes - tktk Microlesson Name](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to practice creating a class in Python.

## Exercise - Create a Class (15 min)

Define a class named `Vehicle` with the following members:

- **`vin`**: attribute for the vehicle’s identification
- **`make`**: attribute for the vehicle’s make
- **`model`**: attribute for the vehicle’s model
- **`running`**: attribute for maintaining whether or not the vehicle is running. This should be set to `False` within the `__init__` method instead of being passed in at the time of instantiation.
- **`start`**: method for changing `running` to `True`
- **`stop`**: method for changing `running` to `False`

Test out the class by instantiating it a couple of times, calling `start`/`stop` methods and printing some of its attributes:

```python
car = Vehicle('TS123', 'Tesla', 'Model S')
print(car.running) # -> False
car.start()
print(car.running) # -> True
plane = Vehicle('X99Y', 'Boeing', '747-B')
print(plane.vin, plane.make, plane.model)
```
Override the __str__ method so that it returns a string formatted as:

```python
Vehicle (<vin>) is a <make> <model>
```
