# [Behavioral Design Patterns in C++](#behavioral-design-patterns-in-c)
Behavioral design patterns focus on how objects interact and communicate with each other while ensuring flexibility and maintainability. These patterns help define the flow of control between objects and promote loose coupling.


## **1. Observer Pattern**
The **Observer pattern** defines a **one-to-many dependency** between objects, ensuring that when one object changes state, all its dependents are notified automatically.

### **When to Use?**
- When multiple objects need to be informed about state changes of a subject.
- When implementing **event-driven programming**.
- When you need a publish-subscribe mechanism.

### **Example in C++**
Let's implement a simple **Weather Station** where multiple devices (observers) subscribe to updates.

#### **Code Implementation**
```cpp
#include <iostream>
#include <vector>
#include <memory>

// Observer Interface
class IObserver {
public:
    virtual void update(float temperature) = 0;
    virtual ~IObserver() = default;
};

// Subject Interface
class ISubject {
public:
    virtual void addObserver(std::shared_ptr<IObserver> observer) = 0;
    virtual void removeObserver(std::shared_ptr<IObserver> observer) = 0;
    virtual void notifyObservers() = 0;
    virtual ~ISubject() = default;
};

// Concrete Subject (Weather Station)
class WeatherStation : public ISubject {
private:
    std::vector<std::shared_ptr<IObserver>> observers;
    float temperature;

public:
    void setTemperature(float temp) {
        temperature = temp;
        notifyObservers();
    }

    void addObserver(std::shared_ptr<IObserver> observer) override {
        observers.push_back(observer);
    }

    void removeObserver(std::shared_ptr<IObserver> observer) override {
        observers.erase(std::remove(observers.begin(), observers.end(), observer), observers.end());
    }

    void notifyObservers() override {
        for (auto& observer : observers) {
            observer->update(temperature);
        }
    }
};

// Concrete Observer (Display Device)
class Display : public IObserver {
public:
    void update(float temperature) override {
        std::cout << "Temperature updated: " << temperature << "°C\n";
    }
};

int main() {
    auto weatherStation = std::make_shared<WeatherStation>();
    auto display1 = std::make_shared<Display>();
    auto display2 = std::make_shared<Display>();

    weatherStation->addObserver(display1);
    weatherStation->addObserver(display2);
    
    weatherStation->setTemperature(25.5);
    weatherStation->setTemperature(30.0);

    return 0;
}
```

### **Explanation**
- `WeatherStation` acts as a **subject** that maintains a list of observers.
- `Display` is an **observer** that gets notified when the temperature changes.
- When `setTemperature()` is called, all observers receive the updated value.

---

## **2. Strategy Pattern**
The **Strategy pattern** defines a **family of algorithms**, encapsulates each one, and makes them interchangeable. This allows the **algorithm to vary independently** from clients that use it.

### **When to Use?**
- When you have multiple algorithms for a specific task.
- When you want to **switch behavior dynamically** at runtime.
- When you want to **avoid using many conditionals** to determine behavior.

### **Example in C++**
Let's implement a **Payment System** where we can switch between different payment methods (Credit Card, PayPal).

#### **Code Implementation**
```cpp
#include <iostream>
#include <memory>

// Strategy Interface
class PaymentStrategy {
public:
    virtual void pay(int amount) = 0;
    virtual ~PaymentStrategy() = default;
};

// Concrete Strategies
class CreditCardPayment : public PaymentStrategy {
public:
    void pay(int amount) override {
        std::cout << "Paid " << amount << " using Credit Card.\n";
    }
};

class PayPalPayment : public PaymentStrategy {
public:
    void pay(int amount) override {
        std::cout << "Paid " << amount << " using PayPal.\n";
    }
};

// Context Class
class ShoppingCart {
private:
    std::unique_ptr<PaymentStrategy> paymentMethod;

public:
    void setPaymentMethod(std::unique_ptr<PaymentStrategy> method) {
        paymentMethod = std::move(method);
    }

    void checkout(int amount) {
        if (paymentMethod) {
            paymentMethod->pay(amount);
        } else {
            std::cout << "No payment method selected!\n";
        }
    }
};

int main() {
    ShoppingCart cart;

    cart.setPaymentMethod(std::make_unique<CreditCardPayment>());
    cart.checkout(500);

    cart.setPaymentMethod(std::make_unique<PayPalPayment>());
    cart.checkout(300);

    return 0;
}
```

### **Explanation**
- `PaymentStrategy` is the **interface** that defines a common payment method.
- `CreditCardPayment` and `PayPalPayment` are **concrete strategies**.
- `ShoppingCart` is the **context** that holds a strategy and allows switching between them dynamically.

---

## **Key Takeaways**
| Pattern   | Purpose | Example |
|-----------|---------|---------|
| **Observer** | Notifies multiple objects when a subject changes | Weather Station updates displays |
| **Strategy** | Encapsulates interchangeable algorithms | Different payment methods in a shopping cart |

These patterns help make code **more flexible**, **modular**, and **easy to maintain** by promoting reusable behaviors.
