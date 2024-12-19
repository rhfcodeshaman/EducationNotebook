#note
# Subject Overview
[Decorators Explained](https://www.youtube.com/watch?v=BE-L7xu8pO4)
[Decorators Article](https://pythonbasics.org/decorators/)
**Overview**:
Decorates add functionality to an existing function. This is called metaprogramming.

A decorator uses the `@` to denote that a function under the decorator needs to be passed into the decorator function.
```python
def decorator_function(func)
    def thefunbegins():
        do a thing
        func()
        do another thing
    return thefunbegins

@decorator_function
def somefunc(somearg,arg2)
	function function function
	return
```