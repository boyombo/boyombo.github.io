# What if?

Today we will learn about decision making in python or the `if` statement. Also we will learn more about indentation in python.
We learned in day 1 that python is quite unforgiving with indentation issues, today we see how.

You will be typing into a file named `age.py` in the top-left pane in thonny.
From the menu, select File -> New to create a new file, then File -> Save naming the file age.py.
It is good practice to save your files in a location you will be able to find later.
Now type the below code into the `age.py` file and save.

```
birthYear = int(input('Enter the year you were born: '))
currentYear = 2017
age = currentYear - birthYear
print('You are', age, 'years old')
if age < 18:
    print('You are still a minor, listen to your parents')
else:
    print("You are an adult now, congratulations!")
```

To run the program, select Run -> Run current script menu. Or you can just press the F5 key. 
The results will appear in the *shell* pane of thonny, and you can see the variables in the *variables* pane as well.

Run the program a few times, entering different inputs each time to see how the results will change.

#### Explanation

- First you ask the user of the program to enter the year they were born
- Then you subtract the year from 2017 to get the age of the user (assuming we are still in 2017)
- We then print 'You are x years old' (replace x with the age of the user)
- Now we get into the decision statement. If the age is less than 18, we give good advice, but if not we give bad advice :)

You will notice the statement `if age < 18` ends with a colon `:`. 
This indicates to python that what follows will be a *block* and would be indented (use 4 spaces please, yes 4 spaces).

#### Structure of the if statement

The `if` statement has the following structure:

`if <<condition>>:`

    `<<body>>`

- The condition must be something that can evaluate to True or False
- The body can be one or more lines of code with consistent indentation (use 4 spaces please).

True and False in python are called boolean values. When you write an expression like x > y, the result is a boolean value which means it is either True or False. 
Note that in python True and False always start with a capital "T" and a capital "F".

###### Examples of boolean expressions

```
>>> 2 > 1
True
>>> 2 < 1
False
```

###### else

The `if` statement is a little richer, it can contain an optional `else` statement. 
Let us say we have 2 variables `x` and `y`. 
Instead of

```
>>> if x > y:
        print(x, 'is greater than', y)
>>> if x <= y:
        print (x, 'is not greater than', y)
```

You can do

```
>>> if x > y:
       print(x, 'is greater than', y)
    else:
       print(x, 'is not greater than', y)
```

###### elif

You can get a little more fancy with `if` statements with the `elif` clause. 
`elif` is short for `else-if`

Write out this program in the file `whatif.py`

```
hour = int(input('What hour is it: '))
if hour < 12:
    print('Good morning')
elif hour < 17:
    print('Good afternoon')
else:
    print('Good evening')
```

You can have as many `elif` blocks as you like, for instance...

Save this as `elif.py` 

```
number = 3
guess = int(input('Choose a number between 1 and 5'))
if guess == 1:
    print('Too low!')
elif guess == 2:
    print('A little higher')
elif guess == 3:
    print('Correct!')
elif guess == 4:
    print('A little lower')
elif guess == 5:
    print('Too high!')
else:
    print('The number is not between 1 and 5')
```

#### Comparison Operators

In order to compare things in python you use operators. There are a few boolean operators (operators that result in True or False)

`==, !=, <, >, <=, >=`

`x == 5` returns True if x is equal to 5 and False if not.  
`x != 5` returns True if x is not equal to 5 and False if x is equal to 5.  
`x > 10` returns True if x is greater than 10 and False if it is less.  
`x < 15` returns True if x is less than 15 and False if x is greater.  
`x <= 4` returns True if x is for example 4, 3, 2 or 1 but False if x is 6 or 7.  
`x >= 7` returns True if x is either 7 or greater than 7, and False otherwise.  

#### More blocks

A block can contain other blocks. It is called *nesting*. 
Save this example as `nesting.py`

```
number = int(input('Enter a number between 1 and 5:'))
if number >= 1:
    if number <= 5:
        print('You entered', number);
```

You can replace this code by introducing another operator called `and`. 
Save this as `and.py`

```
number = int(input('Enter a number between 1 and 5:'))
if number >= 1 and number <= 5:
    print('You entered', number)
```

Which is easier to read than the first. 

#### More Operators

Like we said earlier, operators can be used for comparison. You can combine different comparisons with logical operators.

`and` returns True if *all* the comparisons are true else it returns False.  
`or` returns True if *any* of the comparisons are true else it returns False.  
`not` returns True if the expression is False, and it returns False if the expression is True.  

Here are some examples. Save them in logic.py

```
rice = input('Do you like rice? ')
beans = input('Do you like beans? ')
if rice == 'Yes' or rice == 'yes' or rice == 'YES':
    print('You like rice')
elif beans == 'Yes' or beans == 'yes' or beans == 'YES':
    print('You like beans')
else:
    print('No lunch for you!')
```

We will see some other operators later.
