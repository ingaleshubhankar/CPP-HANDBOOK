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

```
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


### [Data Abstraction](#data-abstraction)
 - Abstraction means hiding the details of how something works and showing only what is necessary. It allows users to interact with a system without needing to understand its internal workings.

 - In programming, abstraction can be achieved by using access modifiers like the private keyword to hide certain parts of the code.

 For more detailed explaination please refer [Abstraction](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Introduction/AbstractionReadMe.md)
<br>


 ### [Encapsulation](#encapsulation)
 - The process of binding data and procedure into single unit is known as Encapsulation.
 - Encapsulation in C++ is the concept of bundling the data (variables) and the methods (functions) that operate on the data into a single unit, called a class. It also restricts direct access to some of the object's components, which is done to protect the integrity of the object.

 - Think of a class like a box that hides its contents. The box (class) has buttons (functions) on the outside that let you interact with what's inside, but you can't directly reach in and change things. The variables inside the class are usually marked as private so that they can't be accessed directly from outside the class. 
<br>
 For more detailed explaination please refer [Encapsulation](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Introduction/EncapsulationReadMe.md)


 