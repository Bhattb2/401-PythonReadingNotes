# Python Classes and Objects

[Home](../Class-Readings)

Reference
Learn about dunder methods

- Python is an object oriented programming language.

- Almost everything in Python is an object, with its properties and methods.

- A Class is like an object constructor, or a "blueprint" for creating objects. When you create a class it is created automatically to help construct an instance.

- Create Class

class MyClass:
x = 5

Create object
p1 = MyClass()
print(p1.x)

- All classes have a function called init(), which is always executed when the class is being initiated.
class Person:
def _init_(self, name, age):
self.name = name
self.age = age
p1 = Person("John", 36)

- Objects can also contain methods. Methods in objects are functions that belong to the object.

def myfunc(self):
print("Hello my name is " + self.name)
p1 = Person("John", 36)
p1.myfunc()

- The self parameter is a reference to the current instance of the class, and is used to access variables that belong to the class.

- Modify:

p1.age = 40

Delete:
del p1

## Objects
---

Objects are an encapsulation of variables and functions into a single entity. Objects get their variables and functions from classes. Classes are essentially a template to create your objects.

    class MyClass:
        variable = "blah"

        def function(self):
            print("This is a message inside the class.")

    myobjectx = MyClass()

    print(myobjectx.variable)
You can create multiple different objects that are of the same class(have the same variables and functions defined). However, each object contains independent copies of the variables defined in the class. For instance, if we were to define another object with the "MyClass" class and then change the string in the variable above:

    class MyClass:
        variable = "blah"

        def function(self):
            print("This is a message inside the class.")

    myobjectx = MyClass()
    myobjecty = MyClass()

    myobjecty.variable = "yackity"

    # Then print out both values
    print(myobjectx.variable) # blah
    print(myobjecty.variable) # yackity

###     
    class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

    myobjectx = MyClass()

    myobjectx.function() # This is a message inside the class.

### Thinking Recursively

We use recursion when we want to break a large problem into smaller sub-problems.

## Recursive Functions
 ---
         
A recursive function is a function defined in terms of itself via self-referential expressions.

This means that the function will continue to call itself and repeat its behavior until some condition is met to return a result. All recursive functions share a common structure made up of two parts: base case and recursive case.

    n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2 x 1
    n! = n x (n−1)!
###
    def factorial_recursive(n):
        # Base case: 1! = 1
        if n == 1:
            return 1

        # Recursive case: n! = n * (n-1)!
        else:
            return n * factorial_recursive(n-1)
## Maintaining State
---
When dealing with recursive functions, keep in mind that each recursive call has its own execution context, so to maintain state during recursion you have to either:

- Thread the state through each recursive call so that the current state is part of the current call’s execution context
- Keep the state in global scope
A demo might help clarify things. Calculate 1 + 2 + 3 ⋅⋅⋅⋅ + 10 using recursion. The state that we have to maintain is (current number we are adding, accumulated sum until now).

This is accomplished: by threading it through each recursive call (i.e. passing the updated current state to each recursive call as arguments):

def sum_recursive(current_number, accumulated_sum):
    # Base case
    # Return the final state
    if current_number == 11:
        return accumulated_sum

    # Recursive case
    # Thread the state through the recursive call
    else:
        return sum_recursive(current_number + 1, accumulated_sum + current_number)

## Pytest Fixtures and Coverage

- When you're writing tests, you'll have a few tests with similar characteristics, something that pytest handles with "parametrized tests".
- Those objects might contain data you want to share across tests, or they might involve the network or filesystem. These are often known as "fixtures" in the testing world, and they take a variety of different forms.
- Define fixtures using a combination of the pytest.fixture decorator, along with a function definition.

    def reverse_lines(f):

    return [one_line.rstrip()[::-1] + '\n'

    for one_line in f]

    @pytest.fixture

    def simple_file():

    return StringIO('\n'.join(['abc', 'def', 'ghi', 'jkl']))

    def test_reverse_lines(simple_file):

    assert reverse_lines(simple_file) == ['cba\n', 'fed\n', ↪'ihg\n', 'lkj\n']

- this looks like a simple function

- fixtures are used differently from global variables

- fixture might act like data, in that you don't invoke it with parentheses

- can make calculations and decisions

- if you set the scope of the fixture to be "module", it'll be available throughout your tests but will execute only a single time.

-   @pytest.fixture(scope='module') def simple_file():

    return StringIO('\n'.join(['abc', 'def', 'ghi', 'jkl']))

- Do not do the scope = 'module'

## Coverage
- "Code coverage" allows you to check that your tests have run all of the code.

    pytest --cov=my_function coverage html human readable coverage report

- This creates a directory called htmlcov. Open the index.html file in this directory using your browser, and you'll get a web-based report showing (in red) where your program still lacks coverage.