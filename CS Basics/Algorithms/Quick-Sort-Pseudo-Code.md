# Quick Sort Pseudo Code

## Concept

Find a pivot, move to the end. Put one pointer at the start that moves inwards until it finds item bigger than pivot, put another pointer at the end that moves inwards until it finds item smaller than pivot. If both pointers find items, swap them. If pointers cross, swap the item with the pivot. Do this recursively for sub-arrays on each side of the pivot until complete.

```
function quickSort(array, left, right) {
    // if left < right
        // get partition point with partition(array, left, right)
        // run quickSort on left sub-array where right becomes pivotIndex - 1
        // run quickSort on right sub-array where left becomes pivotIndex
}

function partition(array, left, right) {
    // set the pivot (be sure to use left and right, not array length)
    // while left hasn't met right (EASY TO FORGET THIS PART--needs to run all available swaps)
        // move left inwards until left item > pivot
        // move right inwards until right item < pivot
        // if left <= right, swap them
            // increment/decrement left/right

    // return the partition point, left
}
```

## Code

```js
function quickSort(array, left, right) {
    if (left < right && array.length > 1) {
        const partitionPoint = partition(array, left, right);
        quickSort(array, left, partitionPoint - 1);
        quickSort(array, partitionPoint, right);
    }

    return array;
}

function partition(array, left, right) {
    const pivot = array[Math.floor((right + left) / 2)];
    while (left <= right) {
        while (array[left] < pivot) {
            left++;
        }

        while (array[right] > pivot) {
            right--;
        }

        if (left <= right) {
            [array[left], array[right]] = [array[right], array[left]];
            left++;
            right--;
        }
    }

    return left;
}

const array = [1,6,2,8,0,3,7,4,9,5];
console.log(quickSort(array, 0, array.length - 1))
```
