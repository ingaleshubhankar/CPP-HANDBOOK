# [Inline Function in C++](#inline-function-in-c)
An inline function in C++ is a function that the compiler expands in place wherever it is called, instead of performing a normal function call. This can improve performance by reducing the overhead of function calls, especially for small and frequently used functions.


## [1. Syntax of Inline Function](#1-syntax-of-inline-function)
To define an inline function, use the inline keyword before the function 
```cpp
#include <iostream>
using namespace std;

inline int square(int x) {
    return x * x;
}

int main() {
    cout << "Square of 5: " << square(5) << endl;
    return 0;
}
```


### How It Works?
When square(5) is called, the compiler replaces it with 5 * 5 directly.
This eliminates the overhead of a function call (like pushing arguments to the stack, jumping to the function, etc.).
<br>
<br>


### When to Use Inline Functions?
✅ Use inline functions for:
 - Small functions (typically 1-5 lines).
 - Functions that are frequently called.
 - Simple getter/setter methods in classes.
<br>

🚫 Avoid inline functions for:
 - Large or complex functions (they increase code size).
 - Functions that use loops, recursion, or static variables.
 - Functions that are modified frequently (as every modification requires recompiling all code using them).
<br>
<br>


## [2. Inline Function in Classes](#2-inline-function-in-classes)
In C++, class member functions defined inside the class are implicitly inline.
```cpp
#include <iostream>
using namespace std;

class Math {
public:
    inline int cube(int x) { return x * x * x; } // Explicit inline function
};

int main() {
    Math m;
    cout << "Cube of 3: " << m.cube(3) << endl;
    return 0;
}
```
<br>

### Compiler Decision on Inlining
The inline keyword is only a request to the compiler; it may ignore it if the function is too large or complex. Modern compilers use optimization techniques and decide whether to inline a function based on performance trade-offs.
<br>


### Advantages & Disadvantages
✅ Advantages:
 - Eliminates function call overhead.
 - Improves performance for small functions.
 - Helps in better optimization by the compiler.

🚫 Disadvantages:
 - Increases code size (code bloat) if overused.
 - Can lead to cache inefficiency if too many functions are inlined.
 - Changes in the function require recompilation of all code using it.
<br>
<br>



