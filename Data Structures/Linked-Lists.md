# Linked Lists

* Stored anywhere in memory. To link, each node must have the data and the memory address of the next node
* Dynamic size
* Elements must be accessed sequentially, instead of via memory index, like an array
  * Operates at `O(n)`
* Uses more memory than array because a pointer is required for each element, but this makes insertion and deletion fast