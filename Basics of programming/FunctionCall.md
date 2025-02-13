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
