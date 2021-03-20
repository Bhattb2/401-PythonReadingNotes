# List Comprehensions
[Home](../Class-Readings)

[Referenes](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python)

List comprehensions provide a concise way to create lists.
- It consists of brackets containing an expression followed by a for clause, then zero or more for or if clauses. The expressions can be anything, meaning you can put in all kinds of objects in lists.
- The result will be a new list resulting from evaluating the expression in the context of the for and if clauses which follow it.
- The list comprehension always returns a result list.

>new_list = [expression(i) for i in old_list if filter(i)]
>
>new_list = []
> 
> for i in old_list:
>
>if filter(i):
>
>new_list.append(expressions(i))

>**result* * = [*transform* *iteration* *filter* ]

>[x+y for x in [10,30,50] for y in [20,40,60]]
>
>[30, 50, 70, 50, 70, 90, 70, 90, 110]


You can obtain the same thing using list comprehension. Notice the append method has vanished!

    new_list = [expression(i) for i in old_list if filter(i)]
**new_list** The new list (result).

**expression(i)** Expression is based on the variable used for each element in the old list.

**for i in old_list** The word for followed by the variable name to use, followed by the word in the old list.

**if filter(i)** Apply a filter with an If-statement.

### Examples:

    list1 = [3,4,5]
 
    multiplied = [item*3 for item in list1] 
 
    print multiplied 
    [9,12,15]




    listOfWords = ["this","is","a","list","of","words"]

    items = [ word[0] for word in listOfWords ]

    print items
    The output should be: [‘t’, ‘i’, ‘a’, ‘l’, ‘o’, ‘w’]

## Using list comprehension in functions
---
### Now, let’s see how we can use list comprehension in functions.

    # Create a function and name it double:
    def double(x):
        return x*2


    # If you now just print that function with a value in it, it should look like this:
    >>> print double(10)
    20
### We can easily use list comprehension on that function.

    >>> [double(x) for x in range(10)]

    print double
    [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]

    # You can put in conditions:

    >>> [double(x) for x in range(10) if x%2==0]
    [0, 4, 8, 12, 16]

    # You can add more arguments:

    >>> [x+y for x in [10,30,50] for y in [20,40,60]]
    [30, 50, 70, 50, 70, 90, 70, 90, 110]


# Primer On Decorator
--
[References](https://realpython.com/primer-on-python-decorators/)

Decorators provide a simple syntax for calling higher-order functions.

## Functions as First-Class Objects
In Python, functions are first-class objects. This means that functions can be passed around and used as arguments, just like any other object (string, int, float, list, and so on).

It’s possible to define functions inside other functions. Such functions are called inner functions.

The inner functions are not defined until the parent function is called. They are locally scoped to parent(): they only exist inside the parent() function as local variables.

Python also allows you to use functions as return values, this means that you are returning a reference to the function.

# Simple Decorators