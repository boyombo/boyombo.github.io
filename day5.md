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
6. `return number + 5`: the body of the function. Note the indentation. The body of the function is what the function does.

In more formal terms, functions can be defined like this...

```
def func_name(func_arguments):
    func_body
```

The first line (with the `def`) is called the header, while the rest is called the body.