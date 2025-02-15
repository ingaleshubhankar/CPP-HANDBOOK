# Input & Output in C++
C++ does not have built-in statements for input and output (I/O). Instead, it provides an extensive **Standard Library** that includes functionalities for I/O operations. The **iostream** library is used to handle input and output in C++.

---

## What is iostream?

`iostream` stands for **Input Output Stream** and is made up of two main components:
- **istream** → Handles input operations (e.g., taking user input)
- **ostream** → Handles output operations (e.g., displaying output)

---

## What is a Stream?

A **stream** is a sequence of characters that flow from or to an I/O device.

---

## I/O Objects in iostream

The `iostream` library provides four key objects for I/O operations:

1. **cin** (see-in) → Standard input (type: `istream`)
2. **cout** (see-out) → Standard output (type: `ostream`)
3. **cerr** (see-err) → Standard error (type: `ostream`)
4. **clog** (see-log) → General information (type: `ostream`)

Among these, **cin** and **cout** are the most commonly used.

---

## Example: Using cin & cout

```cpp
#include <iostream>

int main() {
    int age;
    
    std::cout << "Enter your age: ";  // Output
    std::cin >> age;  // Input
    
    std::cout << "You are " << age << " years old.\n";  // Output
    
    return 0;
}
```

### Explanation:
 - std::cout is used to display text on the screen.
 - std::cin is used to take user input.
 - The >> operator is used to take input, while the << operator is used for output.


