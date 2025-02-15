# [Structural Design Patterns in C++](#structural-design-patterns-in-c)
Structural patterns in C++ focus on how classes and objects are composed to form larger structures. These patterns help ensure that if one part of a system changes, the entire system doesn't need to be modified. Structural patterns emphasize class composition and interface inheritance to create flexible and efficient solutions.<br>


## **1. Adapter Pattern (Wrapper Pattern)**
The **Adapter pattern** allows incompatible interfaces to work together by providing a wrapper that converts one interface into another expected by clients.

### **When to Use?**
- When you have an existing class but its interface doesn’t match the requirements.
- When integrating legacy code with a new system.
- When working with third-party libraries that have a different API.

### **Example in C++**
Suppose you have a legacy class that provides temperature in **Fahrenheit**, but your new system expects temperature in **Celsius**.

#### **Code Implementation**
```cpp
#include <iostream>

// Legacy class (Adaptee)
class FahrenheitSensor {
public:
    float getTemperatureFahrenheit() {
        return 100.0;  // Some dummy temperature
    }
};

// Target interface (Celsius-based system)
class CelsiusSensor {
public:
    virtual float getTemperatureCelsius() = 0;
};

// Adapter class
class TemperatureAdapter : public CelsiusSensor {
private:
    FahrenheitSensor& fahrenheitSensor;

public:
    TemperatureAdapter(FahrenheitSensor& sensor) : fahrenheitSensor(sensor) {}

    float getTemperatureCelsius() override {
        return (fahrenheitSensor.getTemperatureFahrenheit() - 32) * 5.0 / 9.0;
    }
};

int main() {
    FahrenheitSensor oldSensor;
    TemperatureAdapter adapter(oldSensor);

    std::cout << "Temperature in Celsius: " << adapter.getTemperatureCelsius() << "°C\n";
    return 0;
}
```

### **Explanation**
- `FahrenheitSensor` is an **existing class** (Adaptee) that provides temperature in Fahrenheit.
- `CelsiusSensor` is the **desired interface**.
- `TemperatureAdapter` converts Fahrenheit to Celsius and **adapts the incompatible interface**.
- The client (main function) can now use `TemperatureAdapter` to work with `FahrenheitSensor` as if it were a `CelsiusSensor`.

---

## **2. Decorator Pattern**
The **Decorator pattern** allows adding behavior to objects dynamically **without modifying their structure**. It follows the **open-closed principle**, meaning you can extend functionality without changing the base class.

### **When to Use?**
- When you want to **add features to an object at runtime** without modifying its base class.
- When subclassing leads to too many subclasses for every feature combination.

### **Example in C++**
Suppose we have a **Coffee** class, and we want to dynamically add features like **Milk** and **Sugar** without modifying the base class.

#### **Code Implementation**
```cpp
#include <iostream>
#include <memory>

// Base Component
class Coffee {
public:
    virtual std::string getDescription() = 0;
    virtual double getCost() = 0;
    virtual ~Coffee() = default;
};

// Concrete Component
class SimpleCoffee : public Coffee {
public:
    std::string getDescription() override {
        return "Simple Coffee";
    }

    double getCost() override {
        return 50.0; // Base price
    }
};

// Decorator Base Class
class CoffeeDecorator : public Coffee {
protected:
    std::unique_ptr<Coffee> coffee; // Pointer to the wrapped object

public:
    CoffeeDecorator(std::unique_ptr<Coffee> c) : coffee(std::move(c)) {}

    std::string getDescription() override {
        return coffee->getDescription();
    }

    double getCost() override {
        return coffee->getCost();
    }
};

// Concrete Decorators
class Milk : public CoffeeDecorator {
public:
    Milk(std::unique_ptr<Coffee> c) : CoffeeDecorator(std::move(c)) {}

    std::string getDescription() override {
        return coffee->getDescription() + ", Milk";
    }

    double getCost() override {
        return coffee->getCost() + 10.0; // Extra charge for Milk
    }
};

class Sugar : public CoffeeDecorator {
public:
    Sugar(std::unique_ptr<Coffee> c) : CoffeeDecorator(std::move(c)) {}

    std::string getDescription() override {
        return coffee->getDescription() + ", Sugar";
    }

    double getCost() override {
        return coffee->getCost() + 5.0; // Extra charge for Sugar
    }
};

int main() {
    std::unique_ptr<Coffee> myCoffee = std::make_unique<SimpleCoffee>();
    myCoffee = std::make_unique<Milk>(std::move(myCoffee)); // Add Milk
    myCoffee = std::make_unique<Sugar>(std::move(myCoffee)); // Add Sugar

    std::cout << "Order: " << myCoffee->getDescription() << "\n";
    std::cout << "Total Cost: " << myCoffee->getCost() << " INR\n";

    return 0;
}
```

### **Explanation**
- `SimpleCoffee` is the base **concrete component**.
- `CoffeeDecorator` acts as a **base decorator** that wraps a `Coffee` object.
- `Milk` and `Sugar` are **concrete decorators** that extend functionality dynamically.
- The main function **chains multiple decorators** to enhance a `SimpleCoffee` object.

---

## **Key Takeaways**
| Pattern   | Purpose | Example |
|-----------|---------|---------|
| **Adapter** | Converts one interface into another to enable compatibility | Converting temperature units |
| **Decorator** | Dynamically adds behavior to objects without altering the base class | Adding milk & sugar to coffee |

These patterns make code **more flexible** and **extensible** while following **good design principles**.

