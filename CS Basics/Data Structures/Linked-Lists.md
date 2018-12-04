# Linked Lists

* Stored anywhere in memory. To link, each node must have the data and the memory address of the next node
* Dynamic size
* Elements must be accessed sequentially, instead of via memory index, like an array
  * Operates at `O(n)`
* Uses more memory than array because a pointer is required for each element, but this makes insertion and deletion fast
* Since a linked list uses constant time for insertion and deletion at the ends, it would be better to use for a stack/queue than an array
* A doubly-linked list links forwards AND backwards