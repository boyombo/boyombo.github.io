Decisions
=========

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

To run the program, select Run -> Run current script menu. Or you can just press the F5 key. The results will appear in the *shell* pane of thonny, and you can see the variables in the *variables* pane as well.

Run the program a few times, entering different inputs each time to see how the results will change.

Explanation
-----------

- First you ask the user of the program to enter the year they were born
- Then you subtract the year from 2017 to get the age of the user (assuming we are still in 2017)
- We then print 'You are x years old' (replace x with the age of the user)
- Now we get into the decision statement. If the age is less than 18, we give good advice, but if not we give bad advice :)

You will notice the statement `if age < 18` ends with a colon `:`.
This indicates to python that what follows will be a *block* and would be indented (use 4 spaces please, yes 4 spaces).

Structure of the if statement
-----------------------------

The `if` statement has the following structure:

`if <<condition>>:`
    `<<body>>`

- The condition must be something that can evaluate to True or False
- The body can be one or more lines of code
