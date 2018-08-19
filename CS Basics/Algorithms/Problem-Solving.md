# Problem-Solving Strategies

1. Understand the problem
    * Be able to explain the problem in plain English
    * Make diagrams of the problem, if needed
    * Re-wording the problem may also be helpful
2. Come up with a SOLID plan
    * "With input X, what is each step I need to take to produce Y?"
    * Solve all of the details first
    * Can it be solved a different way?
      * Backwards or Bottom-Up
      * Divide and Conquer
      * Recursion
      * Brute force
    * Still stuck? Try the simplest input you can think of and go up from there
3. Divide the problem into smaller parts
    * The sub-problems should be simpler to solve and help you focus
    * Start solving the sub-problem you're most confident you can solve, them move onto the rest
    * Stop and make sure each sub-problem produces expected results
4. Improve the plan
    * Can any of the sub-problems be solved in a way that's more space or time-efficient?
        * What about the problem, as a whole?
        * Does it matter? If we know the input is small, we don't need to operate in linear time, do we?

## Recursion

Start with problems you can already solve through iteration

1. *(optional)* Write an iterative function that solves the problem
2. Write a "dispatcher" function that solves the problem for a "minimal" data set, like for the last item in a loop (like a base case)
    * Have the dispatcher call the iterative function for non-minimal cases
3. Merge your iterative function into your dispatcher function

Recursion works like a stack. It adds variables with the calls to the function to the stack until you hit the base case. Then it solves the base case and removes calls from the stacks, solving the problems in LIFO order.

Because of storing everything in a stack, recursion often uses more memory than iteration.