# Mar28 (R)

- Prob 5 very important
- Prob 5
```java
int countCircular() {
  if (head == null) {
    return 0;
  }
  return 1 + countCircular(head.next);
}

int countCircular(Node n) {
  if (n == head) {
    return 0;
  } else {
    return 1 + countCircular(n.next);
  }
}
```
- Prob 6
```
// 6a
void addFront(Node n) {
  if (head == null) {
    head = n
    tail = n
  } else {
    n.next = head
    head.previous = n
    head = n
    // 6b
    // n.previous = tail
    // tail.next = n
    // tail = n
  }
}
// 6c
Object removeFront() {
  if (head == null) {
    return null
  } else if (head == tail) {
    Object temp = head.value
    head = null
    tail = null
    return temp
  } else {
    Object temp = head.value
    head = head.next
    head.previous = null
    return temp
    // 6d
    // Object temp = tail.value
    // tail = tail.previous
    // tail.next = null
    // return temp
  }
}
```
- Prob 7
```
// recursive
int size() {
  Node temp = head
  int c = 0
  while (temp != null) {
    temp = temp.next;
    c++;
  }
  return c;
}
```
- Prob 8
```
// recursive
int count() {
  Node temp = head
  int c = 0
  while (temp != null) {
    c += temp.data
    temp = temp.next
  }
  return c;
}
// iterative
int sum() {
  return size(head)
}
int sum(Node n) {
  if (n == null) return 0
  else return n.data + sum(n.next)
}
```
- Extra Challenge 2
  - Use a stack and midway start popping and seeing if it matches
