# What is a Function Call?
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


## Types of Function call:-

### 1. Call by Value
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

