# Mar 30

## BST
- Recursive
```
public boolean find(T data) { // necessary because of the root
  return find(data, root)
}

private boolean find(T data, Node n) {
  if (n == null) // if this check for null is below, could run into NullPointerException
    return false
  if (data.compareTo(n.data) == 0) 
    return true
  if (data.compareTo(n.data) < 0)
    return find(data, n.left)
  if (data.compareTo(n.data) > 0)
    return find(data, n.right)
}
```
- Visit Nodes in a *single* path
- Node can only be on one place
- Iterative
```
boolean find(T data) { 
  Node curr = root
  while (curr != null) {
    if (data.compareTo(curr.data) == 0)
      return true
    if (data.compareTo(curr.data) < 0)
      curr = curr.left
    if (data.compareTo(curr.data) > 0)
      curr = curr.right
  }
  return false
}
```
- Inorder, Preorder, Postorder
  - Inorder
    - Left child subtree, Node, Right child subtree
    - Gives you Nodes in order
  - Preorder
    - Node, Left child subtree, Right child subtree
    - Root will appear first
    - Good for viz a tree
  - Postorder
    - Left child subtree, Right child subtree, Node
    - Root last, subdivide list from left-hand side to right-hand side
  - Alternative notation is in code
- Inorder traversal
```
void inOrder(Node n)
  if (n == null) 
    return
  inOrder(n.left)
  S.o.p(n.data)
  inOrder(n.right)
```
- Postorder traversal
```
void postOrder(Node n)
  if (n == null) 
    return
  postOrder(n.left)
  postOrder(n.right)
  S.o.p(n.data)
```
- Inserting
  - Most efficient will add at leaf level
    - Downside: Can get skinny branches --> Work with Self-Balancing Binary Search Trees
