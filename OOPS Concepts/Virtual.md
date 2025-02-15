# [Virtual Concept in C++](#virtual-concept-in-c)

## [1. Virtual Functions](#1-virtual-functions)

### What is a Virtual Function?
A **virtual function** in C++ is a function that is **declared** in the **base class** and is meant to be **overridden in the derived class**. When a base class pointer or reference is used to call a virtual function, the function that gets executed is the one in the derived class (if overridden), not the one in the base class. This behavior is known as **dynamic dispatch** or **runtime polymorphism**.
<br>


### Why Do We Need Virtual Functions?
By default, C++ uses **compile-time binding** (also known as static binding). This means that if a base class pointer or reference is used to call a function, the function from the base class will be executed, even if the pointer actually points to a derived class object. This is a limitation when trying to implement polymorphism, where we expect different behavior based on the actual object type.<br>


To enable **runtime binding** (also called dynamic binding), we use virtual functions. This ensures that the function call is resolved at runtime instead of compile-time.
<br>
<br>


### Example of Virtual Function
```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void show() {  // Virtual function
        cout << "Base class show function" << endl;
    }
};

class Derived : public Base {
public:
    void show() override {  // Overrides Base::show()
        cout << "Derived class show function" << endl;
    }
};

int main() {
    Base* basePtr; 
    Derived d;
    basePtr = &d;

    basePtr->show();  // Calls Derived class function due to dynamic binding

    return 0;
}
```
**Output:**
```
Derived class show function
```

---

## [2. Virtual Destructor](#2-virtual-destructor)
If a base class has a virtual function, the **destructor should also be virtual** to ensure proper cleanup.

### Example of Virtual Destructor
```cpp
#include <iostream>
using namespace std;

class Base {
public:
    Base() { cout << "Base Constructor\n"; }
    virtual ~Base() { cout << "Base Destructor\n"; }  // Virtual destructor
};

class Derived : public Base {
public:
    Derived() { cout << "Derived Constructor\n"; }
    ~Derived() { cout << "Derived Destructor\n"; }
};

int main() {
    Base* basePtr = new Derived();
    delete basePtr;  // Ensures proper cleanup

    return 0;
}
```
**Output:**
```
Base Constructor
Derived Constructor
Derived Destructor
Base Destructor
```

---

## [3. Pure Virtual Functions & Abstract Classes](#3-pure-virtual-functions--abstract-classes)
A **pure virtual function** has no definition in the base class and must be overridden in derived classes. A class containing a pure virtual function is called an **abstract class**.

### Example of Abstract Class
```cpp
#include <iostream>
using namespace std;

class Shape {
public:
    virtual void draw() = 0;  // Pure virtual function
};

class Circle : public Shape {
public:
    void draw() override {
        cout << "Drawing a Circle" << endl;
    }
};

int main() {
    Shape* shapePtr = new Circle();
    shapePtr->draw();
    delete shapePtr;
    return 0;
}
```
**Output:**
```
Drawing a Circle
```

---

## [4. VTable](#4-vtable)
When a class has virtual functions, the compiler creates a **virtual table (vtable)** storing function pointers. Each object has a **vptr (virtual table pointer)** to enable dynamic dispatch.

### Example of VTable Usage
```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void fun1() { cout << "Base fun1" << endl; }
    virtual void fun2() { cout << "Base fun2" << endl; }
};

class Derived : public Base {
public:
    void fun1() override { cout << "Derived fun1" << endl; }
};

int main() {
    Base* basePtr;
    Derived d;
    basePtr = &d;

    basePtr->fun1();  // Calls Derived::fun1()
    basePtr->fun2();  // Calls Base::fun2() (not overridden)

    return 0;
}
```
**Output:**
```
Derived fun1
Base fun2
```

---

## [Rules for Virtual Functions](#rules-for-virtual-functions)
1. **Declared in Base, Overridden in Derived** – Not mandatory but recommended.
2. **Works with Pointers or References** – Static binding applies otherwise.
3. **Destructors Should Be Virtual** – Prevents memory leaks.
4. **Constructors Cannot Be Virtual** – Object creation must be known at compile-time.
5. **Abstract Classes Cannot Be Instantiated** – They enforce function overrides.

---
