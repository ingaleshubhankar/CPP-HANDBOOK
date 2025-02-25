# [Stograge Classes](#stograge-classes)
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
> **Lifetime:** Till the end of the program
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
<br>



### [3. static Storage Class](#3-static-storage-class)
A static variable in C++ keeps its value even after the function where it was declared finishes running. Unlike normal variables that get created and destroyed each time a function runs, a static variable is initialized only once and retains its value throughout the program's execution.

When a static variable is inside a function, it remembers its last stored value every time the function is called. This makes it useful for counting function calls or storing values that shouldn’t reset between function calls.

If a static variable is declared globally (outside of functions), it is only accessible within the same file. Unlike extern variables, which can be used across multiple files, global static variables have internal linkage, meaning they are restricted to the file where they are defined.

They are declared using static keyword.

**Properties** of auto Storage Class Objects
> **Scope:** Local <br>
> **Default Value:** Zero <br>
> **Memory Location:** RAM <br>
> **Lifetime:** Till the end of the program
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
<br>



### [4. register Storage Class](#4-register-storage-class)
The register storage class is used to suggest that a variable should be stored in a CPU register instead of the main memory (RAM). This makes accessing the variable much faster because registers are the quickest storage locations inside the processor.

However, the compiler decides whether to store the variable in a register or not based on availability. If no free registers are available, the variable is stored in RAM like a normal variable.

One special rule about register variables is that **you cannot get their memory address using pointers** because they might be stored in a register instead of RAM.

Properties of register Storage Class Objects.

**Properties** of auto Storage Class Objects
> **Scope:** Local <br>
> **Default Value:** Garbage Value <br>
> **Memory Location:** Register in CPU or RAM <br>
> **Lifetime:** Till the end of its scope
<br>

#### Example:
```cpp
#include <iostream>

int main() {
    register int count = 10;  // Suggests storing count in a CPU register
    std::cout << "Count: " << count << std::endl;

    // Trying to get the address (this will cause an error)
    // std::cout << &count; 

    return 0;
}
```

#### Pointers:-
 - register suggests faster access by storing the variable in a CPU register.
 - If no free register is available, it behaves like a normal variable in RAM.
 - You cannot get the memory address of a register variable using pointers.
 - Modern compilers often ignore the register keyword because they automatically optimize variable storage for the best performance.
<br>


### [5. Mutable Storage Class](#5-mutable-storage-class)
The mutable storage class is used inside classes or structs when you want to allow specific variables to be modified, even if the object itself is marked as const.

Normally, when an object is declared as const, none of its data members can be changed. However, sometimes you might need to update only a particular member, such as a cache value or a log counter, without modifying the entire object. In such cases, the mutable keyword helps by making that specific variable modifiable inside const functions.

**Properties** of mutable Storage Class Objects
 > The mutable specifier **does NOT** affect the **linkage** or **lifetime** of the object.
 > It will be the **same as the normal object** declared in that place.
<br>

#### Example:
```cpp
#include <iostream>
using namespace std;

class A {
public:
    int x;

    // Defining mutable variable y
    // now this can be modified
    mutable int y;

    A(): x(4), y(10) {}
};

int main() {
  
    // a is created as constant
    const A a;

    // Trying to change the value
    a.y = 200;
    cout << a.y;

    // Uncommenting below lines
    // will throw error
    /* a.x = 8;
    cout << a.x; */
  
    return 0;
}
```
<br>



### [5. thread_local Storage Class](#5-thread_local-storage-class)
The **thread_local storage class was introduced in C++11** and is used to create variables that are unique to each thread. This means that **every thread gets its own separate copy of the variable**, preventing data conflicts when multiple threads are running.

A thread_local variable exists only as long as the thread is running. When the thread ends, its copy of the variable is destroyed.

You can also combine thread_local with static (to make it last for the thread’s lifetime) or extern (to share it across multiple files but still per thread).

**Properties** of mutable Storage Class Objects
 > **Memory Location:** RAM.
 > **Lifetime:** Till the **end of its thread**.
<br>




#### Example:
```cpp
#include <iostream>
#include <thread>
#include <mutex>

using namespace std;

// Defining thread-local variable
thread_local int count = 5;

// Mutex for synchronization
mutex mtx;

void modifyValue(int increment, const string& threadName) {
    count += increment;
    
    // Locking for safe console output
    lock_guard<mutex> lock(mtx);
    cout << threadName << " value: " << count << '\n';
}

int main() {
    // Creating threads
    thread th1(modifyValue, 10, "Thread 1");
    thread th2(modifyValue, 20, "Thread 2");
    thread th3(modifyValue, 30, "Thread 3");

    // Wait for all threads to finish
    th1.join();
    th2.join();
    th3.join();

    // Print the value of count in the main thread
    cout << "Main thread value: " << count << '\n';

    return 0;
}
```
<br>

##### Output:
```
Thread 1 value: 15
Thread 2 value: 25
Thread 3 value: 35
Main thread value: 5
```


##### Explaination:
 - Each thread gets its own separate count variable because of thread_local, meaning their modifications don’t affect each other.

 - Each thread increments its own version of count independently.
A mutex (mtx) is used to prevent mixed-up console output when multiple threads print messages.


