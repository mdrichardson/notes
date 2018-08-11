# Stack/Queue

## Stack

* LIFO
* Abstract data type, meaning it's defined by its behavior and not how it represents data
* Two operations:
  * `push` adds elements to collection
  * `pop` removes most recently added
  * So, all operations occur at the end/top of the stack
* A stack can have a max/bounded capacity. If a stack is full and then a element is pushed to it, it causes a stack overflow
* In python, lists are often used as stacks with `append()` and `pop()`
  * This is `push()` and `pop()` in JavaScript
* There's a security risk for buffer overflows when using stacks. Can be prevented by verifying size of data pushed to stack prior to pushing

## Queue

* Similar to stack, but FIFO
* Commonly used in circular buffers and linked lists
* Used in python from `collections.deque` with `append()` and `popleft()`
  * JavaScript has it with `push()` and `queue.shift()`
* Queue overflow results from trying to add an element onto a full queue and queue underflow happens when trying to remove an element from an empty queue
* A bounded queue is a queue limited to a fixed number of items