#note
# Subject Overview
[Python Documentation](https://docs.python.org/3/tutorial/modules.html)
**Overview**:
Modules are stored scripts that can imported into other Python scripts to enhance the functionality of your programs. This is accomplished using:
```python
import <modulename> <tag such as *>
```
or
```python
from <modulename> import <modules or *>
```
**Index**:
- Module Overview
## Module Overview
A module is a file containing Python definitions and statements. The file name is the module name with the suffix `.py` appended. Within a module, the module’s name (as a string) is available as the value of the global variable `__name__`. For instance, use your favorite text editor to create a file called `fibo.py` in the current directory with the following contents:
```python
# Fibonacci numbers module

def fib(n):    # write Fibonacci series up to n
    a, b = 0, 1
    while a < n:
        print(a, end=' ')
        a, b = b, a+b
    print()

def fib2(n):   # return Fibonacci series up to n
    result = []
    a, b = 0, 1
    while a < n:
        result.append(a)
        a, b = b, a+b
    return result
```
Now enter the Python interpreter and import this module with the following command:
```python
import fibo
```
This does not add the names of the functions defined in `fibo` directly to the current [namespace](https://docs.python.org/3/glossary.html#term-namespace) (see [Python Scopes and Namespaces](https://docs.python.org/3/tutorial/classes.html#tut-scopes) for more details); it only adds the module name `fibo` there. Using the module name you can access the functions:
```python
fibo.fib
fibo.fib2
```
Use this variant of import to import names directly from the module into the importing module's namespace:
```python
from fib import fib1,fib2
```
OR
```python
from fib import *
```
This imports all names **EXCEPT** those starting with an underscore `_`.
