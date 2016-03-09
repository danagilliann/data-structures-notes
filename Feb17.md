# Feb 17

- Selection Sort
  - Looks for the smallest element and puts it in the least place
- When sorting ask: What are we sorting by?
- Sorting Strings
  - Sorted by ascii
  - Default: Alphabetically
  - Other than default: Can use/create/`implement` a Comparable class
- Comparator
  - Generic class
  - Pretty good sort alternative to assignment (do this only if there's time)
  - Do not necessarily have to Override contains method (unless you're using contains)
```java
public void sort(ClassName list, Comparator<ClassName> comp) {
  for (int i ...) {
    ...
    for (int j ...) {
      if (comp.compare(currentMin, list[j]) > 0) { // currentMin is list[i]
        currentMin = list[j]
        currentMinIndex = j
      }
    }
  }
}
```
- Approaches to sorting MyArrayList
  1. If/else statement in one method)
  2. *Uses the key or takes parameter of comparator*
- Testing code
  - Maintain software specification
  - Black-box testing
