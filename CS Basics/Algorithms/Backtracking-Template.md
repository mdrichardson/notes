# Backtracking Template

Backtracking recursive functions all have a similar layout. Here's a basic template for getting it started.

## Pseudo-Code

```
mainFunction(input) {
  // create pointer for returnArray
  // call backtrack() with appropriate args, including return array and starter args
  // return return array
}

backtrack(returnArray, current, **args) {
  // Handle base case
    // base case usually adds current array/string to returnArray
  // call backtrack(returnArray, current, **args) for all possible decisions, ensuring to change args to represent a possible decision
    // may need to reset current after backtrack call
}