# April 11

## Proj4
- Proj4: BST
- Use built-in LinkedList
- Do not enter the lists into the tree in alphabetical order
- Use recursion NOT iterative
- Implement remove method
- .toString() for tree for easy debugging
- BSTNode
  - Data: DBAList (which is a LinkedList)
    - `String name`
    - LinkedList of Records with same name
    - Facilitate findByName
  - Left (BSTNode)
  - Right (BSTNode)

## AVL Trees
- Balancing
  - Calling balance() --> Tree which maintains itself
  - Looking at a neighborhood of the tree and seeing if they're balanced
  - Keep track of insertion and removal
  - Checking whether the tree is balanced after each removal or insertion
  - Doesn't prevent skinny branches but even with the balancing criteria, guarantees height is O(log n)
- Node unbalanced
  - Heights of two children becomes out of order by more than 1
  - Ex: If Node is 2 or -2, must balance
- Height
  - Start at either 1 or 0 but keep track of it
- Balancing
  - Adding to one side means you don't look at the other side
  - Leaf considered balanced
  - Changing 2 or 3 connections around the node which were unbalanced
  - Come from bottom up
- Balance method for LL rotation --> Mirror of RR
```
Node balance(Node A)
  Node B = A.left

  A.left = B.right // Already created B which holds A.left
  B.right = A

  height(A) // fix heights STORED in both Nodes
  height(B) // fix heights STORED in both Nodes

  return B
```
- LR rotation --> Mirror of RL (Double rotations)
```
Node balance(Node A)
  Node B = A.left
  Node C = B.right

  A.left = C.right
  B.right = C.left
  C.left = B
  C.right = A

  updateHeight(A)
  updateHeight(B)
  updateHeight(C)

  return C
```
