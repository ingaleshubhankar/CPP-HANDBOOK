# [Basics of programming](#basics-of-programming)

## [Control Flow](#control-flow)
**Control flow** in C++ refers to how the computer follows the instructions in a program, step by step. To make it easier to understand, we can look at it through three main parts: **Sequence**, **Iteration**, and **Selection**.<br>

Below are the basic categories of [control flow](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Basics%20of%20programming/ControlFlow.md#control-flow),
1. [Sequence](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Basics%20of%20programming/ControlFlow.md#1-sequence)
2. [Iteration](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Basics%20of%20programming/ControlFlow.md#2-iteration)
3. [Selection](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Basics%20of%20programming/ControlFlow.md#3-selection)
<br>



## [Time and Space Complexity](#time-and-space-complexity)
Time complexity and space complexity are two key concepts in computer science and programming that help evaluate the efficiency of algorithms. They describe how the performance of an algorithm changes with the size of the input.<br>
<br>

### [Time Complexity](#time-complexity)
Time complexity is a measure of the amount of time an algorithm takes to complete as a function of the input size `n`. It is used to analyze how the runtime of an algorithm scales with larger inputs, helping us evaluate its efficiency.<br>

Time complexity of our application is **total time required to execute our application**. 

> Key Points about **Time Complexity**,
1. **Independent of Machine**: Time complexity focuses on the algorithm's structure and logic, not the hardware it runs on.
2. **Growth Rate**: It describes the rate at which the algorithm's runtime increases with respect to the input size.
3. **Big-O Notation**: The most common way to express time complexity, e.g., O(1),O(n), O(n^2), etc.

    - O(1): Constant time — the runtime is independent of the input size.
    - O(n): Linear time — the runtime grows linearly with input size.
    - O(log n): Logarithmic time — the runtime grows logarithmically with input size.
    - O(n^2): Quadratic time — the runtime grows quadratically with input size.

Generally time complexity of our program is depend on the iterations which are used (loops).<br>

If program contains single iteration which executes `n` times. Then its time complexity is `n`.<br>

If our application contains two iterations & each iteration iterates `n` times then time complexity is `2n`.<br>

If our program contains iteration and it contains another in it(nested loop) & every iteration iterates `n` times then time complexity is `n^2`.<br>

According to the concept of time complexity, above approach required. `2n` as time complexity.<br>

if our program successfully working then we can reduce time complexity by removing any of iteration.
<br>
<br>

### [Space Complexity](#space-complexity)
Space complexity is the total amount of memory an algorithm uses as a function of the input size  n. It accounts for both the auxiliary space (temporary space used during execution) and the input space.<br>

> Key Points about Space Complexity
 - Memory Usage: Measures memory required during runtime, including stack space, heap space, and static memory.
 - Components:
    - Fixed part: Space needed for constants, program instructions, and variables independent of the input size.
    - Variable part: Space required for dynamic allocations, recursion stack, etc.
 - Big-O Notation: Space complexity is also expressed using Big-O, e.g.,O(1),O(n). 

