# [Reference Variable](#reference-variable)
A reference variable in C++ is an alias (another name) for an existing variable. It allows us to refer to the same memory location with a different name. References are primarily used for function arguments and return values to avoid unnecessary copying of data.


## Syntax:
```cpp
datatype &reference_name = original_variable;
```

## Example:
```cpp
#include <iostream>

int main() {
    int x = 10;
    int &ref = x;  // 'ref' is a reference to 'x'

    std::cout << "x = " << x << std::endl;   // Output: 10
    std::cout << "ref = " << ref << std::endl; // Output: 10

    ref = 20;  // Changing 'ref' also changes 'x'

    std::cout << "x = " << x << std::endl;   // Output: 20
    std::cout << "ref = " << ref << std::endl; // Output: 20

    return 0;
}
```

Here, ref is just another name for x. Any modification to ref affects x as well.


## Key Properties of Reference Variables

### 1. Must be initialized

A reference must be assigned a variable at the time of declaration.
```cpp
int &ref; // ❌ Error: A reference must be initialized
```

### 2.Cannot be changed to refer to another variable
Once a reference is assigned, it cannot be made to reference another variable.
```cpp
int a = 5, b = 10;
int &ref = a;
ref = b;  // This does NOT change 'ref' to refer to 'b'. Instead, it changes 'a' to 10.
```

### 3. No separate memory allocation
A reference shares the same memory as the original variable.