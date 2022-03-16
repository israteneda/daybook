# Grokking Algorithms

## First Chapter
```
def binary_search(l: typing.List[], e: int):
    start = 0
    end = len(l) - 1
    mid = (end - start) // 2
    while True:
        if e == mid:
            break
        if e < mid:
            high = mid
        if e > mid:
            start = mid
        mid = (end - start) // 2
```