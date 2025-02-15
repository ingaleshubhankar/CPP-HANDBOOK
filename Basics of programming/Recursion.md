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

```
void fun()
{
    // Code
    fun();
}
```


### Head Recursion

```
void gun()
{
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

---

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
