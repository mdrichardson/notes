# Optimize and Solve Techniques

These come from Cracking the Code Interview

## BUD

Three common things that an algorithm can "waste" time doing:

* Bottlenecks
* Unnecessary Work
* Duplicated Work

### Bottlenecks

Slow down the overall runtime. Time complexity is usually the big one here. Try to reduce the time complexity.

Is there work that's done repeatedly?

### Unnecessary Work

Just like it sounds. A common one is finding the solution, but having the algorithm still run. Maybe it saves data to a temporary variable that isn't of much use.

### Duplicated Work

Cacheing data or recursion can often solve this.

## DIY

We often make writing and algorithm much harder than we would actually solve it ourselves. For example, if you needed to find Peter Smith's file in a stack of alphebetized folders, we'd do a binary search without even thinking about the algorithm.

So, when trying to solve a problem. Actually solve the problem without code, first.

## Simplify and Generalize

If you're stuck, try making part of it easier. Change the data type or pretend one of the steps is already solved.

Maybe instead of looking at a problem involving whole words, make it involve just single characters first.

## Base Case and Build

Solve the problem for a base case first, then go from there.

## Data Structure Brainstorm

Just run through a list of data structures and try to apply each one.