# April 4

- Circular Linked List Prob
```
while (p2 != null && p1 != null) {
  p1 = p2.next
  p2 = p2.next
  if (p2 != null)
    return false
  p2 = p2.next
  if (p1 == p2)
    return true
}
return false
```
