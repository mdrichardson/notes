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
    // our height is greatest child height + 1
    // our balance is rightHeight - leftHeight
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
    // node's right node is right node's left node
    // pointer's left node is node
    // update() the node, then the pointer. Order important because pointer will be the parent
    // return the pointer because it's the new parent
  }

  _rightRotate(node) {
    // opposite directions from above
  }
}
```
