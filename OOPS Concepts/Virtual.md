# Virtual Concept in C++

## 1. Virtual Functions
A **virtual function** is a function in a **base class** that can be **overridden** in a **derived class**. It enables **dynamic binding** at runtime.

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

## 2. Virtual Destructor
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

## 3. Pure Virtual Functions & Abstract Classes
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

## 4. Virtual Table (VTable) and Virtual Pointer (VPTR)
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

## 5. Rules for Virtual Functions
1. **Declared in Base, Overridden in Derived** – Not mandatory but recommended.
2. **Works with Pointers or References** – Static binding applies otherwise.
3. **Destructors Should Be Virtual** – Prevents memory leaks.
4. **Constructors Cannot Be Virtual** – Object creation must be known at compile-time.
5. **Abstract Classes Cannot Be Instantiated** – They enforce function overrides.

---
