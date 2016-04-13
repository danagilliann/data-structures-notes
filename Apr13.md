# April 13

## Tree
- Tree
  - Special node called root
  - Restriction: Only one path from root to every other node
- Binary Tree
  - A tree with nodes that have at most, 2 children
- BST
  - A binary tree with an order property value in left child < value in node < value on right child
- AVL
  - A BST where every node has a balanced factor of -2 < balance factor < 2
  - Balance factor being the difference in height of the two children
- Heap
  - DIFFERENT FROM THE HEAP IN MEMORY
  - A binary tree with shape and order properties
  - Shape property: Tree complete
  - Complete: Shape is filled and last level of leaves will be filled from left to right
  - Order property:
    - Max heap: For any node, children are smaller (or equal)
    - Min heap: For any node, children are bigger (or equal)
  - Don't quite behave like trees
- Given a Node in a binary tree, figure out its height
  - Non-AVL Trees
    - O(n) --> Visit each node to compute height
    - DO NOT USE THIS FOR AVL TREES. TOO DARN SLOW.
    ```
    // E data
    // Node right
    // Node left
    int height (Node n) {
      if (n == null) {
        return -1;
      }
      return 1 + max(height(n.right), height(n.left));
    }
    ```
  - AVL Trees
```
// Node AVL
// E data
// Node left
// Node right
// int h
int height ()
  if (n == null)
    return -1
  if (n.right == null)
    return 
  if (n.left == null)
    return
  return max(n.right.h, n.left.h) + 1
```
- Red-Blacks used more often because constant is much lower

## Priority Queue
- Vanilla Queue: Determined by time
- Array
  - Remove: O(1)
  - Insert: O(n)
    - Find location and shift
- LinkedList
  - Remove: O(1)
  - Insert: O(n)
    - Find location, no shift
- BST
  - Sorted by priority
  - Insert: O(log n) but actually O(n)
    - Will suffer because it will become unbalanced
  - Remove: O(n)
    - Skewed to right
- AVL
  - Insert: O(log n)
  - Remove: O(log n)
- Heaps are used --> Much smaller constants
  - Insert: O(log n)
    - Gen idea: Swap until you get to the root --> Ensures you don't have to visit every element
  - Remove: O(log n)
