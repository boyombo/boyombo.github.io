Classes
=======

Classes are another way to organise our code.
There is a concept called "encapsulation" that helps us a lot when programming.
Basically in order to solve complex problems, it is useful to treat parts of the problem like single entities that we know and understand.

Let us consider an example in real life:
Let us say you want to make lunch. You have egusi, water, ugu, meat, stockfish, seasoning, salt, a pot, garri, etc...
An hour later when you are done with cooking, you now have egusi soup (hopefully) and eba. At this point it is sometimes useful to talk in terms of the soup (or meal) as a whole instead of the individual components.
We say the concept of "egusi soup" encapsulates all the ingredients and the things you can do with the soup

# Defining Classes

A class in python is a blueprint for creating `objects`. Like a recipe.

Write this in a script classes.py
```
class Car:
    type = 'Toyota'

>>> c = Car()
>>> c.type
'Toyota'
```

Here we have defined a class Car and have instantiated it by making a Car object called c.
Unfortunately there isn't much we can do with this particular Car, we can't drive it or refuel for instance.
Let's do a little better.

```python
class Car:
	type = 'Toyota'
	fuel_guage = 20

	def drive(self):
	    self.fuel_guage -= 1

>>> 
>>> c = Car()
>>> c.fuel_guage
20
>>> c.drive()
>>> c.fuel_guage
19
>>> 
```

Usually you want to to have the ability customize the construction of your objects.
For instance you don't want all the cars in the world be Toyota and have only a 20 lt tank by default.
Classes have a means to customize the data during construction.

```python
class Car:
    def __init__(self, type, fuel_guage):
        self.type = type
        self.fuel_guage = fuel_guage
    
    def drive(self, dist):
	    self.fuel_guage -= dist
	
    def refuel(self, qty):
        self.fuel_guage += qty


>>> 
>>> c = Car(type='Honda', fuel_guage=10)
>>> c.type
'Honda'
>>> c.fuel_guage
10
>>> m = Car(type='BMW', fuel_guage=20)
>>> m.drive(10)
>>> m.fuel_guage
10
>>> m.refuel(5)
>>> m.fuel_guage
15
```

What is Self?
-------------

A method is a function that belongs to a class.
self is the first parameter passed into a method and is also used to reference variables inside the class.


Inheritance
-----------

You can inherit one class from another and it means you can get all the functionality from the parent class in the child class

```python
class SUV(Car):
    def offroad(self, dist):
        self.fuel_guage -= 2 * dist


>>> s = SUV(type='Benz', fuel_guage=30)
>>> s.drive(1)
>>> s.fuel_guage
29
>>> 
>>> s = SUV(type='Benz', fuel_guage=30)
>>> s.drive(1)
>>> s.offroad(2)
>>> s.fuel_guage
25
>>> c = Car(type='Benz', fuel_guage=20)
>>> c.drive(1)
>>> c.offroad(3)
Traceback (most recent call last):
  File "<pyshell>", line 1, in <module>
AttributeError: 'Car' object has no attribute 'offroad'
>>> 
```

Above, the SUV can perform the functionality of the Car but also has the offroad function.


What I like classes for
-----------------------

I like using classes to encapsulate logic.