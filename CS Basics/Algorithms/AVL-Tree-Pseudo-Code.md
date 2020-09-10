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
    // recurse to appropriate last node and add new one at the bottom (node.left = _insert(value, node.left), etc
    // update node
    // return _balance(node), which will give us the appropriate "root" node of the sub-tree
  }

  _update(node) {
    // get children heights - be sure to account for null children w/ ternary
    // node height is greatest child height + 1
    // node balance is rightHeight - leftHeight
  }

  _balance(node) {
    // if left-heavy (balanceFactor < -1)
      // if left child is left-heavy (balanceFactor <= 0), just do one right rotation
      // otherwise, child is right-heavy, so we need a left rotation on the left child (node.left = leftRotate(node.left)), then a right rotation on parent node
    // if right-heavy (balanceFactor > 1)
      // if right child is right-heavy (balanceFactor >= 0), just do one left rotation
      // otherwise, child is left-heavy, so we need a right rotation on the right child (node.right = leftRotate(node.right)), then a left rotation on parent node
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


## Code

```js
class Node {
    constructor(value, left, right) {
        this.value = value;
        this.left = left;
        this.right = right;
        this.balanceFactor = 0;
        this.height = 0;
    }
}

class AVLTree {
    constructor(value) {
        this.root = value != null ? new Node(value) : null;
    }

    insert(value) {
        if (!this.root) {
            this.root = new Node(value);
        } else {
            this.root = this._insert(value, this.root);
        }
    }

    _insert(value, node) {
        if (!node) return new Node(value);

        if (value < node.value) {
            node.left = this._insert(value, node.left);
        } else {
            node.right = this._insert(value, node.right);
        }

        this._update(node);
        return this._balance(node);
    }

    _update(node) {
        const leftHeight = node.left ? node.left.height : -1;
        const rightHeight = node.right ? node.right.height : -1;

        node.height = Math.max(leftHeight, rightHeight) + 1;
        node.balanceFactor = rightHeight - leftHeight;
    }

    _balance(node) {
        if (node.balanceFactor < -1) {
            if (node.left.balanceFactor <= 0) {
                return this._rotateRight(node);
            } else {
                node.left = this.rotateLeft(node.left);
                return this._rotateRight(node);
            }
        } else if (node.balanceFactor > 1) {
            if (node.right.balanceFactor >= 0) {
                return this._rotateLeft(node);
            } else {
                node.right = this.rotateRight(node.right);
                return this._rotateLeft(node);
            }
        }

        return node;
    }

    _rotateRight(node) {
        const newParent = node.left;
        node.left = newParent.right;
        newParent.right = node;

        this._update(node);
        this._update(newParent);

        return newParent;
    }

    _rotateLeft(node) {
        const newParent = node.right;
        node.right = newParent.left;
        newParent.left = node;

        this._update(node);
        this._update(newParent);

        return newParent;
    }

    remove(value) {
        this.root = this._remove(value, this.root);
    }

    _remove(value, node) {
        if (!node) return null;

        if (value < node.value) {
            node.left = this._remove(value, node.left);
        } else if (value > node.value) {
            node.right = this._remove(value, node.right);
        } else {
            if (!node.left) return node.right;
            if (!node.right) return node.left;

            if (node.balanceFactor < 0) {
                const pointer = this._findMax(node.left);
                node.value = pointer.value;
                node.left = this.remove(pointer.value, node.left);
            } else {
                const pointer = this._findMin(node.right);
                node.value = pointer.value;
                node.left = this.remove(pointer.value, node.right);
            }
        }

        this._update(node);
        return this._balance(node);
    }

    _findMax(node) {
        while(node.right) {
            node = node.right;
        }

        return node;
    }

    _findMin(node) {
        while(node.left) {
            node = node.left;
        }

        return node;
    }
}
```
