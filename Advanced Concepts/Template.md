# Template

Templates in C++ allow us to write generic code that works with different data types without having to rewrite the same logic multiple times. This is useful when we want to create functions or classes that can handle multiple data types efficiently.

## 1. What is a Template?
A template is a blueprint for creating functions or classes that can operate on different data types. Instead of writing separate versions of a function or class for `int`, `float`, `double`, etc., we define a single template that adapts to different types automatically.

## 2. Why Use Templates?
- **Code Reusability**: Avoids duplicating code for different data types.
- **Type Safety**: Ensures that only valid operations are performed on the data.
- **Flexibility**: Works with any data type, including user-defined types.

## 3. Function Templates
A function template allows us to define a function that works with any data type.

### Example of a Function Template
```cpp
#include <iostream>
using namespace std;

// Function template to find the maximum of two values
template <typename T>
T findMax(T a, T b) {
    return (a > b) ? a : b;
}

int main() {
    cout << "Max of 10 and 20: " << findMax(10, 20) << endl;
    cout << "Max of 5.5 and 2.3: " << findMax(5.5, 2.3) << endl;
    cout << "Max of 'A' and 'Z': " << findMax('A', 'Z') << endl;
    return 0;
}
```

### Explanation
- `template <typename T>` tells the compiler that `T` is a placeholder for any data type.
- The function `findMax(T a, T b)` works for `int`, `float`, `char`, and any type that supports the `>` operator.
- When we call `findMax(10, 20)`, the compiler automatically replaces `T` with `int`.
- For `findMax(5.5, 2.3)`, `T` is replaced with `double`, and so on.

## 4. Class Templates
A class template allows us to define a class that can work with any data type.

### Example of a Class Template
```cpp
#include <iostream>
using namespace std;

// Class template for a simple Box
template <typename T>
class Box {
private:
    T value;
public:
    Box(T val) { value = val; }
    void show() { cout << "Value: " << value << endl; }
};

int main() {
    Box<int> intBox(10);
    intBox.show();  // Output: Value: 10

    Box<double> doubleBox(5.7);
    doubleBox.show();  // Output: Value: 5.7

    Box<string> strBox("Hello Templates");
    strBox.show();  // Output: Value: Hello Templates

    return 0;
}
```

### Explanation
- `template <typename T>` allows us to use `T` as a placeholder for any data type.
- The `Box` class stores a value of type `T`.
- We create different objects: `Box<int>`, `Box<double>`, and `Box<string>`, and the template adapts accordingly.

## 5. Advantages of Templates
 ✅ **Faster Development**: No need to rewrite similar functions/classes for different types.
 ✅ **Better Maintainability**: One template can replace multiple function/class definitions.
 ✅ **Increased Performance**: The compiler generates optimized code for each data type at compile time.

