# [OOPS Concepts](#oops-concepts)

## [Classes and Objects](#classes-and-objects)
Object-Oriented Programming (OOP) is a way of designing programs using objects, which helps organize and reuse code easily.<br>

Let's see! I'll now explain the basic ideas of Object-Oriented Programming (OOP), like encapsulation, inheritance, polymorphism, and abstraction, in a simple and easy-to-understand way.
<br>
<br>

### [Classes](#classes)
The **class** is user defined type which consist of both data and function of the object. A class is like a blueprint for a house. It defines what the house will have: the number of rooms, the type of roof, etc. 

### [Objects](#objects)
The term **objects** are run-time entities entities in an object oriented system. It combines into single unit both data and functions.<br>

An object is an actual house built using that blueprint. You can build many houses (objects) from the same blueprint (class), but each house can have different details, like the color of the walls or the furniture inside.

**Example:-**
```cpp
class Car {
public:
    string brand;
    int year;
    
    void displayInfo() {
        cout << "Brand: " << brand << ", Year: " << year << endl;
    }
};

int main() {
    Car car1;  // car1 is an object of class Car
    car1.brand = "Toyota";
    car1.year = 2020;
    car1.displayInfo();  // This will print: Brand: Toyota, Year: 2020

    Car car2;  // car2 is another object of class Car
    car2.brand = "Honda";
    car2.year = 2021;
    car2.displayInfo();  // This will print: Brand: Honda, Year: 2021

    return 0;
}
```
<br>


## [Data Abstraction](#data-abstraction)
 - Abstraction means hiding the details of how something works and showing only what is necessary. It allows users to interact with a system without needing to understand its internal workings.

 - In programming, abstraction can be achieved by using access modifiers like the private keyword to hide certain parts of the code.

 For more detailed explaination please refer [Abstraction](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Introduction/AbstractionReadMe.md)
<br>
<br>



## [Encapsulation](#encapsulation)
 - The process of binding data and procedure into single unit is known as Encapsulation.
 - Encapsulation in C++ is the concept of bundling the data (variables) and the methods (functions) that operate on the data into a single unit, called a class. It also restricts direct access to some of the object's components, which is done to protect the integrity of the object.

 - Think of a class like a box that hides its contents. The box (class) has buttons (functions) on the outside that let you interact with what's inside, but you can't directly reach in and change things. The variables inside the class are usually marked as private so that they can't be accessed directly from outside the class. 

 For more detailed explaination please refer [Encapsulation](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Introduction/EncapsulationReadMe.md)
<br>
<br>


## [Inheritance](#inheritance)
 - Inheritance is the process by which object of one class acquire the properties of object of another class. 
 - Creating new class from existing one.
 - The news class Inherits the property of original class called derived class. The Original class will be called base class.

 For more detailed explaination please refer [Inheritance](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Introduction/InheritanceReadMe.md)
<br>
<br>


## [Polymorphism](#polymorphism)
 - It is the ability of a **single interface to have multiple forms**.
 - The same entity exhibits different behaviors.
 - There are two main types of polymorphism in C++:
   i) Compile-Time Polymorphism
   ii) Run-Time Polymorphism
<br>

i) **Compile-Time Polymorphism (Static Polymorphism)**:
The process where procedures are bound (linked) to the code to be executed at compile time is known as compile-time polymorphism. It is also known as early binding, static binding, or static linkage.

This is achieved in two ways:
 - Function Overloading
 - Operator Overloading
<br>

ii) **Run-Time Polymorphism (Dynamic Polymorphism)**:
 - Virtual Functions: Functions declared with the virtual keyword in a base class can be overridden in derived classes. The function to be invoked is determined at runtime based on the object type, enabling dynamic method dispatch.

 For more detailed explaination please refer [polymorphism](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Introduction/PolymorphismReadMe.md)
<br>
<br>



## [What is a Nested Class?](#what-is-a-nested-class)
 - A Nested class is a class defined inside another class. The nested class acts as a member of the outer class and has access to its private and protected members if needed.

For more detailed explaination please refer [Nested Class](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/OOPS%20Concepts/NestedClasses.md#what-is-a-nested-class)
<br>
<br>


## [Inline Functions](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/OOPS%20Concepts/InlineFunctions.md#inline-function-in-c)
 - The `inline` is a **keyword** used to suggest that the compiler should replace a function call with the actual function code to reduce function call overhead. This can improve performance, especially for small, frequently used functions.

For more details click [here](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/OOPS%20Concepts/InlineFunctions.md#inline-function-in-c)
<br>
<br>



## [Virtual](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/OOPS%20Concepts/Virtual.md#virtual-concept-in-c)
 - The `virtual` keyword is used to enable **runtime polymorphism** in object-oriented programming (OOP). It allows a derived class to override a base class method, ensuring that the correct function is called for an object, even when accessed through a base class pointer or reference.

For more details click [here](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/OOPS%20Concepts/Virtual.md#virtual-concept-in-c)
<br>
<br>


## [Access Specifier in C++](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/OOPS%20Concepts/AccessSpacifiersInCpp.md#access-specifiers-in-c)
 - Access specifiers in C++ define the **visibility** and **accessibility** of class members (variables and methods). They determine who can access the members of a class.

For more details click [here](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/OOPS%20Concepts/AccessSpacifiersInCpp.md#access-specifiers-in-c)
<br>
<br>



## [Constructor and Destructor](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/OOPS%20Concepts/ConstructorAndDestructor.md#constructor-and-destructor-in-c)
 - Constructors and destructors are special member functions of a class that are automatically invoked when an object is created or destroyed.

For more details click [here](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/OOPS%20Concepts/ConstructorAndDestructor.md#constructor-and-destructor-in-c)
<br>
<br>


---
