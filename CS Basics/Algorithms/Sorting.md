# Sorting Algorithms

[Neat site showing all of these in action](https://www.toptal.com/developers/sorting-algorithms)

## Bubble

1. Starts at start of list
2. If next item is smaller, they swap places and this continues until next item is no longer smaller
3. Starts over

* Worst case performance: O(n^2)
* Best case performance: O(n)
* Average case performance: O(n^2)

* Too slow and impractical for most problems. Only really practical if input is mostly sorted already

## Insertion

* Process is like sorting playing cards. Select a card and insert it between the lower/higher values

* Worst case performance: O(n^2)
* Best case performance: O(n)
* Average case performance: O(n^2)

* Useful only for very small arrays

## Merge

* Uses divide and conquer strategy

1. Divide list into smallest unit (1 element)
2. Compare each element with adjacent element so you have sorted pairs
3. Compare first element of first list with each element of neighbor list and merge into group of 4
4. Repeat until fully sorted into 1 list

* Worst case performance: O(n log n)
* Best case performance: O(n)
* Average case performance: O(n)

* Outperformed by RAM-based arrays, but more efficient at slow-to-access sequential media

## Quick

* Can be performed in-place on an array
* Uses divide and conquer

1. Pick an element, called a pivot
2. Reorder the array so that all elements with values less than pivot come before pivot, and all values greater than come after
3. Recursively apply above steps to each sub-array separated by pivot

* Worst case performance: O(n^2)
* Best case performance: O(n log n) or O(n) with three-way partition
* Average case performance: O(n log n)

* Best used to save space

