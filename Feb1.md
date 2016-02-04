# Feb 1

- Dynamic Binding
  - Runs the object method not reference
  - Actual type
- `instanceof`
  - Test particular class type
- \*switch/case statements have fall-through behavior --> Take advantage of fall-through behavior (recall: race02)
- `printf`
  - \*Automatically calls a `.toString()` method
  - Polymorphically handle objects of different types
  - \*If calling a method on declared type but only exists on actual type then you'll get a compiler error (`.move` method)
- Abstract Class
  - \*Skeleton for a subclass
  - Present abstract methods (usually)
  - \*Cannot instantiate it (`new` keyword)
  - \*Done to access the methods of the subclass
  - \*Cannot instantiate Math class (`private` Constructor)
- Interfaces
  - \*Do not exist in hierarchy
  - `comparable` interface
    - \*`.compareTo` method allows you to compare based on a certain object or values
    - \*Work with primitive types
    - \*Return values: negative, 0, positive
```java
obj1.compareTo(obj2)
  negative // obj1 < obj2
  0 // obj1 == obj2
  positive // obj1 > obj2
```
    - Strings return a negative/positive number not necessarily -1/1
    - Compliments `Arrays.sort()` or `Collections.sort()`
