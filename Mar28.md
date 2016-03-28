# Mar 28

## Double Linked List
- Has reference to next AND prev Node
- Optimizations!!! :smile:
- Starts from front/back depending on Node index --> Doesn't change O(n)

## Circularly Linked List
- Job interviews lol
- Last Node pointing to Null points to Head
- Determining LinkedList or Circularly Linked List
```
Node curr = head.next
while (curr != null) && (!curr != head) {
  curr = curr.next
}
```

## Deque
- Double ended queue
- Hybrid between a queue and stack
- Add and remove from either end

## Tree
- Root is only reference
- Leaves pinakabottom --> points to null
- Each node does not know how to get back to parent
- Ascendants --> Come above Node (including Root)
- Descendants --> Below Node
- \**There's only path to get a Node*

## Binary Trees
- Every Node can only have AT MOST 2 children
- No lowerbound, only upperbound
- Distinction of left child and right child
- 10 nodes, deepest: 10 levels
- \**TERMS WILL SHOW UP IN THE FINALS*

## Binary Search Tree
- \* *Strings in BST* will be in exam
- Computing size
```
int size() {
  return size(root)
}
int size(Node n) {
  if (n == null) {
    return 0
  }
  return 1 + size(n.left) + size(n.right)
}
```
