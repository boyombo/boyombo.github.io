Expressions
===========

Today we will learn about expressions. I cannot think of a suitable definition for expressions but I will give examples.
```
1 + 1
```
Expressions can generally be evaluated by the python interpreter into something. If you type

```
>>> 1 + 1
2
```

python will give you the answer 2.

Let us break down the expression into component parts now. Taking the expression
```
1 + 1
```
You can see there are 3 parts, "1", "+" and "1".
"+" is the operator, it is the one that determines what happens to the other components of the expression, while "1" and the other "1" are called operands.
"+" is the addition operator, or as we all know it, the plus. Let us try some expressions on our shell
```
>>> 2 + 5
7
>>> "a" + "b"
"ab"
>>> 2 - 5
-3
>>> "a" - "b"
TypeError: unsupported operand type(s) for -: 'str' and 'str'
```
Python doesn't understand why you want to subtract one string from another. But when you try to add two strings it simply "concatenates" them, meaning it puts the first string and the second one side by side.

```
>>> "a" + "b"
>>> "ab"
```

Let us try a few more expressions and operations

```
>>> 2 * 3
6
>>> "name" * 2
"namename"
```

"*" is the multiplication operator. Multiplying 2 numbers is quite what we are used to, but multiplying a string (like "name") by a number is like adding the string to itself over and over again. What do you think will happen when you multiply a string with a fractional number?

```
>>> "name" * 1.5
TypeError: can't multiply sequence by non-int of type 'float'
```

Python doesn't understand what you mean (and neither do I).

Let us look at the kinds of division.

```
>>> 10/3
3.3333
>>> 9/3
3.0
```

"/" is the division operator, you can use "//" if you want to get rid of the decimal part of the result

```python
>>> 10//3
3
```

But if you are only interested in the remainder of a division, you use the "%" (modulo) operator.

```python
>>> 13 % 3
1
>>>15 % 3
0
```

Comparison
----------

Some operators are used for comparing different operands, examples of these are 

">" or greater than
"<" or less than
"==" or equal to
"<=" or less than or equal to
">=" greater than or equal to
"!=" not equal to

These expressions return either a True or False value. Note that the 'T' and 'F' are capitalized, and remember that python is case-sensitive. T and t are not at all the same thing.
Let us try some comparison expressions or operations.

>>> 5 > 1
True
>>> 5 < 1
False

We can get more complex

>>> 5 > (2 + 8)
False

Just like with BODMAS, (2 + 8) will evaluate to 10 and so the expression will simplify to 5 > 10, which is obviously False.
Let us try something even more fancy...

>>> 10 > 7 > 3
True
>>> 10 > 7 < 3
False

So you can chain the expressions which is like saying 10 is greater than 7 which is greater than 3.

To get even more complex combinations of expressions, we have the "and", "or" and "not" operators. Now we can get very expressive with

>>> 10 > 7 and 6 < 9
True

Though I would much rather express it like this

>>> (10 > 7) and (6 < 9)
True

So that I don't get confused about the order of evaluation of the expression. When you type this expression in thonny (your trusty editor), press Ctrl + F5 (hold down the Control key while pressing F5) and follow the order of evaluation.

Order of Evaluation
-------------------

If you have an expression like this

>>> 2 + 1 * 5

What do you get as the result? Will the "2 + 1" be evaluated first? or the "1 * 5"?
Type it into your python shell to test.

>>> 2 + 1 * 5
7

So python uses BODMAS rules it seems. In case you cannot remember this rule let me spell it out...

B(rackets)
O(f)
D(ivision)
M(ultiplication)
A(ddition)
S(ubtraction)

The higher precedents on top.

In python there are different kinds of brackets. We will meet them in subsequent discussions, but they all sort of have the highest precedence in expressions.

Next are powers (Of) something or exponents

Multiplication and division (and modulo)

Addition and subtraction

Comparisons (<, >, ==, !=, <=, >=)

Boolean operators (or, and, not)

This is not comprehensive but should be ok for us now. As for me, instead of memorizing the operator precedences, I just use a bracket to indicate what I want.

Example
-------

Try out this example in your shell

>>> english = 60
>>> math = 70
>>> avg = (english + math)/2
>>> print('Average is', avg)
Average is 65.0

Now type it into the thonny editor pane

english = 60
math = 70

avg = (english + math)/2
print('Average is', avg)

Save the file as avg.py
Then run it in thonny by pressing the F5 key


Control Flow
============

There are basically 2 fundamental ways in which you control what happens in your programs:

- Decisions
- Repititions

With these 2 things in your belt, you are able to tackle a lot of simple tasks
