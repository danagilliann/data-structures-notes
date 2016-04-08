# April 4

# Generics
- Problems
  - Generics introduced late
  - Java is backwards compatible --> Java 1 code can run on Java 8
    - Allow "incorrect" syntax
- Allows programmer to be flexible with parameters
- Generics write skeleton, comparator deals with rest
- Templates vs. Generics
  - Same thing (sort of) --> Parameterize types and elements
  - Difference
    - Templates
      - (C++) 
      - Duplicates of code 
      - (sub parameters)
    - Generics
      - Use parameter to test type agreements then replaces type with Object
      - Guaranteed type agreement
- Letter of Generic doesn't matter, but there is convention
- Generics can only be holders Objects
- Autoboxing
```
Integer n1 = 1 // works
Integer n2 = new Integer(1) // works
ArrayList<int> list // error!
ArrayList<Integer> list // works
```
- Methods
```
// Tells compiler that this method is special
public static <E> void printList(E[] list) {
  for (int i = 0; i < list.length; i++)
    System.out.print(list[i] + " ");
  System.out.println();
}
```
  - Smallest element
```
<E extends Comparable<E>> E findSmallest(E[] list) { 
  E min = list[0]
  for (int i = 0; i < list.length; ++i) {
    if (min.compareTo(list[i]) > 0) { // not <, > because Generics can't handle primitives. Restricts it to Objects with compareTo
      min = list[i]
    }
  }
  return min
}
```
    - `compareTo` restricts Objects which implement Comparable
    - `<E extends Comparable<E>>` makes the method safer
      - NOT IMPLEMENTS because it's Generics (lol)
      - Bounded Generics
      - If you do not do this, compiler will complain
- "Toolbox class"
  - Like Math class
  - private Constructor
    - Can't create an instance
  - static and private --> "Toolbox" like
  - Cannot be interface because interfaces can't be static
- Arrays
  - Cannot create an array of Generic Type
  - Compiler cannot create an array without a specified type
  - DON'T DO THIS!!!
  - \*Just use an ArrayList
  - Application: Merge sort
- Wildcards --> \*NOT ON EXAM OR ANYTHING LOL :tada:
  - `?`
  - Allows compiler to use whatever type it wants
  - RARELY USED
  - `? Extends`
- \*ArrayToolbox WILL BE ON THE FINAL
- \*WILL BE ON EXAM

