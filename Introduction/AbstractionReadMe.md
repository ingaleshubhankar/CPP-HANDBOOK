# Abstraction
Abstraction means hiding the details of how something works and showing only what is necessary. It allows users to interact with a system without needing to understand its internal workings.

In programming, abstraction can be achieved by using access modifiers like the `private` keyword to hide certain parts of the code.

There are two types of abstraction:
 - **Data Abstraction**: Hides the details of how data is stored and managed, showing only what is necessary.
 - **Method Abstraction**: Hides the internal logic of methods and shows only what they do


# Abstraction in C++  

This example demonstrates **abstraction** in C++ using a single class. It includes:  
- Abstract data (private member)  
- Abstract method (public member function)  

## Code Example  

```cpp
#include <iostream>
using namespace std;

class Employee {
private:
    // Abstract data (hidden from the user)
    int salary;

public:
    // Constructor to initialize salary
    Employee(int s) : salary(s) {}

    // Abstract method to access data
    void displaySalary() {
        cout << "Salary: " << salary << endl;
    }
};

int main() {
    Employee emp(50000); // Create an object of Employee
    emp.displaySalary(); // Access abstracted data through the method
    return 0;
}
```

### Explanation
 - Abstract Data: The salary variable is private, so it is hidden from external access.
 - Abstract Method: The displaySalary() method allows controlled access to the salary variable.


### Output
```
    Salary: 50000
```

### Key Points
 - Abstraction hides implementation details while exposing essential functionality.
 - In this example, the salary is hidden, and the user interacts with it only through the displaySalary() method.
 