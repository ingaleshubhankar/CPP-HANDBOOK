# Constructor and Destructor in C++

## 1.Constructor
A constructor is a special member function in C++ that is automatically called when an object of a class is created. It is mainly used to initialize the object's properties.

### Key Features of a Constructor:
 - Has the same name as the class.
 - Does not have a return type (not even void).
 - Can be overloaded.
 - Is called automatically when an object is created.


#### Example of a Constructor:
```cpp
#include <iostream>
using namespace std;

class Car {
public:
    string brand;

    // Constructor
    Car(string b) {
        brand = b;
        cout << "Constructor called for " << brand << endl;
    }
};

int main() {
    Car car1("Toyota");
    Car car2("Honda");

    return 0;
}
```
##### Output:
```
Constructor called for Toyota
Constructor called for Honda
```

## 2. Destructor
A destructor is a special member function that is automatically called when an object goes out of scope or is deleted. It is used to free resources like memory, file handles, etc.

### Key Features of a Destructor:
 - Has the same name as the class, but with a ~ (tilde) before it.
 - Does not take any parameters.
 - Cannot be overloaded.
 - Is called automatically when an object is destroyed.

#### Example of a Destructor:
```cpp
#include <iostream>
using namespace std;

class Car {
public:
    string brand;

    // Constructor
    Car(string b) {
        brand = b;
        cout << "Constructor called for " << brand << endl;
    }

    // Destructor
    ~Car() {
        cout << "Destructor called for " << brand << endl;
    }
};

int main() {
    Car car1("Toyota");
    Car car2("Honda");

    return 0; // When the program exits, destructors are called automatically
}
```

##### Output:
```
Constructor called for Toyota
Constructor called for Honda
Destructor called for Honda
Destructor called for Toyota
```


## Features comparison:
| Feature         | Constructor | Destructor |
|---------------|-------------|-------------|
| Purpose       | Initializes an object | Cleans up before object destruction |
| Naming       | Same as class name | Same as class name with `~` prefix |
| Parameters  | Can take parameters (overloaded) | No parameters (cannot be overloaded) |
| Return Type | No return type | No return type |
| Invocation | Called when an object is created | Called when an object is destroyed |
| Number of calls | Once per object creation | Once per object destruction |
<br>
<br>




