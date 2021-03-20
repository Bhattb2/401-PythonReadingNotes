# What is Jupyter Lab
JupiterLab
JupyterLab enables you to work with documents and activities such as Jupyter notebooks, text editors, terminals, and custom components in a flexible, integrated, and extensible manner.

[jupyter.org](https://jupyter.org/about)

# NumPy Tutorial
[Numpy](https://www.dataquest.io/blog/numpy-tutorial-python/)

NumPy is a commonly used Python data analysis package. By using NumPy, you can speed up your workflow, and interface with other packages in the Python ecosystem, like scikit-learn, that use NumPy under the hood. NumPy was originally developed in the mid 2000s, and arose from an even older package called Numeric. This longevity means that almost every data analysis or machine learning package for Python leverages NumPy in some way.

[Numpy Arrays](https://www.tutorialspoint.com/numpy/index.htm)

NumPy
Read a csv file

import csv
with open('winequality-red.csv', 'r') as f:
    wines = list(csv.reader(f, delimiter=';'))

### breaks the csv.reader at the delimiter ";" instead of standard ","


- Extract the last element from each row after the header row.
- Convert each extracted element to a float.
- Assign all the extracted elements to the list qualities.
- Divide the sum of all the elements in qualities by the total number of elements in qualities to the get the mean.

qualities =
[float(item[-1]) for item in wines[1:]]
sum(qualities) / len(qualities)

Numpy 2-Dimensional Arrays
- In a NumPy array, the number of dimensions is called the rank, and each dimension is called an axis. So the rows are the first axis, and the columns are the second axis.
- One of the limitations of NumPy is that all the elements in an array have to be of the same type, so if we include the header row, all the elements in the array will be read in as strings.

import csv

with open("winequality-red.csv", 'r') as f:

    wines = list(csv.reader(f, delimiter=";"))

import numpy as np

wines = np.array(wines[1:], dtype=np.float)


In the above code, we:

1. Import the numpy package.
2. Pass the list of lists wines into the array function, which converts it into a NumPy array.
3. Exclude the header row with list slicing.
4. Specify the keyword argument dtype to make sure each element is converted to a float. We’ll dive more into what the dtype is later on.
5. check out the rows and columns using command - wines.shape

- NumPy has several data types.

    - float — numeric floating point data

    - int — integer data.

    - string — character data.

    - object — Python objects.


NumPy, which stands for Numerical Python, is a library consisting of multidimensional array objects and a collection of routines for processing those arrays. Using NumPy, mathematical and logical operations on arrays can be performed.

Standard Python distribution doesn't come bundled with NumPy module. A lightweight alternative is to install NumPy using popular Python package installer, pip.

>pip install numpy

The best way to enable NumPy is to use an installable binary package specific to your operating system. These binaries contain full SciPy stack (inclusive of NumPy, SciPy, matplotlib, IPython, SymPy and nose packages along with core Python).

Linux Package managers of respective Linux distributions are used to install one or more packages in SciPy stack.

For Ubuntu

sudo apt-get install python-numpy 
python-scipy python-matplotlibipythonipythonnotebook python-pandas 
python-sympy python-nose