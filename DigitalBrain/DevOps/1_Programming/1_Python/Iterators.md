#note
# Subject Overview
[Iterator Article](https://www.w3schools.com/python/python_iterators.asp)
**Overview**:
An iterator is an object that contains a countable number of values.
An iterator is an object that can be iterated upon, meaning that you can traverse through all the values.
Technically, in Python, an iterator is an object which implements the iterator protocol, which consist of the methods `__iter__()` and `__next__()`.
```python
iter1 = [1,2]
iter2 = ("item1","item2")
iter3 = {"key1": 1, "key2": 2}
```
Lists, tuples, dictionaries, and sets are all iterable objects. They are iterable _containers_ which you can get an iterator from.
All these objects have a `iter()` method which is used to get an iterator.
Technically even strings are iterable objects, containing a sequence of characters.