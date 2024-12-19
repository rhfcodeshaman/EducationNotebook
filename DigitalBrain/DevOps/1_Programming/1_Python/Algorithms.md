#note
# Subject Overview
[Algorithm Article](https://www.programiz.com/dsa/algorithm)
## Algorithms
An algorithm is a set of well-defined instructions to solve a particular problem that is independent of a programming language. It takes a set of input(s) and produces the desired output. For example:
> [!Example] An Algorithm That Adds Two Numbers
> 1. Take two number inputs
> 2. Add numbers using the `+` operator
> 3. Display the result

**Qualities of a Good Algorithm**:
- Input and output defined *precisely*
- Each step in the algorithm is clear and unambiguous
- The most effective among different ways to solve a problem
- Written in such a way that it can be used in different programming languages
# Sorting and Searching Algorithms
A sorting algorithm is used to arrange elements of an array/list in a specific order.
## Bubble Sort
A bubble sort is a sorting algorithm that compares two adjacent elements and swaps them until they are in the intended order, think of an air bubble moving to the surface of water.
> [!Example] Working of Bubble Sort - Compare and Swap
> 1. Starting from the first index, compare the first and second elements
> 2. If the first element is greater than the second, they are swapped
> 3. Now, compare the second and third elements and swap them if they are not in order
> 4. Repeat process until last element

**Python Bubble Sort**
```python
def bubbleSort(array):
    
  # loop to access each array element
  for i in range(len(array)):

    # loop to compare array elements
    for j in range(0, len(array) - i - 1):

      # compare two adjacent elements
      # change > to < to sort in descending order
      if array[j] > array[j + 1]:

        # swapping elements if elements
        # are not in the intended order
        temp = array[j]
        array[j] = array[j+1]
        array[j+1] = temp


data = [-2, 45, 0, 11, -9]

bubbleSort(data)

print('Sorted Array in Ascending Order:')
print(data)
```
## Selection Sort
Selection sort is a sorting algorithm that selects the smallest element from an unsorted list in each iteration and places that element at the beginning of the unsorted list.
> [!Example] Working of Selection Sort
> 1. Set the first element as minimum, semi-reverse of bubble sort
> 2. Compare `minimum` with the second element, if the second element is smaller than `minimum`, assign the second element as minimum
> 3. Compare `minimum` with the third element, again, if the third element is smaller, then assign `minimum` to the third, otherwise do nothing
> 4. Repeat until last element

**Python Selection Sort**
```python
def selectionSort(array, size):
   
    for step in range(size):
        min_idx = step

        for i in range(step + 1, size):
         
            # to sort in descending order, change > to < in this line
            # select the minimum element in each loop
            if array[i] < array[min_idx]:
                min_idx = i
         
        # put min at the correct position
        (array[step], array[min_idx]) = (array[min_idx], array[step])


data = [-2, 45, 0, 11, -9]
size = len(data)
selectionSort(data, size)
print('Sorted Array in Ascending Order:')
print(data)
```