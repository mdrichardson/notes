# AVL Tree Pseudo Code

## Concept

Node class needs:

* right and left
* value
* height (for later calculating balance factor)
* balance factor (for detecting imbalance)

Tree class needs:

* root property
* methods:
  * public insert
  * private insert for recursively inserting
  * private update for calculating height and balance factor after insertion and rotation
  * private rotation methods, including for rotating based off of parent and child imbalance
  * public remove
  * private remove for recursion
  * private findMaxNode
  * private findMinNode

```
class Node {
  // Properties from above
}

class Tree {
  insert(value) {
    // set the root if we don't have one
    // otherwise, set the root to _insert(value, this.root)
  }

  _insert(value, node) {
    // handle base case of null node, which is a new Node(value)
    // recurse to appropriate last node and add new one at the bottom
    // update node
    // return _balance(node), which will give us the appropriate "root" node of the sub-tree
  }

  _update(node) {
    // get children heights
    // node height is greatest child height + 1
    // node balance is rightHeight - leftHeight
  }

  _balance(node) {
    // if left-heavy
      // if left child is left-heavy, just do one right rotation
      // otherwise, child is right-heavy, so we need a left rotation on the left child, then a right rotation on parent node
    // if right-heavy
      // if right child is right-heavy, just do one left rotation
      // otherwise, child is left-heavy, so we need a right rotation on the right child, then a left rotation on parent node
    // return the resulting node for each case
  }

  _leftRotate(node) {
    // set pointer for the right node
    // node's right node is pointer's left node
    // pointer's left node is node
    // update() the node, then the pointer. Order important because pointer will be the parent
    // return the pointer because it's the new parent
  }

  _rightRotate(node) {
    // opposite directions from above
  }

  remove(value) {
    // set root to _remove(value, this.root)
  }

  _remove(value, node) {
    // return null when node == null because that means node has no children, easy removal
    // recurse left/right until we find our node
    // when value === node.value
      // if there's no left child node, return the right (easy swap)
      // if there's no right child node, return the left (easy swap)
      // otherwise, we have two children and need to find an appropriate successor, which is either the max value in the left tree or the min value in the right tree
      //    we can choose whether to go for min or max by how our tree is currently balanced
        // if we're left heavy
          // set a pointer for the max value of the node's left tree
          // node value is equal to pointer's value, so now we have two of the same value with the duplicate in our left tree
          // set node.left to _remove(pointer value, node.left), so that we remove the duplicate from node's left tree
        // if we're right heavy
          // ... do the same, but opposite left/right min/max
    // update the node
    // return _balance(node)
  }

  _findMax(node) {
    // base case is node.right == null, in which case we return node
    // recurse down node.right and return
  }

  _findMin(node) {
    // same as _findMax, but for the left side
  }
}
```
