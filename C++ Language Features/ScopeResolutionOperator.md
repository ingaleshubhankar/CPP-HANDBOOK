# Scope Resolution Operator (::) in C++
The Scope Resolution Operator (::) in C++ is used to define and access members (variables, functions, etc.) that belong to a specific scope, such as a class, namespace, or global scope. It helps differentiate between local and global identifiers with the same name.
<br>


## Uses of Scope Resolution Operator in C++

### 1. Accessing Global Variables
If a local variable has the same name as a global variable, `::` can be used to access the global variable.

#### Example:
```cpp
#include <iostream>
using namespace std;

int x = 10;  // Global variable

int main() {
    int x = 20;  // Local variable
    cout << "Local x: " << x << endl;
    cout << "Global x: " << ::x << endl; // Using scope resolution to access global x
    return 0;
}
```

##### Output:
```
Local x: 20
Global x: 10
```
<br>



### 2. Defining a Class Member Outside the Class
C++ allows function definitions to be written outside the class using ::.

#### Example:
```cpp
#include <iostream>
using namespace std;

class MyClass {
public:
    void display();  // Function declaration
};

// Function definition outside the class using scope resolution operator
void MyClass::display() {
    cout << "Hello from MyClass!" << endl;
}

int main() {
    MyClass obj;
    obj.display();
    return 0;
}
```

##### Output:
```
Hello from MyClass!
```
<br>


### 3. Accessing Static Class Members
Static members belong to the class rather than any specific object. They can be accessed using the class name with ::.

#### Example
```cpp
include <iostream>
using namespace std;

class Demo {
public:
    static int count;
};

// Defining static member outside the class
int Demo::count = 5;

int main() {
    cout << "Static count: " << Demo::count << endl;
    return 0;
}
```

##### Output:
```
Static count: 5
```
<br>


### 4. Accessing Namespace Members
If there are multiple namespaces, :: is used to specify which namespace’s member to access.

#### Example
```cpp
#include <iostream>

namespace A {
    int num = 100;
}

int main() {
    std::cout << "Value from namespace A: " << A::num << std::endl;
    return 0;
}
```


##### Output:
```
Value from namespace A: 100
```
