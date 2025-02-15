# [Access Specifiers in C++](#access-specifiers-in-c)
Access specifiers control the visibility and accessibility of class members (data members and member functions). C++ provides three main access specifiers:
1. Private (private)
2. Protected (protected)
3. Public (public)

Additionally, we will discuss Friend functions and classes, which bypass these access controls.


## 1. Private (`private`)

**Scope:**
- Accessible only within the class.
- Not accessible from outside the class, even in derived classes.
- Default access level for class members.

```cpp
#include <iostream>
using namespace std;

class PrivateExample {
private:
    int data; // Private member

public:
    void setData(int d) { data = d; } // Public setter function
    int getData() { return data; } // Public getter function
};

int main() {
    PrivateExample obj;
    obj.setData(10); // Allowed
    cout << obj.getData() << endl; // Allowed

    // obj.data = 20; // ❌ Error: 'data' is private
    return 0;
}
```

### 👉 Why private?
- Helps in data hiding and encapsulation.
- Prevents direct modification of variables, ensuring controlled access through methods.
<br>


---

## 2. Protected (`protected`)

**Scope:**
- Accessible within the class and derived (child) classes.
- Not accessible outside the class unless inherited.
- Used in inheritance when you want derived classes to access members but keep them hidden from external access.

```cpp
class Base {
protected:
    int protectedVar;

public:
    void setVar(int v) { protectedVar = v; }
};

class Derived : public Base {
public:
    void show() {
        cout << "Protected Variable: " << protectedVar << endl; // Allowed
    }
};

int main() {
    Derived obj;
    obj.setVar(50);
    obj.show();

    // obj.protectedVar = 100; // ❌ Error: Not accessible outside class
    return 0;
}
```

### 👉 Why protected?
- Useful in inheritance scenarios where child classes need access to parent class members but outside access should be restricted.
<br>


---

## 3. Public (`public`)

**Scope:**
- Accessible from anywhere.
- Used for interfaces, i.e., functions that need to be accessible to other parts of the program.

```cpp
class PublicExample {
public:
    int publicVar; // Public variable

    void display() {
        cout << "Public Variable: " << publicVar << endl;
    }
};

int main() {
    PublicExample obj;
    obj.publicVar = 10; // Allowed
    obj.display();
    return 0;
}
```

### 👉 Why public?
- Used for functions and variables that should be accessible from outside the class.
<br>


---

## Friend Functions & Friend Classes
C++ provides the `friend` keyword to allow private and protected members to be accessed by specific external functions or classes.

For more details on this concept, refer [Friend]()