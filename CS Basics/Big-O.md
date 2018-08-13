# Big O Notation

![Big O Time Complexity](https://www.nickang.com/wp-content/uploads/2017/11/big-o-notation-complexity-from-stackoverflow.png)

* You don't have to use `n`. It's just a variable. Replace it to represent what makes sense.
  * Example: If you're trying to figure out O notation for how long it takes to mow a square area of land, you can use:
    * `O(a)` where `a` is the area. Or `O(s^2)` where `s` is the length of a side
* 4 big rules:
  * If you have different steps, you add them up: `O(a)` and `O(b)` = `O(a+b)`
  * Drop constants: If two things operate at `O(n)`, it isn't `O(2n)`. It's just `O(n)`
  * With different inputs, you should use different variables to represent them. Give `n` a meaning. For arrays `a` and `b` use both separately
  * Drop non-dominant terms: If you have `O(n)` and `O(n^2)`, just drop the `O(n)` so you only represent as `O(n^2)`

## Examples

If you ask somebody about numbers 1-100 and tell them to guess which one you're thinking:

* `O(1)`: You tell them what the answer is first. Called `constant time`
* `O(log n)`: They guess 50, and you tell them higher or lower until they get it.
* `O(n)`: They guess in order from 1 to 2 to 3 until they get it., Callled `linear time`
* `O(n log n)`: They guess 50 and you tell them lower, but they still guess at higher and at lower
* `O(n^2)`: They guess in order, but when they guess wrong, they have to start over. 1, then 1 2, then 1 2 3
* `O(2^n)`: Same as above, but they have to repeat as they go, so 1 12 1 12 123 1 12 123 1234