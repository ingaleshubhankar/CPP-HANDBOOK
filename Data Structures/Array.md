# Array
An array in C++ is a collection of multiple values of the same data type stored in a single variable. It helps in organizing data efficiently, making it easier to access and manipulate.

## Why Use Arrays?
Instead of declaring multiple individual variables (`int num1, num2, num3;`), you can store multiple values in a single variable using an array.
Arrays allow fast access to elements using an index.

## How to Declare an Array?
An array is declared using this format:

### Syntax:
```cpp
data_type array_name[size];
```

For example, to store 5 integers, declare an integer array like this:
```cpp
int numbers[5];  // Array of 5 integers
```

Here:
- `int` → Data type (integer values)
- `numbers` → Name of the array
- `[5]` → Size of the array (can hold 5 elements)

## Initializing an Array
You can assign values in two ways:

### 1. Assigning values one by one:
```cpp
numbers[0] = 10;
numbers[1] = 20;
numbers[2] = 30;
numbers[3] = 40;
numbers[4] = 50;
```
(Indexes start from `0` and go up to `size - 1`)

### 2. Assigning values during declaration:
```cpp
int numbers[5] = {10, 20, 30, 40, 50};
```
Or, if you omit the size, C++ calculates it automatically:
```cpp
int numbers[] = {10, 20, 30, 40, 50};
```

## Accessing Elements of an Array
You can access elements using their index number.
```cpp
cout << numbers[0];  // Outputs 10
cout << numbers[3];  // Outputs 40
```

## Looping Through an Array
You can use a `for` loop to process all elements.

```cpp
#include <iostream>
using namespace std;

int main() {
    int numbers[5] = {10, 20, 30, 40, 50};

    for(int i = 0; i < 5; i++) {
        cout << "Element at index " << i << " = " << numbers[i] << endl;
    }
    return 0;
}
```

### Output:
```
Element at index 0 = 10
Element at index 1 = 20
Element at index 2 = 30
Element at index 3 = 40
Element at index 4 = 50
```

## Important Key Points to Remember
- **Indexing starts from `0`** (First element → `arr[0]`).
- **Arrays store values of the same type**.
- **Size of the array must be known before using it** (C++ does not support dynamic arrays like Python lists).
- **Accessing an invalid index (out of bounds) can cause errors**.

