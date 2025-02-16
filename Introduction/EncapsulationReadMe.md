# Encapsulation
Encapsulation means binding the data (attributes) and the methods (functions) that operate on that data into a single unit, typically a class. Encapsulation in C++ is achieved through classes, which allow us to control access to data and protect it from unauthorized modifications.

## What is a class?
 - A class is a blueprint or template that defines the characteristics (attributes) and behaviors (methods) of an object.
 - Alternatively, a class can be described as a collection of data members (attributes) and methods (functions) that define the behavior of objects.


## Example
```cpp
#include <iostream>
using namespace std;

class BankAccount {
private:
    double balance;  // Private data member

public:
    // Constructor to initialize the balance
    BankAccount(double initialBalance) {
        balance = initialBalance;
    }

    // Public method to deposit money
    void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    // Public method to withdraw money
    void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
        }
    }

    // Public method to get the current balance
    double getBalance() {
        return balance;
    }
};

int main() {
    BankAccount account(1000);  // Create an account with $1000
    account.deposit(500);        // Deposit $500
    account.withdraw(200);      // Withdraw $200
    cout << "Current Balance: $" << account.getBalance() << endl;  // Output the balance

    return 0;
}
```

### Key Points:
 - Encapsulation is used here to protect the balance from direct access. It can only be modified or read via the public methods deposit(), withdraw(), and getBalance().
<br>

---