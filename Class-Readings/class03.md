# Read and Write Files in Python
## Table of Contents
* [Questions](###questions)
### Questions
1. What Is a File?

A file is a contiguous set of bytes used to store data. This data is organized in a specific format and can be anything as simple as a text file or as complicated as a program executable. In the end, these byte files are then translated into binary 1 and 0 for easier processing by the computer.

        a. Header: metadata about the contents of the file (file name, size, type, and so on)
        b. Data: contents of the file as written by the creator or editor
        c. End of file (EOF): special character that indicates the end of the file

2. File Paths
The file path is a string that represents the location of a file. It’s broken up into three major parts:

        a. Folder Path: the file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)
        b. File Name: the actual name of the file
        c. Extension: the end of the file path pre-pended with a period (.) used to indicate the file type

To open a file in Python:

file = open('dog_breeds.txt')

When you’re manipulating a file, there are two ways that you can use to ensure that a file is closed properly, even when encountering an error. The first way to close a file is to use the try-finally block:

reader = open('dog_breeds.txt')
try:
    # Further file processing goes here
finally:
    reader.close()

The second option to close a file is to use the with statement:

with open('dog_breeds.txt') as reader:
    # Further file processing goes here

3. Exceptions in Python

A Python program terminates as soon as it encounters an error. In Python, an error can be a syntax error or an exception.

syntax error

>>> print( 0 / 0 ))
  File "<stdin>", line 1
    print( 0 / 0 ))
                  ^
SyntaxError: invalid syntax
exception error

>>> print( 0 / 0)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: integer division or modulo by zero
try / except

try:
    linux_interaction()
except AssertionError as error:
    print(error)
    print('The linux_interaction() function was not executed')
