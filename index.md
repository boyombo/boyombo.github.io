Yet Another Python Tutorial
===========================

Hi there, I have broken the tutorial into days/chapters, and here they are:

[day1](day1)
[day2](day2)

Python is my goto language for development because of a simple reason. It has a very simple and small syntax (different commands you can use) and yet can do really awesome thing. Unlike most languages I have used in the past, and some I still use today, with python I hardly spend any time thinking of the syntax of the language or how it will behave in certain circumstances. I spend most of my time thinking of the problem I want to solve and how to model it in ways that make sense, trusting that python will do the rest.

One of the most important points to the people who maintain the language is clarity. You read code much more than you write it, so it makes sense to optimize for readability of your code. You need to keep that in mind when programming in any language, and especially in python.

Some of the notable features of python are:
    - Elegant syntax that is easy to read
    - Easy to use and learn
    - Large library so you can do lots of stuff with it
    - Interactive shell for experimentation (we will see this very soon)
    - Runs on just about any operating system (linux, windows, mac and even on mobile)
    - It is free and open source
    - High productivity, it helps you write code very quickly


Installing python
=================

So we will start by installing a python environment which is tailor-made for learning the language. It is called "Thonny".
Thonny is an IDE (Integrated Development Environment) which is a big name for the tool you use to write your code, and which helps you make the process as painless as possible.
Download thonny from [thonny](http://thonny.org) for your operating system.
You can find instructions for installation here if you need it

[for Windows](https://bitbucket.org/plas/thonny/wiki/Windows)
[for Mac](https://bitbucket.org/plas/thonny/wiki/MacOSX)
[for Linux](https://bitbucket.org/plas/thonny/wiki/Linux)

After installing thonny, take a look at the features on [thonny home page](http://thonny.org) for a bit and try it out on your installation.
Let us walk through them step by step.

1. First open thonny
    You will notice that it shows something like the figure below
    
![Thonny](http://thonny.org/img/screenshot.png)

2. Before you start coding, save the file as "hello.py"
3. Type `print('Hello world!')`
4. From the Run menu select "Run current script" or click on the "play" toolbar button, or just press f5.
5. You will see "Hello world!" printed on the bottom half of the environment.


The interpreter (not Wole Soyinka)
==================================

So, python is an interpreted language, meaning each line of code is executed as you type them. 
The lower part of thonny with a blinking cursor is your interpreter console (where you can type commands that will be interpreted) which we will call the python "shell" from now on.

type:

```python
print("hello world")
```

then press the [enter] key. You should see `hello world` printed after like this

```python
>>> print("hello world")
hello world
```

Let us try doing some math. Type each line into the shell, press the [enter] key and note the result you get

```python
>>> 2 + 2

>>> 10 - 5 + 6

>>> 2 * 7

>>> 5 / 2
```

Now let us see how to get help in the shell in case we can't remember what a particular keyword does

```python
>>> help(len)

Help on built-in function len in module builtins:

len(obj, /)
    Return the number of items in a container.
```

You use the python shell to experiment with your code. It is very useful and you will use it more and more often as you go.

Note:
-----

> Whenever I write something beginning with `>>>` it means I expect you to type it in the python shell

The Editor
==========

The editor is the top pane of thonny where you type your code into a file. Unlike the shell, the things you type into a file and save are not lost if you restart thonny.

>Note: You need to make a directory where you keep the files of this tutorial, you can name it anything but I will assume it is called pytutorial.


Data
====

Let us spend some time printing things in the shell to get a grasp of what kinds of data python supports.
As usuall, when you see `>>>` it means you should type whatever comes after it into the shell and press [enter]

```python
>>> 5
5

>>> 2.67
2.67
```

Numbers, python supports both integers and floating point numbers (numbers that have decimal places)

```python
>>> 'Everybody must vote in 2019'
'Everybody must vote in 2019'

>>> "Nobody has a voters card"
'Nobody has a voters card'
```

In python strings (you can think of them as plain text, like your address or name) are put inside quotes ('' or ""). Single quotes and double quotes are treated alike in python, though you are not allowed to mix them.

```python
>>> "One more bottle'
SyntaxError: EOL while scanning string literal
```

This will give you a "SyntaxError". It is an error to tell you that python does not understand what you just typed. Luckily, thonny will let you know when you are making such mistakes.
One nice thing you can do with double and single quotes is when you want to write something like this:

```python
>>> "That's my name"
"That's my name"
```

Because the single quote is between double quotes, python understands what you are trying to do.

How about mixing numbers and strings?

```python
>>> "I am 10 years old"
"I am 10 years old"
```

Here the number 10 is treated as a string because it is inside quotes.

```python
>>> '10' + '10'
'1010'
```

You see that python does not take them as numbers.

Let us try and be sly...

```python
>>> '10' + 10
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

We get another kind of error called a "TypeError". It means you are trying to do something with data types that are not quite correct.
You cannot add a string to a number. Just like saying you want to add some money to your name, #kolewerk

But python has a technique if you want to really really mix strings with numbers, it is called the 'format' method (don't worry we will discuss what methods are later)
Let us try a small exercise...

```python
>>> age = 10
>>> name = 'bayo'
>>> '{} is {} years old'.format(name, age)
'bayo is 10 years old'
```

You see that we use format to tell python to replace some placeholders {} with real values for name and age.

There is another way we can achieve the same end without using format, but it is not quite as elegant. For full disclosure, here it is:

```python
>>> age = 10
>>> name = 'bayo'
>>> name + ' is ' + str(age) + ' years old'
'bayo is 10 years old'
```

Here we had to use `str` function to convert the number to a string, then we just added (actually called concatenated) the strings together.

The usual way to print data to the screen is by using the `print` function

```python
>>> name = 'bayo'
>>> print(name)
'bayo'
```

Variables
=========

You will have noticed that we have just been printing data to the screen, that is not how all of programming is. It would have been nice though, but not very useful.
A lot of the time, you want to do something with the data, sometimes you want to do a lot with the data.
In this case you will want to store the data somewhere in memory. Trust me you don't want to know where every bit of data you need is stored in memory, what you want is a way to say 'Hey python, give me the data you stored somewhere that I called x', in this case 'x' is a variable.
So variables are names we give to data stored somewhere in memory.

```python
>>> x = 1
>>> y = 6
>>> z = x + y
```

In this case we have defined 3 variables, x, x and z
On thonny, select View -> Heap from the menu. You will see a pane showing "ID" and "value". Also make sure you have the Variables pane open (View -> Variables).
On the variables pane, you will see the name you gave the variable and the location in memory that the variable is stored.
On the heap pane you will see the address in memory and the value stored in it.

Now you know that variables are simply convenient names you give to pieces of your data, you should keep in mind a couple of simple rules for naming variables:

 - Varible names should start with an alphabet (or underscore)
 - Variable names can consist of alphabets, numbers or underscores.
 - Names are case-sensitive. So `name` is not the same as `nAme` which is not the same as `Name`. This is the most important rule because python may simpy assume you are defining two different variables when you actually wanted to refer to the same one.

 Indentation
 ===========

 Indentation is very important in python. Indentation is whitespace (space, tab, etc...) at the beginning of a line of code. For example let us look at the last code we wrote

```python
>>> x = 1
>>> y = 6
>>>  z = x + y

SyntaxError: unexpected indent
```

Looks very harmless but python will complain about it. All lines that go together must have the same indentation.

Note on indentation:
    Use four spaces for indentation. This is the official Python language recommendation. Good editors will automatically do this for you. Make sure you use a consistent number of spaces for indentation, otherwise your program will not run or will have unexpected behavior.

Input
=====

I am getting a little ahead of myself here, but I want us to write a couple of interesting exercises and so here we go...

```python
>>> name = input('Enter your name: ')
Enter your name: bayo
>>> name
bayo
```

Here you should type this first
`>>> name = input('Enter your name: ')`

Then you will see 
`'Enter your name: '`
with the cursor blinking on the next line. This is an indication that it is expecting input from you. Whatever you enter (and press the [enter] key) will be stored as the variable `name`.

So when you type
`>>> name`
on the shell you get whatever you typed in back.

Exercises
=========

1. Write a program to ask for your name and your friend's name. The the program will print out "`your name` and `your friend's name` are friends"

2. Write a program that will ask for your name and age, then print out "`your name` is `your age` years old"
