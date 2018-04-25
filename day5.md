Functions
=========

Functions are a primary way to organise our code.
We can imagine python functions to be a mathematical function `f(x) = y`

`f` is our function
when we put `x` into it we get `y`

Let us look at an examples in algebra:

```
let f(x) = x + 5
    If we make x 10, y becomes 15
    If we make x 5, y becomes 10
```

Functions in python are similar but not identical, but first let us see how to make functions.

# Making Functions

You create a function by using the `def` keyword and then writing the *body* of the function within a block (don't forget to indent!)
Let us make one quick one for breakfast!

```
def add_five(number):
    return number + 5
```

This will do what the math function we typed above does, add 5 to a number and return it.

Let us break the function down a bit...

1. `def`: keyword to tell python to make a function for us
2. `add_five`: the name of the function (we need the name in order to access the function later, just like with variables)
3. `()`: brackets to contain the things we want to pass into the function
4. `number`: a name we give to what we are passing into the function, they are called arguments and they can be many, one or none.
5. `:`: A colon after the closing bracket
6. `return number + 5`: the body of the function. Note the indentation. The body of the function is what the function does. The `return` here means that when the function runs it will give you something at the end of it. In this case it will give you the initial number plus 5. We will see what it means to return a value next.

In more formal terms, functions can be defined like this...

```
def func_name(func_arguments):
    func_body
```

The first line (with the `def`) is called the header, while the rest is called the body.

# Return values

Though return values are not compulsory for functions but they are pretty useful, like when you `send` your younger brother or sister to go buy akara and yam. The input is the money and the output "akara and yam" (or cock and bull excuses how the money got lost etc...).
Let us try another function

```
def retirement(current_age):
    retirement_age = 60
    years_to_retirement = 60 - current_age
    return 2018 + years_to_retirement
```

The function above takes your current age and predicts what year you will retire, assuming 60 is the retirement age (so you have another 20 years enjoying yourself, yay!)

# calling it

```
retirement(25)
```

or 

```
end_of_slavery = retirement(25)
```

### No return values

Not all functions have return values, sometimes you just want the function to do something, like when you ask your son/daughter to sweep the sitting room. You get a "partially" swept room, but they don't exactly bring the house to you. Also, remember when you needed to remind your little cousin to greet when visitors come to the house? They don't exactly return the greeting to you.
Let us write a greeting function

```
def greet():
    print("Good morning ma");
```

Here you notice that we don't have any return statement, we just print out `Good morning ma` and are done with it. Sometimes that is what we want a function to do. You will also notice that we don't have any arguments in the function (sometimes a knock on the cousin's head is required), functions don't require arguments either.

### How to scope

There are a few things we need to be careful of when we use functions in python. One is scoping (not your neighbour abeg).

```
>>> x = 10
>>> def printer():
    print(x)
    
>>> printer()
10
>>> 
```

Here we can notice that the `printer` function can "see" `x` that was defined outside it.
Let us be a bit more curious...

```
>>> x = 10
>>> def printer():
    x = 20
    print(x)
    
>>> printer()
20
>>> x
10
>>> 
```

Here we defined an `x` outside the function `printer`, and another one inside it.
When we `call` the function it returns the `x` that was defined inside it but it doesn't change the `x` defined outside the function as you can see when we check the value of `x` later.
We learn 2 things here

1. Varibles defined in an "outer" scope are visible in an "inner" scope.
2. Variables defined in an "inner" scope override those
3. Variables defined in an "inner" scope are not available in an "outer" scope

/****** NOT CLEAR ENOUGH
At this point it may be relevant to discuss what a scope is. First in "akara and yam" terms.

When you ask your little cousin to buy akara you call the `buy_akara` function, passing in the money.
In the body of the function we have money. But things outside the function can affect the function as well, like whether or not it is raining or the price of akara (no point sending him with N50 when akara costs N100).

However, what you have inside the function is not visible outside of it.
*********/