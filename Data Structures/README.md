# [Data Structure](#data-structure)
The most fundamental data structures in C++, the core ones are,

## 1. Array
 - A fixed-size collection of elements of the same type.
 - Elements are stored in contiguous memory locations.
 - Supports random access via indexing.
 - Example
 ```cpp
int arr[5] = {1, 2, 3, 4, 5};
 ```
For details click [here](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Data%20Structures/Array.md#array)
<br>
<br>


## 2. Pointer
 - Stores the memory address of another variable.
 - Enables dynamic memory allocation and efficient array handling.
 - Example
 ```cpp
int x = 10;
int* ptr = &x; // Pointer stores the address of x
 ```
For details click [here](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Data%20Structures/Pointer.md#pointer)
<br>
<br>


## 3. Structure (struct)
 - A user-defined data structure that groups variables of different types.
 - Used for logical grouping of related data.
 - Example:
 ```cpp
struct Student {
    int rollNo;
    char name[20];
    float marks;
};
 ```
 <br>


## 3. Linked List (Basic Dynamic Structure)
 - A collection of nodes, where each node stores data and a pointer to the next node.
 - Unlike arrays, it does not require contiguous memory.
 - Example of a basic singly linked list node:
```cpp
struct Node {
    int data;
    Node* next;
};
```
<br>

While **arrays** and **pointers** are the **most fundamental**, **structures and linked lists also form the core of data structures in C++**. They serve as the building blocks for more complex structures like stacks, queues, and trees.
<br>

---