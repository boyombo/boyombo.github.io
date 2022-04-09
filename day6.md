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
    kind = 'Toyota'

>>> c = Car()
>>> c.kind
'Toyota'
```

Here we have defined a class Car which is kind of the blueprint for making cars, and have "made" (instantiated) a specific Car object called c.
You will also notice that the car we have created has a kind. this is a variable (field) who's scope is local to the car object created.
A variable of a class is kind of a description or quality of the car. 
Variables in classes are called "fields"

Unfortunately there isn't much we can do with this particular Car, we can't drive it or refuel for instance.
drive() and refuel() are things that cars do, not really qualities of the car. They are functions that the car can perform.
Functions in classes are called methods.
Note that methods and fields are accessed via the dot-notation (.)
Also note that the definition of a class is indented after the :, that is in a block
A class can have many fields and methods

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
Classes have a means to customize the data using a constructor, called __init__ in python.
Note that __init__ has double underscores (called dunder sometimes).
The __init__ function runs just after the object is created, and you can pass in parameters that will be used
to customize the specific instance.

```python
class Car:
    def __init__(self, kind, fuel_guage):
        self.kind = kind
        self.fuel_guage = fuel_guage
    
    def drive(self, dist):
	    self.fuel_guage -= dist
	
    def refuel(self, qty):
        self.fuel_guage += qty


>>> 
>>> c = Car(kind='Honda', fuel_guage=10)
>>> c.kind
'Honda'
>>> c.fuel_guage
10
>>> m = Car(kind='BMW', fuel_guage=20)
>>> m.drive(10)
>>> m.fuel_guage
10
>>> m.refuel(5)
>>> m.fuel_guage
15
```

Here we have the __init__ method to customize the properties of the car instantiated. Note the difference between self.kind and kind.
self.kind means a field in the class called kind, while the other kind was passed in via the __init__ method
And we also have 2 methods, drive and refuel.
You will notice that methods in python usually have a first argument called "self"

What is Self?
-------------

A method is a function that belongs to a class.
self is the first parameter passed into a method and is also used to reference variables inside the class.
So in our example above self is used to refer to instance variables

```python
class Car:
    def __init__(self, type, fuel_guage):
        self.type = type
        self.fuel_guage = fuel_guage
    
    def drive(self, dist):
        self.fuel_guage -= dist
    
    def refuel(self, qty):
        fuel_guage += qty


>>> 
>>> c = Car('Honda', 20)
>>> c.refuel(10)
Traceback (most recent call last):
  File "<pyshell>", line 1, in <module>
  File "/Users/bayo/Development/test/thonny/name.py", line 10, in refuel
    fuel_guage += qty
UnboundLocalError: local variable 'fuel_guage' referenced before assignment
>>> 
```

If we do not refer to the variables using self, we get an error.


Classes Everywhere
------------------

Actually, in python everything is an object. Which means you can find the "type" of a thing by using the type() function

```python
>>> type(1)
<class 'int'>
>>>
>>> c = Car('Honda', 10)
>>> type(c)
<class '__main__.Car'>
>>> 
```

So even integers have a type as well as your own objects.
The type of an object is the class (blueprint) used to instantiate it.


Class and Instance Variables
----------------------------

You need to be careful when defining variables inside classes. We can define either class or instance variables.
Personally I try to keep all my fields as instant variables except I really really really really.... need class variables
But here we go...

Class variables are owned by the class and not the instance, while
Instance variables are owned by the individual object created.

```python
class Person:
    nationality = 'Nigerian'
    
    def __init__(self, gender):
        self.gender = gender
    
    @classmethod
    def change(cls, new_nationality):
        cls.nationality = new_nationality

>>>
>>> p1 = Person('Female')
>>> p2 = Person('Male')
>>> p1.gender
'FeMale'
>>> p2.gender
'Male'
>>> p1.nationality
'Nigerian'
>>> p2.nationality
'Nigerian'
>>> # If you want to change the class variable you use need to make a "class method"
>>> # this is different from a normal method because it acts on the entire class instead of an instance of the class
>>> # The preferred way to make a class method is to use a "decorator" @classmethod.
>>> # then in the method, pass the class as the first argument instead of self. The convention is to use cls.
>>> p1.change('Indian')
>>> p1.nationality
'Indian'
>>> p2.nationality
'Indian'
>>> 
```

Now if you change the nationality of one instance, it will change for every other instance.
You know how it is that your speedometer is up to 260 even though you don't go past 120?
This is kind of a 150 km/hr speed. You are not likely to need it on a day to day basis.


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


< [Functions](/day5) | [Classes](/day6) >