# Feb 3

- Questions
- Recursion
  - Two kinds of recursion
    1. Direct (method calls itself)
    2. \*Extends to self
    ```java
    int methodA(int x) { 
      methodB(x) // could be recursive
      return x
    }
    ```
  - *Important things*
    - Base case
    - Prevent StackOverflow or Underflow in your recursive case --> Must bring it closer to base case
  - Factorial example (recursion)
  ```
  int factorial(int n)
    if (n == 0)
      return 1
    else
      return factorial(n-1) * n
  ```
  - Recursion comes with a price tag
  - \*Integers can wrap around
  - Fibonacci example (recursion)
  ```
  /* 
  * count the computer science way
  * two base cases because you have two recursive calls
  * (ie you're adding two numbers)
  */
  int fib(int n)
    if (n == 0)
      return 0
    else if (n == 1)
      return 1
    else
      return fib(n-1) + fib(n-2) /* this is why we have two recursive calls */
  ```
  - \*NEVER USE RECURSION FOR FIBONACCI (inefficient)
    - Recursive calls end up repeating (factor out f(5))
    - You can cache/memoize but that takes up space (boo)
  - String reversal --> Uses \*`.substring` 
    - Base case
      1. String w/ one char
      2. String w/ 0 char
      ```
      String reverse(String s)
        if (s.length == 1)
          return s
        else
          return reverse(s.substring(1, s.length)) + s.charAt(0)
      ```
