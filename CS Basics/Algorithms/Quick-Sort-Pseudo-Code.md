# Quick Sort Pseudo Code

## Concept

Find a pivot, move to the end. Put one pointer at the start that moves inwards until it finds item bigger than pivot, put another pointer at the end that moves inwards until it finds item smaller than pivot. If both pointers find items, swap them. If pointers cross, swap the item with the pivot. Do this recursively for sub-arrays on each side of the pivot until complete.

```
function quickSort(array, left, right) {
    // if left < right
        // get partition point with partition(array, left, right)
        // run quickSort on left sub-array where right becomes pivotIndex - 1
        // run quickSort on right sub-array where left becomes pivotIndex + 1
}

function partition(array, left, right, pivot) {
    // while left hasn't met right
        // move left inwards until left item > pivot
        // move right inwards until right item < pivot
        // if left item > right element, swap them

    // return the partition point, left
}
```
