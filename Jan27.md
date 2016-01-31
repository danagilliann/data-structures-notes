# Jan 27

## Questions:


## Lecture:
- Behaviors of classes/objects should make sense
  - Ex: Recall student/roster analogy
- Reference vars vs. Objects
```java
Circle c1 = new Circle(5);
// ^^^       ^^^
// Reference Object
Circle c2 = new Circle(17);
```
- In this example, Reference points to Objects
```java
c1 = c2
```
- In this example, c1 points to c2's object
- `Circle(5)` gets put in the garbage collector --> Don't need to cleanup memory
- \*Cannot capture object once you remove reference
```java
c1.setRadius(102);
s.o.p(c1.getRadius()); // 102
s.o.p(c2.getRadius()); // 102
```
- All changes in c1's object will be in c2 because they point to the same thing
- `has-a` relation
  - Object can contain another object as its data field
  - has-a thing
  - Ex: Student object has name, String object
- `is-a` relation
  - Deals with inheritance
  - Automatically inherits
  - Ex: Students, undergrad and grad
- is-a thing vs. has-a thing
- If assignments say "do this", then do it.
```java
try{Thread.sleep(500)}
catch(InterruptedException e){}
```
- Waits a second
- `clearScreen()` puts blanks on everything
- Inheritance
  - Defining new classes from existing ones
  - `is-a` --> is one thing really another thing?
  - The following do not get inherited
    - Constructors do not get inherited unless you do `super`
    - `Private` variables do not get inherited
    - `Static` methods do not get inherited
- `super()`
  - \*Do not need to use super for inherited methods
  - \*Only do super for methods that you're overriding from the super class
  - \*`.toString` is from the Object class so it's inherited
- Constructors
  - Look at 4.1.3 for notes
  - \*Call to super constructor always has to happen
  - \*At line 3 for C2, the default Constructor will be called UNLESS you specify constructor
  - \*Call to super must be called first in Constructor chaining
  - Compiler makes a default Constructor unless you make a Constructor
  - Once you make a Constructor you will NO LONGER have a Constructor
```java
public class C1 { 
  public C1 (int i) {}
}

public class C2 {
  public C2 () {} // compiler error bc C1 asks for an int
}
```
- Overriding
  - Same name, same params
- Overloading
  - Same name, different params
- Dynamic binding and polymorphism
```java
// Refer to tree of Person
Student s = new Student();
Person p = new Student();
Student s = new Person(); // invalid
Person p = new Prof(); 
p.toString(); // Print's Prof's .toString() not person
```
- \*`p.toString()` points to Prof but encapsulated by Person
