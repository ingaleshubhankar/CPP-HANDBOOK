# What is a Nested Class?
A nested class is a class defined inside another class. 
The nested class acts as a member of the outer class and has access to its private and protected members if needed.

## Why Use Nested Classes?
- To group logically related functionalities.
- To keep implementation details hidden from the outside world.
- To improve encapsulation.

## Syntax of a Nested Class
```cpp
#include <iostream>

class Outer {
public:
    class Inner {  // Nested class
    public:
        void show() {
            std::cout << "Inside Inner class\n";
        }
    };
};

int main() {
    Outer::Inner obj;  // Creating an object of the Inner class
    obj.show();  // Calling a method of the Inner class
    return 0;
}
```

**Output:**
```
Inside Inner class
```

## Types of Nested Classes
There are two main types:

### 1. Private Nested Class
If a nested class is declared private, it can only be accessed from within the outer class.

```cpp
#include <iostream>

class Outer {
private:
    class Inner {  // Private nested class
    public:
        void display() {
            std::cout << "Inside Private Inner class\n";
        }
    };

public:
    void accessInner() {
        Inner obj;  // Allowed because it's inside the Outer class
        obj.display();
    }
};

int main() {
    Outer outer;
    outer.accessInner();  // Allowed

    // Outer::Inner obj; // ❌ Not allowed (Inner is private)
    return 0;
}
```

**Output:**
```
Inside Private Inner class
```

### 2. Public Nested Class
If a nested class is public, it can be accessed outside the outer class.

```cpp
#include <iostream>

class Outer {
public:
    class Inner {  // Public nested class
    public:
        void show() {
            std::cout << "Inside Public Inner class\n";
        }
    };
};

int main() {
    Outer::Inner obj;  // Allowed because Inner is public
    obj.show();
    return 0;
}
```

**Output:**
```
Inside Public Inner class
```

## Nested Class Accessing Outer Class Members
A nested class does not have direct access to the outer class’s private members. But we can use friend functions to allow access.

```cpp
#include <iostream>

class Outer {
private:
    int data = 100;

public:
    class Inner {
    public:
        void show(Outer &obj) {  // Accessing outer class data using a reference
            std::cout << "Outer class data: " << obj.data << "\n";
        }
    };
};

int main() {
    Outer outer;
    Outer::Inner inner;
    inner.show(outer);  // Accessing Outer class private member
    return 0;
}
```

**Output:**
```
Outer class data: 100
```

## Key Takeaways
✅ A nested class is a class defined inside another class.<br>
✅ The nested class does not automatically have access to private members of the outer class.<br>
✅ If needed, the outer class can grant access to private members using friend functions.<br>
✅ A private nested class can only be accessed inside the outer class.<br>
✅ A public nested class can be accessed from outside using `Outer::Inner obj;`.<br>
<br>

## Why Does a Nested Class Not Automatically Have Access to Private Members of the Outer Class?
The reason nested classes do not automatically have access to private members of the outer class in C++ comes down to encapsulation and access control rules.
<br>


### 1. C++ Access Control Rules
In C++, private members of a class are only accessible:
- By the class itself.
- By friend classes or friend functions.

Even though the nested class is defined inside the outer class, it is still treated as a separate entity. This is why the nested class does not automatically get access to the private members of the outer class.

#### Example:
```cpp
#include <iostream>

class Outer {
private:
    int secret = 42;  // Private member

public:
    class Inner {
    public:
        void show(Outer &o) {
            // std::cout << "Secret: " << o.secret; // ❌ Compilation Error
        }
    };
};

int main() {
    Outer outer;
    Outer::Inner inner;
    // inner.show(outer); // Error: Inner has no access to Outer’s private members
    return 0;
}
```

🔴 **Error:** The nested class `Inner` cannot access `Outer::secret` because it is private.
<br>
<br>


### 2. Nested Class is a Separate Scope
Even though a nested class is declared inside an outer class, they are still two separate classes with separate scopes.
- The outer class can create objects of the nested class.
- The nested class does not belong to an instance of the outer class. It is an independent class, like any other.

In simple terms, just because a class is nested, it does not inherit access to private members of its enclosing class.
<br>
<br>

### 3. Allowing Access via Friend Functions
If you want the nested class to access private members, you can explicitly declare it as a friend.

✅ **Solution: Use `friend`**
<br>
<br>

## Conclusion
🔹 A `nested class` is still a separate class, even though it's inside another class.<br>
🔹 By default, nested classes **do NOT inherit** access to private members of the outer class.<br>
🔹 If needed, we can use `friend` to grant access to private members.<br>
<br>
<br>



