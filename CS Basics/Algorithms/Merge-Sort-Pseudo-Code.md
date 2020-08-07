# Merge Sort Pseudo Code

## Concept

Keep splitting array in two. Once we get to single items, compare against neighbor single item, then group them together. Do this for the other singles, then compare first item of each group against neighbor group until we're done. 

```
function mergeSort(array) {
    // stop when array length is 1
    // split array in two
    // call mergeSort on each half
    // call merge on the halves
}

function merge(a, b) {
    // create return array
    // while both arrays have length
    // add smallest of two to return array and remove from original array
    // while a has length
    // add to return array and remove from a
    // while b has length
    // add to return array and remove from b

    // return the return array
}
```
