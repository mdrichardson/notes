# Merge Sort Pseudo Code

## Concept

Keep splitting array in two. Once we get to single items, compare against neighbor single item, then group them together. Do this for the other singles, then compare first item of each group against neighbor group until we're done. 

```
function mergeSort(array) {
    // stop when array length is 1
    // split array in two (left/right)
    // set each half to mergeSort(half)
    // call merge on the halves and return
}

function merge(a, b) {
    // create return array
    // while both arrays have length
        // add smallest of two to return array and remove from original array - use index 0 and push(shift())
    
    // while a has length
        // add to return array and remove from a
    // while b has length
        // add to return array and remove from b
        
    // Alternatively to last two while statements, just returnArray.concat(left, right)

    // return the return array
}
```


## Code

```js
function mergeSort(array) {
    if (array.length <= 1) return array;

    const mid = Math.floor(array.length / 2);
    let left = array.slice(0, mid);
    let right = array.slice(mid);

    left = mergeSort(left);
    right = mergeSort(right);

    return merge(left, right);
}

function merge(left, right) {
    const returnArray = [];

    while (left.length && right.length) {
        if (left[0] <= right[0]) {
            returnArray.push(left.shift());
        } else {
            returnArray.push(right.shift());
        }
    }

    return returnArray.concat(left, right);
}

console.log(mergeSort([1,6,2,8,0,3,7,4,9,5]))
```
