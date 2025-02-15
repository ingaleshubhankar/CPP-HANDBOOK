# Stograge Classes
Think of C++ Storage Classes like different types of storage where variables and functions are kept. Each type of storage has specific rules about where the data is stored, how long it stays, and who can access it.

Storage classes in C++ primarily apply to **variables**, But some storage class specifiers can also be used with functions. However, not all storage classes are applicable to functions. Let's break it down:

## Storage Classes for Variables vs. Functions

| Storage Class  | Used with Variables? | Used with Functions? |
|--------------|------------------|-----------------|
| `auto`      | ✅ Yes | ❌ No (implied for local variables) |
| `static`    | ✅ Yes | ✅ Yes (makes function **local to file**) |
| `extern`    | ✅ Yes | ✅ Yes (makes function **available globally**) |
| `register`  | ✅ Yes (suggests CPU register storage) | ❌ No |
| `mutable`   | ✅ Yes (only in class members) | ❌ No |
<br>
<br>

## When you declare a variable in C++, its storage class defines:
 - **Where** it is stored (memory location).
 - **How long** it exists (lifetime).
 - **Who** can access it (scope/visibility).
 - What its **default value** is (if not initialized explicitly).
<br>


## C++ provides 6 different storage classes, which are as follows:
 1) auto Storage Class
 2) extern Storage Class
 3) static Storage Class
 4) register Storage Class
 5) mutable Storage Class
 6) thread_local Storage Class


### [1. auto Storage Class](#1-auto-storage-class)
The auto storage class is the default class of all the variables declared inside a block. The auto stands for automatic and all the local variables that are declared in a block automatically belong to this class.

**Properties** of auto Storage Class Objects
> **Scope:** Local <br>
> **Default Value:** Garbage Value <br>
> **Memory Location:** RAM <br>
> **Lifetime:** Till the end of its scope <br>
<br>



### [2. extern Storage Class](#2-extern-storage-class)
The extern storage class allows a variable to be defined in one file and used in another. It tells the compiler that the variable is declared somewhere else, so it doesn’t allocate memory for it again. Instead, it looks for the actual definition in another file during the linking process.

In simpler terms, extern is like a reference to a global variable that is already defined elsewhere. This is useful in large programs where multiple files need to share the same variable without duplicating its definition.

**Properties** of auto Storage Class Objects
> **Scope:** Global <br>
> **Default Value:** Zero <br>
> **Memory Location:** RAM <br>
> **Lifetime:** Till the end of the program <br>
<br>

#### Example:
File 1 (Defines the variable)
```cpp
// file1.cpp
#include <iostream>

int count = 10;  // Variable defined here

void display() {
    std::cout << "Count: " << count << std::endl;
}
```

File 2 (Uses the variable)
```cpp
// file2.cpp
#include <iostream>

extern int count;  // Declaring (not defining) the variable

int main() {
    std::cout << "Using extern: " << count << std::endl;
    return 0;
}
```

### [3. static Storage Class](#3-static-storage-class)
A static variable in C++ keeps its value even after the function where it was declared finishes running. Unlike normal variables that get created and destroyed each time a function runs, a static variable is initialized only once and retains its value throughout the program's execution.

When a static variable is inside a function, it remembers its last stored value every time the function is called. This makes it useful for counting function calls or storing values that shouldn’t reset between function calls.

If a static variable is declared globally (outside of functions), it is only accessible within the same file. Unlike extern variables, which can be used across multiple files, global static variables have internal linkage, meaning they are restricted to the file where they are defined.

They are declared using static keyword.

**Properties** of auto Storage Class Objects
> **Scope:** Local <br>
> **Default Value:** Zero <br>
> **Memory Location:** RAM <br>
> **Lifetime:** Till the end of the program <br>
<br>


#### Example:

##### Ex1 : Static Variable Inside a Function
```cpp
#include <iostream>

void counter() {
    static int count = 0;  // Initialized only once
    count++;  // Retains its value between function calls
    std::cout << "Count: " << count << std::endl;
}

int main() {
    counter();
    counter();
    counter();
    return 0;
}
```

###### Output:
```
Count: 1  
Count: 2  
Count: 3  
```
Here, count retains its previous value instead of resetting to 0 on every function call.
<br>


##### Ex2 : Static Global Variable Example
```cpp
#include <iostream>

static int num = 100;  // Can only be used in this file

void display() {
    std::cout << "Num: " << num << std::endl;
}

int main() {
    display();
    return 0;
}
```
In this case, num is a global static variable, meaning it cannot be accessed from another file.
<br>





