# Exception Handling in C++

Exception handling in C++ is a mechanism used to handle runtime errors or exceptional situations in a structured way. It helps prevent program crashes and allows developers to manage errors efficiently.

## Why Exception Handling?

- **Prevents crashes** – Instead of terminating the program abruptly, exceptions allow handling errors gracefully.
- **Improves readability** – Separates error-handling logic from regular code.
- **Ensures robustness** – Helps in writing reliable and maintainable programs.

## Key Keywords in Exception Handling

C++ uses three main keywords for exception handling:

- **`try`** – Defines a block of code where an exception might occur.
- **`throw`** – Used to throw an exception when an error occurs.
- **`catch`** – Handles the exception thrown from the `try` block.

## Basic Syntax

```cpp
#include <iostream>
using namespace std;

int main() {
    try {
        // Code that might throw an exception
        int a = 10, b = 0;
        if (b == 0)
            throw "Division by zero error";  // Throwing an exception

        int result = a / b;
        cout << "Result: " << result << endl;
    } 
    catch (const char* errorMsg) {
        // Handling the exception
        cout << "Exception caught: " << errorMsg << endl;
    }

    cout << "Program continues..." << endl;
    return 0;
}
```

### Explanation:
1. Inside the `try` block, we attempt division by zero.
2. If `b` is zero, we throw an exception (`throw "Division by zero error";`).
3. The `catch` block catches the thrown exception and handles it.
4. The program continues execution after handling the exception.

## Multiple Catch Blocks

You can have multiple `catch` blocks to handle different types of exceptions.

```cpp
#include <iostream>
using namespace std;

void testException(int num) {
    try {
        if (num == 0)
            throw 0;           // Throwing an integer exception
        else if (num == 1)
            throw "String exception";  // Throwing a string exception
        else
            throw 4.5;         // Throwing a double exception
    }
    catch (int e) {
        cout << "Caught an integer exception: " << e << endl;
    }
    catch (const char* msg) {
        cout << "Caught a string exception: " << msg << endl;
    }
    catch (...) {  // Catch-all block
        cout << "Caught an unknown exception" << endl;
    }
}

int main() {
    testException(0);
    testException(1);
    testException(2);
    return 0;
}
```

### Output:
```
Caught an integer exception: 0
Caught a string exception: String exception
Caught an unknown exception
```

## Catching Exceptions by Reference

Instead of passing exceptions by value, it's recommended to catch them by reference (`&`), especially for objects.

```cpp
#include <iostream>
using namespace std;

class MyException {
public:
    void showMessage() {
        cout << "Custom exception occurred!" << endl;
    }
};

int main() {
    try {
        throw MyException();  // Throwing an object
    }
    catch (MyException &e) {  // Catching by reference
        e.showMessage();
    }
    return 0;
}
```

## Summary

- **`try`** block contains the risky code.
- **`throw`** is used to trigger an exception.
- **`catch`** handles the exception.
- **Multiple `catch` blocks** can handle different exception types.
- **`catch(...)`** is a generic catch-all block.
- **Using `std::exception`** provides a standard way to handle errors.