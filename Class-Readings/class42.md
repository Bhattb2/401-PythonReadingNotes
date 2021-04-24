# Pythonsims

Dunder methods, or magical mehods, like `__init__()` are not magicial. It's just normal python.

Iterators

You can define your own iterable class using `__iter__()` and `__next__()` so that you can use `for-in` loops.

There is a corresponding `iter()` and `next()` pair of functions that will invoke those two above dunder methods.

To avoid an infinite loop with an iterator, you'll need to manage incrementing your iteration, and then define some stopping condition.

Python uses an exception to break the iterations loop for when you've reached some stopping condition for iteration; `raise StopIteration`

An example from a tutorial:

    repeater = BoundedRepeater('Hello', 3)
    iterator = iter(repeater)
    while True:
        try:
            item = next(iterator)
        except StopIteration:
            break
        print(item)

## Generators

Introducing 'yield` which behaves much like a temporary version of return. Return will terminate a function and pass back control to the coller, while yield will preserve that same fucntions state and pass back control temporarily.

Generators raise a StopIteration exception any time the control flow leaves the generator fucntion, except through a `yield` statement.