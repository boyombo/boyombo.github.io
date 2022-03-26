Control Flow (contd)
====================

# Repetitions

Computers are really good at doing things many many times. We will look at two ways of doing repetitions or loops in python.  

#### While loop

The first way is called the while statement. Let us look at an example.  

```
counter = 10
while counter > 0:
    print("current count is", counter)
    counter = counter - 1
print("done")
```

The while loop runs while a condition evaluates to True.
In the example above, we declare a variable called counter and initialize it to 10.  
We then set up the loop condition to be `counter > 0`
Then we have the body of the loop (what the loop is actually doing), printing the value of the counter.
Note that inside the loop, we reduce the value of the counter so that after the first run, the counter is 9, then 8, 7, 6, 5, 4, 3, 2, 1 and then 0.  
At that point, the test (`counter > 0`) will fail and the loop will terminate, so control goes to the last statement `print("done")`.  

There are a couple of similarities to the `if` statement here:

- The first line (or header) of the while loop terminates with a `:`
- The body of the while loop is indented (use 4 spaces please)

Let us try another example.  

```
number = int(input('Enter a number between 1 and 5: '))
while number > 0:
    print('The number is now', number)
    number = number - 1
print('The end')
```

###### break

You can break a loop with a `break` statement inside the loop. This will move control from out of the loop to the next statement outside it.  

```
counter = 10
while counter > 0:
    print("current count is", counter)
    counter = counter - 1
    if counter < 5:
        break
print("done")
```

Here we put a condition that the loop should break if the counter goes less than 5

###### continue

You can abort the current loop you are running and continue with the next item in the loop with the `continue` statement.

```
counter = 0
while counter < 10:
    if counter == 7:
        continue
    print("current count is", counter)
    counter = counter + 1
```

Here the program will skip printing when the counter is 7 and go straight to the next item.  

#### for loop

The `for` statement *iterates* over a collection of items, or a sequence.  
Let us say we have a list `lst = [2, 3, 5, 7, 11]`, you can use a `for` loop to go through each of the items in the list.  

```
lst = [2, 3, 5, 7 , 11]
for item in lst:
    print('The current number is ', item)
```

You can also use the `break` statement to leave the loop early, for instance.  

```
lst = [2, 3, 5, 7, 11]
for item in lst:
    print('The current number is', item)
    if item == 7:
        print('Reached ', item, ', exiting...')
        break
print("done")
```

And you can use the `continue` statement to leave off the remaining statements in the current loop and go to the start of the loop again with the next item of the collection.  

With decisions (if-elif-else) statements and looping statements you are basically set to program in python.  
The rest are simply ways to make your life as a python programmer easier.

[<< Control Flow](/day3) | [Functions >>](/day5)
