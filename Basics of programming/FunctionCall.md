# [What is a Function Call?](#what-is-a-function-call)
A function call in C++ is the process of executing a function by specifying its name along with the required arguments (if any). When a function is called, the program control transfers to the function definition, executes the function body, and then returns back to the point from where it was called.<br>

A function call is an expression that invokes a function to perform a specific task. It passes control and possibly arguments to the function and may receive a return value after execution.<br>

## Syntax:-
```
function_name(argument1, argument2, ...);
```

 - ```function_name:``` The name of the function to be executed.
 - ```arguments:``` The values passed to the function (if required).


## Example of a Function Call:
```
#include <iostream>
using namespace std;

void greet() {
    cout << "Hello, World!" << endl;
}

int main() {
    greet();  // Function call
    return 0;
}
```
<br>
<br>


## Types of Function call:-

### [1. Call by Value](#1-call-by-value)
Call by Value is a function calling mechanism where a copy of the actual argument is passed to the function. Any modifications made inside the function do not affect the original variable.

Explanation:
The function gets a separate copy of the variable.
Changes made inside the function do not reflect outside.
Used when we want to protect the original data from being modified.

Example:
```
#include <iostream>
using namespace std;

void modify(int x) {  // x is a copy of the original variable
    x = x + 10;       // Changes only the local copy
}

int main() {
    int a = 5;
    modify(a);  // Pass by value
    cout << "Value of a after function call: " << a << endl;  // Output: 5
    return 0;
}
```

***Key Point:*** The value of a remains unchanged after the function call.
<br>
<br>

### [2. Call by Address](#2-call-by-address)
Call by Address (also called Call by Pointer) is a mechanism where the address of the actual argument is passed to the function. The function modifies the value of the original variable using the pointer.

Explanation:
The function gets a pointer to the actual variable.
Any modification inside the function affects the original variable.
Useful when we need to modify the actual data or work with dynamically allocated memory.

Example:
```
#include <iostream>
using namespace std;

void modify(int *x) {  // x is a pointer to the original variable
    *x = *x + 10;      // Modifies the actual variable
}

int main() {
    int a = 5;
    modify(&a);  // Pass by address
    cout << "Value of a after function call: " << a << endl;  // Output: 15
    return 0;
}
```

***Key Point:*** The value of a gets updated because we pass its address.
<br>
<br>

### [3. Call by Reference](#3-call-by-reference)
Call by Reference is a function calling mechanism where a reference to the actual argument is passed to the function. The function operates directly on the original variable.

Explanation:
The function gets a reference to the original variable, not a copy.
Any modifications inside the function reflect in the caller.
Works like Call by Address but uses references instead of pointers.

Example:
```
#include <iostream>
using namespace std;

void modify(int &x) {  // x is a reference to the actual variable
    x = x + 10;        // Modifies the actual variable
}

int main() {
    int a = 5;
    modify(a);  // Pass by reference
    cout << "Value of a after function call: " << a << endl;  // Output: 15
    return 0;
}
```
***Key Point:*** The value of a is updated without using pointers.
<br>
<br>


## 📝 Cross Comparison of Types of function call

| Function Call Type  | Passing Mechanism  | Modifies Original Variable? | Use Case |
|--------------------|------------------|----------------------------|---------|
| **Call by Value**      | Copy of variable  | ❌ No                         | When original value must be preserved |
| **Call by Address**   | Pointer to variable | ✅ Yes                        | When modifying original data using pointers |
| **Call by Reference** | Reference to variable | ✅ Yes                        | When modifying original data without pointers |
