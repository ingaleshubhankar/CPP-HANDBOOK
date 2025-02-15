# Recursion ?
Recursion is powerful programming **technique that can be used to solve problem, that can be expressed in terms of similer problem of smaller size**.

Recursion is concept which can be used in any programming language which internally users user stack as data structure. We can easily convert the concept of iteration into recursion. Recursion is considered as calling the function from same function itself.

Recursion classification happen in three types Linear Recursion, Binary Recursion & N-ary Recursion.
<br>


There are **Two Categories** of recursion:
 1. Direct recursion
 2. Indirect recursion
<br>


There are **Two Types** of recursion:
1. Head Recursion
2. Tail Recursion
<br>


## Examples:-

### Tail Recursion

```cpp
void fun() {
    // Code
    fun();
}
```


### Head Recursion

```cpp
void gun() {
    gun()
    //Code
}
```
<br>
<br>


## 🌀 Recursive Thinking
Every recursive solution consists of **two essential components**:
1. **Base Case (Termination Condition)** – The condition where recursion stops.
2. **Recursive Case (Infinite Condition)** – The case where the function calls itself to break the problem into smaller subproblems.
<br>


### 🔹 **1. Base Case – The Termination Condition**
The **base case** is the stopping condition of recursion. Without it, recursion would **run indefinitely**, causing a **stack overflow error**.

#### ✅ **Why is a Base Case Important?**
- Ensures the function **does not run forever**.
- Defines the simplest case where the function **knows what to return**.
- Prevents excessive memory usage.

#### 📌 **Example: Factorial Base Case**
```cpp
int factorial(int n) {
    if (n == 0) return 1;  // Base case: factorial(0) = 1
    return n * factorial(n - 1); // Recursive case
}
```

 - **Base case:** if (n == 0) return 1; ensures recursion stops.
 - Without a base case, recursion would go infinitely, causing a crash.
<br>
<br>



### 🔹 **2. Recursive Case – The Infinite Condition**
The **recursive case calls** the function itself to **reduce the problem into smaller instances**.

#### ✅ **Why is the Recursive Case Needed?**
 - It breaks the problem into **smaller subproblems.**
 - Works toward the **base case** in each step.
 - Helps in **divide-and-conquer** problem-solving.

#### 📌 **Example: Factorial Base Case**
```cpp
int fibonacci(int n) {
    if (n <= 1) return n; // Base case: fib(0) = 0, fib(1) = 1
    return fibonacci(n - 1) + fibonacci(n - 2); // Recursive case
}
```

 - **Base case:** Stops recursion when `n <= 1`.
 - **Recursive case:** Calls `fibonacci(n-1)` and `fibonacci(n-2)`, reducing the problem size.



## ⚠️ What Happens Without a Proper Base Case?
If the function does not move toward the base case, it leads to infinite recursion.

### ❌ Example: Infinite Recursion
```cpp
void infiniteRecursion(int n) {
    cout << "n = " << n << endl;
    infiniteRecursion(n - 1);  // No base case! This runs forever
}
```

This function **never stops** because there is no termination condition.
It results in stack overflow.
<br>


### 📝 Example: Sum of Digits Using Recursion
Let’s write a recursive function to calculate the sum of digits of a number.
 - Base Case: If the number has one digit, return it.
 - Recursive Case: Extract the last digit and sum it with the sum of the remaining digits.

#### 📌 C++ Implementation
```cpp
#include <iostream>
using namespace std;

int sumOfDigits(int n) {
    if (n < 10) return n; // Base case: A single-digit number
    return (n % 10) + sumOfDigits(n / 10); // Recursive case
}

int main() {
    cout << sumOfDigits(1234); // Output: 10 (1+2+3+4)
    return 0;
}
```

 - **Base case:** Returns n when it becomes a single-digit number.
 - **Recursive case:** Adds n % 10 (last digit) to the sum of n / 10 (remaining digits).
The function keeps calling itself until n reaches a single-digit.



## ✅ Conclusion
 - Every recursive function must have a base case (stopping condition).
 - The recursive case must move toward the base case to prevent infinite recursion.
 - Without a base case, recursion will run forever and cause a stack overflow error.
 - Recursion is powerful and is commonly used in tree traversal, dynamic programming, and divide-and-conquer algorithms!
<br>


## 📌 Recursion Structure Summary

| **Term**              | **Definition**                                    | **Example**                          |
|----------------------|------------------------------------------------|----------------------------------|
| **Base Case**        | Condition where recursion stops                 | `if (n == 0) return 1;`         |
| **Recursive Case**   | Function calls itself to break the problem down | `return n * factorial(n - 1);`  |
| **Infinite Recursion** | When the function doesn't reach a base case   | `f(n) { f(n-1); }` (without base case) |

