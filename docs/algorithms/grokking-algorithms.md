# Grokking Algorithms

## Chapter 1

Talks about what is an algorithm (a serie of steps to solve a problem)
How to messure an algorithm (Big O notation)
How to implement binary search, and demostrate taht is faster than a simple search.
There are some problems that doesn't have solution and need an aproximation.

```python
def binary_search(list_: typing.List[], item: int):
    low = 0
    high = len( list) - 1

    while low <= high: 
        mid = (low + high)
        guess = list_[mid]
        if guess == item:
            return mid
        if guess > item:
            high = mid - 1
        else:
            low = mid + 1
    
    return None
```


## Chapter 2

- A computer memory is like an Excel sheet and each cell has his address.
- A list uses continuous memory and save items continuously, 
while a linked list, save items in different address and link them.
- Arrays allow fast reads.
- Linked lists allow fast inserts and deletes.
- A explanation of selection sort

```python
def find_smallet(arr: typing.List[]):
    smallest = arr[0]
    smallest_index = 0
    for i in range(1, len(arr)):
        if arr[i] < smallest:
            smallest_index = i
            
    return smallest_index


def selection_sort(arr: typing.List[]):
    new_arr = []
    for i in range(len(arr)):
        smallest = find_smallest(arr)
        new_arr.append(arr.pop(smallest))

    return new_arr
```