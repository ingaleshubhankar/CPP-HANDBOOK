# Memory Management Operators
In C++, `new` and `delete` are used for **dynamic memory allocation** and **deallocation** on the **heap**. This is useful when you don’t know the size of data at compile time. C++ provides these two key memory management operators to dynamically allocate and deallocate memory at runtime.
<br>
<br>


## [1.new Operator](#1new-operator)
The `new` operator dynamically allocates memory on the **heap**. Returns a pointer to the allocated memory.

### Syntax:
```cpp
int* ptr = new int;  // Allocates memory for an integer
```

### For Arrays:
```cpp
int* arr = new int[5];  // Allocates an array of 5 integers
```
<br>



## [2.delete Operator](#2delete-operator)
Frees the dynamically allocated memory to prevent memory leaks.
The `delete` operator is used to free dynamically allocated memory. If you don’t use delete, it can lead to **memory leaks**.

### Syntax:
```cpp
delete pointer;
```

### Deallocates memory allocated for an array:
```cpp
delete[] pointer;
```
<br>



### Example:
```cpp
#include <iostream>
using namespace std;

int main() {
    int* ptr = new int(50);  // Allocate memory
    cout << "Value: " << *ptr << endl;  

    delete ptr;  // Free memory

    return 0;
}
```


### Example of deleting the Array:
```cpp
int* arr = new int[5];  // Allocate memory for an array
delete[] arr;  // Free the allocated memory
```

