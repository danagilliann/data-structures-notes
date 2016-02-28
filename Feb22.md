# Feb 22

- Big O
  - Measures time-complexity
  - \*Approximately N and ignores constants
- Searching
  - \*Linear search:
    - Unsorted list and checks for every index until it finds it or reaches the end
    - O(n)
    - \*Average: n/2
    - Recursively
```java
public int find(int[] a, int key) {
  find(a, key, 0);
}

private int find(int[] a, int key, int pos) {
  if (pos >= a.length()) {
    return -1;
  } else if (a[pos] == key) {
    return pos;
  } else {
    return find(a, key, pos + 1);
  }
}
```
  - Time complexity
    - Makes it slower if you have a huge amount of data and you'll have to generate many stackframes
    - \*Inefficient
  - \*Binary search:
    - Sorted list and start at the middle to determine whether to check left or right
    - O(log n), but the *default base is 2* --> Number of elements and number of times you visit an element
    - \*If you're going to search repetitively, sort and binary search
  - Searching makes a difference depending on the n
- Sorting
  - Selection/Insertion O(N^2)
    - Linear search's n > (selection/insertion + binary sort's) n
  - Merge sort/Quick sort O(N log N)
