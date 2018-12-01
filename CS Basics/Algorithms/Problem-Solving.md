# Problem-Solving Strategies

1. Understand the problem
    * Be able to explain the problem in plain English
    * Make diagrams of the problem, if needed
    * Re-wording the problem may also be helpful
2. Come up with a SOLID plan
    * "With input X, what is each step I need to take to produce Y?"
    * Solve all of the details first
    * Can it be solved a different way?
      * Backwards
      * Divide and Conquer
      * Recursion
      * Bottom Up
      * Backtracking
      * Brute force
        * This is generally a last resort, but might lead you to an optimized solution
    * Still stuck? Try the simplest input you can think of and go up from there
3. Divide the problem into smaller parts
    * The sub-problems should be simpler to solve and help you focus
    * Start solving the sub-problem you're most confident you can solve, them move onto the rest
    * Stop and make sure each sub-problem produces expected results
4. Improve the plan
    * Can any of the sub-problems be solved in a way that's more space or time-efficient?
        * What about the problem, as a whole?
        * Does it matter? If we know the input is small, we don't need to operate in linear time, do we?

## Another Approach

From Cracking the Code Interview:

1. Listen
    * Make sure you have all of the necessary information
    * Record anything unique or that stands out
2. Example
    * Come up with an easy-ish example. Don't make it too easy. Debug it.
    * The example should be specific (real numbers/strings), sufficiently large, and not a special case
    * Draw it and make sure the interviewer agrees the example fits the problem
3. Brute Force
    * Come up with the brute-force solution first.
    * State it out loud even though you know it's simple and inefficient. Some candidates may struggle even getting this far.
4. Optimize
    * Find where it slows down and try to optimize it
    * Try a time vs. space tradeoff (hash tables?)
    * Look for unused information
    * Use a fresh example
5. Walkthrough
    * Walk through the approach in detail
    * Make sure you understand all of it before you write any code
6. Implement
    * Write beautiful code
    * Modularize it - Pretend helper functions and classes exist and fill in later, if needed
    * Use meaningful names
7. Test
    * Pay attention to hot spots like math and null nodes and unusual/non-standard code
    * Walk through the code with small test cases
    * Test some special and edge cases

## Recursion

Start with problems you can already solve through iteration

1. *(optional)* Write an iterative function that solves the problem
2. Write a "dispatcher" function that solves the problem for a "minimal" data set, like for the last item in a loop (like a base case)
    * Have the dispatcher call the iterative function for non-minimal cases
3. Merge your iterative function into your dispatcher function

Recursion works like a stack. It adds variables with the calls to the function to the stack until you hit the base case. Then it solves the base case and removes calls from the stacks, solving the problems in LIFO order.

Because of storing everything in a stack, recursion often uses more memory than iteration.

## Coding Challenge Patterns

These are solution patterns that often show up for coding challenges. Mostly for the harder Easy levels and above

1. [Iterative Tree Traversals](https://medium.com/leetcode-patterns/leetcode-pattern-0-iterative-traversals-on-trees-d373568eb0ec)
2. Breadth-First-Search and Depth-First Search: [Part 1](https://medium.com/leetcode-patterns/leetcode-pattern-1-bfs-dfs-25-of-the-problems-part-1-519450a84353) [Part 2](https://medium.com/leetcode-patterns/leetcode-pattern-2-dfs-bfs-25-of-the-problems-part-2-a5b269597f52)
3. [Sliding Windows for String](https://medium.com/leetcode-patterns/leetcode-pattern-2-sliding-windows-for-strings-e19af105316b)
4. [Backtracking](https://medium.com/leetcode-patterns/leetcode-pattern-3-backtracking-5d9e5a03dc26)