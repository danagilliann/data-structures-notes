# Mar 21

## Singly LinkedLists
- `Person p;` - Reference
  - Creates room for memory address (64 bit)
  - `Person p = null` - Safer
- `p = new Person()` - Creates object, allocated on the heap
  - Assigns to memory address to reference variable
  - On heap
  - Do not know address in Java
  - `p` references Person object
- Starts with reference to first object -> Obj1 -> Obj2 --> Obj3 -> ... -> null
  - No fixed position in memory
  - No ordered fashion in memory
- Not `Person`, `Nodes`
  - `data` and `next` should be private, have getters and setters
- \*By default, if you don't initialize data fields, it is null
- Reference points to null by default
- `sn.setNext(current)` --> Sets tail of `sn` to tail of `current` (before the null)
  - Review pictures
- `current.setNext(new StringNode());`` --> This is valid
  - It does get stored (?)
- head or front
  - First reference variable, don't lose it!
- \*Never touch the head!!!
```java
class LinkedList {
  private int size;
  private Node head = null;
  public LinkedList() {
    size = 0;
  }
  // insert
  // remove
  // find
}
```
- Insert front O(1)
```
addFront
  Node tmp = new Node();
  tmp.next = head;
  head = tmp;
```
- Insert back O(n)
  - Visit every single element
  - Create a curr Node
```
Node curr = head;
/* Special case */
if (curr == null)
  head = temp;
while (curr.next != null)
  curr = curr.next;
curr.next = temp;
```
- Insert somewhere in middle O(n)
  - Visit every single element until reach desired index
```
Node curr = head;
Node temp = new Node();
if (position > size)
  return;
for (int i=0; i < position; ++i) {
  if (curr.next != null)
    curr = curr.next;
temp.next = curr.next; // points to current's next element
curr.next = temp; // current points to temp
}
```
