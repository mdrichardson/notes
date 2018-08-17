# Data Trees

* Hierarchical and non-linear
* Uses `parent`/`child`/`sibling`, etc
* Examples:
  * Family tree
  * Company org chart
  * HTML DOM
* `Nodes` are connected by `edges`. Each node contains a `value` or `data`
  * First node is called a `root`
  * `Leaves` are the last nodes (nodes without children)
* Tree height is length of the longest path to a leaf
* Node depth is the length of the path back to the root

## Binary Trees

* More of a family of data structures, than data structures themselves
* If balanced changes search from O(n) to O(log n)
* Each node has at most two children, referred to as `left` and `right` child
* Example:

```
        1
    2       5
  3   4   6   7
```

### Traversal

#### Depth-First Search (DFS)

* Starts at root and goes as deep as possible before backtracking
* Types:
  * Pre-order: Root, left, right. Result: 1-2-3-4-5-6-7
  * In-order: Left, root, right. Result: 3-2-4-1-6-5-7
  * Post-order: Left, right, root. Result: 3-4-2-6-7-5-1
* You usually want to search with an In-Order traversal because with a binary tree, the nodes will come out roughly in order.
  * If this is the binary tree:

```
        6
    3       9
  1   4   7   10
```

* ...it would come out 1, 3, 4, 6, 7, 9, 10

#### Breadth-First Search (BFS)

* Starts at root and gets neighbor nodes first, before moving down a level
* Result: 1-2-5-3-4-6-7

### Binary Search Tree

* Value of node must be larger than the values of all left children, but smaller than values of all right child.

```python
class BinarySearchTree:
    def __init__(self, value):
        self.value = value
        self.left_child = None
        self.right_child = None

    def insert_node(self, value):
        if value <= self.value and self.left_child:
            self.left_child.insert_node(value)
        elif value <= self.value:
            self.left_child = BinarySearchTree(value)
        elif value > self.value and self.right_child:
            self.right_child.insert_node(value)
        else:
            self.right_child = BinarySearchTree(value)

    def find_node(self, value):
        if value < self.value and self.left_child:
            return self.left_child.find_node(value)
        if value > self.value and self.right_child:
            return self.right_child.find_node(value)

        return value == self.value
```

## Red-Black Tree

* Self-balancing, binary search tree with an extra bit representing color (red or black) of the node

![Red-Black Tree](https://upload.wikimedia.org/wikipedia/commons/thumb/6/66/Red-black_tree_example.svg/750px-Red-black_tree_example.svg.png)

Rules:

* Each node is either red or black.
* The root is black. This rule is sometimes omitted. Since the root can always be changed from red to black, but not necessarily vice versa, this rule has little effect on analysis.
* All leaves (NIL) are black.
* If a node is red, then both its children are black.
* Every path from a given node to any of its descendant NIL nodes contains the same number of black nodes.

* Because of the rules, the tree is forced to be height-balanced, therefore the path from the root to the farthest leaf is no more than twice as long as the path from the root to the nearest leaf.
  * This mitigates the worst-possible big O scenario

## Representing a Binary Tree

![Binary Tree](http://btechsmartclass.com/DS/images/Binary%20Tree.png)

### As Array:

![Binary Tree as Array](http://btechsmartclass.com/DS/images/BT%20Array%20Representation.png)

### As Double-Linked List

![Binary Tree as Double-Linked List](http://btechsmartclass.com/DS/images/BT%20LR%20Node.png)
