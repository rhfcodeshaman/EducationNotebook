#note
# Subject Overview
[Lambas Explained](https://www.youtube.com/watch?v=KR22jigJLok)
[How to Use Lambdas](https://realpython.com/python-lambda/)
**Overview**:
A lambda is an anonymous function that exists on a single line of code.
```python
(lambda x,y: x+y)(4,5)
add2 = lambda x,y: x+y
```
Lambdas are made to be passed into higher-order functions and keep the code clean:
```python
nums = [3,4,5,6,7]

def my_map(my_func, my iter):
    result = []
    for item in my_iter:
        new_item = my_func(item)
        result.append(new_item)
    return(result)

cubed = my_map(lambda x: x**3, nums)
```