# April 6

# Binary Search Trees
- Adding new Node to tree becomes a leaf
- If construct a bst and listing nodes in order, becomes linkedlist
- Creating bushy trees
  - *Sort*
  - Pick middle and add as first thing
  - Find middle of two sides repeat
- Balancing unbalanced tree
  - Get all Nodes out of the tree inorder --> *inorder traversal* --> Array
  - Creating bushy trees
  - If the number of nodes *is not* power of 2, might end up unbalanced
- Binary trees vs. ArrayList
  - Adding, removing, and finding can be MUCH faster
  - If you're just searching, use an ArrayList because you could end up with a linkedlist
- Removing
  - Pick inorder predecessor or inorder successor
  - Replace removed element with pre or succ
  - Bring pre or succ's nodes to pre or succ's old position
- Remove: Nice O(log n)
- Add: Nice O(log n)
- Remove: Ugly O(n)
- Add: Ugly O(n)
- Use the visualizer to check for dnhis
- Adding
  - Look at joannaNotes
- Self-balancing BST
  - AVL
  - RedBlack
