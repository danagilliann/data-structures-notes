# Feb 8

## Homework
```java
class MyArrayList extends ArrayList<Record> {
  private ArrayList<Recods> list; // DO NOT DO THIS because you're extending ArrayList class
  // You can use the getters and setters of the ArrayList class instead
  public void add(Record r); // DO NOT DO THIS because ArrayList already has .add
}
```
- Cannot use built-in sort method (BUT DO NOT USE BUBBLE SORT)
- Will be using the same code for the hw *SO WRITE IT WELL*
- Go to OpenNYC to generate SMALLER datasets
- DO NOT USE THE LARGEST FILES BECAUSE EVERYTHING WILL SUCK

## Recursion
- \*First method called: Main method
- View notes for crude viz
- \*If used inappropriately, StackOverflow happens --> Your program has no more space for the memory it allocated
- \*The parameter we're modifying lives on a *heap* memory location
- Uses a *stack*
  - Very organized
- Heap
  - If the memory not used, garbage collector does away with it
- (View code on p4) If change base case then can't call empty string
- Towers of Hanoi --> View notes
- Backtracking --> View notes
  - Challenge: Only print stuff which end with a "1"
    - Sol1: Alter the base case
    - Sol2: Prevent the "0" side from happening (View notes)
## Immutability
```
String s = "Hello"
s = s + "world" // Creates a new object and extra garbage. aka more work
```
- `StringBuilder` does not make it necessarily better (sacrifices space time for runtime)
```
StringBuilder sb = new StringBuilder("hello")
sb.append("world") // Uses an internal array of character much larger than necessary
```
- `StringBuffer` vs `StringBuilder`
  - `StringBuffer` is thread-safe (but requires more computational steps)
