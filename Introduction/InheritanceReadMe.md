# Inheritance
`Inheritance` is a fundamental concept in object-oriented programming (OOP) that promotes **reusability**. It allows a new class to acquire the properties and behaviors of an existing class, enabling the creation of new products based on existing ones. In C++, inheritance enables a class to **inherit all characteristics and behaviors of its parent class automatically**, allowing you to **reuse**, **extend**, or **modify** attributes and behaviors.

## Types of Inheritance in C++:
1. **Single Inheritance:** In this type, a class inherits from a single base class.
2. **Multilevel Inheritance:** Here, a class derives from another derived class, forming a chain.
3. **Multiple Inheritance:** In this form, a class inherits from more than one base class.
4. **Hierarchical Inheritance:** In this structure, multiple classes inherit from a single base class.
5. **Hybrid Inheritance:** This is a combination of two or more types of inheritance.

### Example: Single Inheritance
```cpp
#include <iostream>
using namespace std;

class Vehicle {  // Base class
public:
    void drive() {
        cout << "Driving the vehicle." << endl;
    }
};

class Car : public Vehicle {  // Derived class
public:
    void honk() {
        cout << "Honking the car horn." << endl;
    }
};

int main() {
    Car myCar;
    myCar.drive();  // Inherited from Vehicle
    myCar.honk();   // Defined in Car
    return 0;
}
```

### Key Points:
 - Base Class (Vehicle): Defines a method drive().
 - Derived Class (Car): Inherits from Vehicle and adds its own specific behavior (honk()).
 - Usage: In the main() function, an object of Car is created. This object can access the inherited drive() method and its own honk() method.
<br>
This above structure demonstrates **how single inheritance allows a derived class to inherit and extend the functionality of a base class**, promoting code reusability and logical organization.
<br>

---