# Arrays

* Stored sequentially in memory
* In Python, arrays are declared with `x = array([1, 2, 3])`
  * You can do math on array but not on list. `x*3` would result in `[3, 6, 9]`
  * Array shouldn't mix data types
* Frequently used in matrices (list of lists)
* Could be used as switch statements:

```python
days = ['Monday', 'Tuesday'...]
def getDay(index):
    return days[index]
```

* Most languages use row-major order. Difference:

For matrix:

```
1   2   3
4   5   6
7   8   9
```

Row-Order:

```python
[
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
```

Column-Order (used by Fortran):

```fortran
[
    [1, 4, 7],
    [2, 5, 8],
    [3, 6, 9]
]
```

* Selecting is fast and operates at `O(1)`
* Arrays use less memory than if you stored elements as individual variables
* Deletion and insert can be expensive, since elements may have to change index if inserted/deleted from beginning or middle
* Fixed size with an upper limit
