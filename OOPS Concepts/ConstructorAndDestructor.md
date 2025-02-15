# [Constructor and Destructor in C++](#constructor-and-destructor-in-c)

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
<br>

# [**Types of Constructors in C++**](#types-of-constructors-in-c)

In C++, a constructor is a special member function that initializes objects when they are created. The four main types of constructors are:

---

## **1. Default Constructor (Empty Constructor)**
A **default constructor** is a constructor that takes no arguments and initializes the object with default values.

### **Characteristics:**
- No parameters.
- Called automatically when an object is created.
- If no constructor is provided, the compiler generates a default constructor.

### **Example:**
```cpp
#include <iostream>
using namespace std;

class Example {
public:
    Example() {  // Default Constructor
        cout << "Default Constructor Called!" << endl;
    }
};

int main() {
    Example obj;  // Calls the default constructor
    return 0;
}
```
<br>
<br>


## **2. Parameterized Constructor**
A **parameterized constructor** allows passing arguments to initialize an object with specific values.

### **Characteristics:**
- Takes one or more parameters.
- Used to assign specific values to object members.

### **Example:**
```cpp
#include <iostream>
using namespace std;

class Example {
    int num;
public:
    Example(int n) {  // Parameterized Constructor
        num = n;
    }
};

int main() {
    Example obj(10);  // Calls the parameterized constructor
    return 0;
}
```
<br>
<br>


## **3. Copy Constructor**
A **copy constructor** creates a new object as a copy of an existing object.

### **Characteristics:**
- Takes a reference to an existing object of the same class.
- Ensures that a new object is initialized with the values of another object.

### **Example:**
```cpp
#include <iostream>
using namespace std;

class Example {
    int num;
public:
    Example(int n) {  // Parameterized Constructor
        num = n;
    }
    
    Example(const Example &obj) {  // Copy Constructor
        num = obj.num;
    }
};

int main() {
    Example obj1(20);  // Calls parameterized constructor
    Example obj2(obj1); // Calls copy constructor
    return 0;
}
```


## **4. Move Constructor (C++11 and later)**
A **move constructor** transfers ownership of resources from one object to another, preventing unnecessary deep copies.

### **Characteristics:**
- Introduced in **C++11**.
- Uses **rvalue references (`&&`)**.
- Efficient when working with dynamically allocated memory.

### **Example:**
```cpp
#include <iostream>
using namespace std;

class Example {
    int* ptr;
public:
    Example(int val) {  // Parameterized Constructor
        ptr = new int(val);
    }

    // Move Constructor
    Example(Example&& obj) noexcept {
        ptr = obj.ptr; // Transfer ownership
        obj.ptr = nullptr; // Prevent old object from deleting memory
    }

    ~Example() {  // Destructor
        delete ptr;
    }
};

int main() {
    Example obj1(30);
    Example obj2(move(obj1)); // Calls the move constructor
    return 0;
}
```
<br>
<br>


## **Summary of Constructor Types**

| Constructor Type           | Description |
|----------------------------|-------------|
| **Default Constructor**     | No parameters, initializes with default values. |
| **Parameterized Constructor** | Takes arguments to initialize members. |
| **Copy Constructor**        | Creates a new object as a copy of an existing object. |
| **Move Constructor**        | Transfers ownership of resources from one object to another (C++11+). |
<br>
<br>

---




