# Mar 23

- LinkedList
  - Reference to head
  - Reference to other nodes
  - Nodes do not know where it is in the list
  - Last --> null
  - \*Do not know position in list
  - "Egocentric"
- Remove first O(1)
  - `head = head.next`
  - Ideally return data that was in the "old" head
  - GC collects the "old" head because nothing points to it
```
if head != null
  String tmp = head.data
  head = head.next
  return tmp
return null // Depends if you allow "null" to be in the linkedlist. 
// Alternative: throw exception
```
  - Require the user to be least responsible
  - Flexible programs == :100:
- Remove last O(n)
```
String tmp = null
if (head == null)
  return null
if (head.next == null) {
  tmp = head
  head = null
  return tmp
}
Node curr = head
while(curr.next.next != null) {
  curr = curr.next
}
curr.next = null
tmp = curr.next
return tmp
```
- Removing nth Node O(n)
```
String temp = null
if (size < n + 1) 
  return null
Node curr = head
for (int i = 0; i < n-1; ++i) { 
  curr = curr.next
}
temp = curr.next.data
curr = curr.next.next
size-- // Important!!
return temp
```
- Recursive data structures
  - Do not use recursion all the time
- Size method iteratively
```
// compute and return # of nodes in list
int size() {
  int count = 0;
  Node cur = head;
  // no need for special case for head -> null
  while (curr != null) { // curr.next != null will give off by 1 error
    curr = curr.next
    count++
  }
  return count
}
```
- Size recursively
```
int size() {
  return size(head) // head is data field
}

int size(Node head) { // head is local to method
  if (head == null) {
    return 0
  }
  return size(head.next) + 1 // head.next DOES NOT reassign head
}
```
  - If you wanted to access head in `size(Node head)`, you will have to do `this.head`
- LinkedLists are great for stacks
  - The head is the first element in the linkedlist
  - O(1) for adding/removal
