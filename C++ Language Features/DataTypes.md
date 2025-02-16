## [Data Types](#data-types)

###  [1. Basic Primitive Data Types](#1-basic-primitive-data-types)
These are the fundamental types provided by C++.

#### int (Integer)
 - Represents whole numbers without a decimal point.Used for whole numbers like 1, 2, 3, or -5.
 - Size: Typically 4 bytes (varies by system).
 - Range: It represents a signed 32-bit integer on most systems. range -2,147,483,648 to 2,147,483,647 (for 4 bytes).

Example,
```
int age = 25;
```
<br>

#### float (Floating Point)
 - Represents floating-point numbers, which are numbers with a fractional part. Used for numbers with decimals like 3.14 or -0.01.
 - It represents a single-precision floating-point number, typically 32 bits.
 - Size: Typically 4 bytes.
 - Precision: Up to 7 decimal digits

Example,
```
float height = 5.75f;
```
<br>

#### double (Double Precision Floating Point)
 - Represents double-precision floating-point numbers, allowing more precise fractional values. Like float, but with more precision for decimals (e.g., 3.14159). 
 - It represents a double-precision floating-point number, usually 64 bits.
 - Size: Typically 8 bytes.
 - Precision: Up to 15 decimal digits.

Example,
```
double pi = 3.141592653589793;
```
<br>

#### char (Character)
 - Represents a single character from the ASCII set. Used to store a single character like 'a' or 'Z'. 
 - It represents a single byte (8 bits), which can store an ASCII character.
 - Size: 1 byte.
 - Range: -128 to 127 or 0 to 255 (depending on whether it's signed or unsigned).

Example,
```
char grade = 'A';
```
<br>

#### bool (Boolean)
 - Represents a boolean value, which can be true or false. Used to store true or false. It typically represents a single bit of information (though it may take up more space in memory).
 - Size: Typically 1 byte.

Example,
```
bool isPassed = true;
```
<br>
<br>


###  [2. Derived Data Types](#2-derived-data-types)

These are built from the basic data types.


#### Arrays
 - A collection of items of the same type (e.g., an array of integers). It is a contiguous block of memory where each element can be accessed via its index.
 - Array is collection of elements of the same type, stored in contiguous memory locations.

Syntax:
```
type arrayName[size];
```
<br>

Example,
```
int numbers[5] = {1, 2, 3, 4, 5};
```
<br>


#### Pointers
 - Variables that store memory addresses.They are used to store the address of another variable and provide the ability to perform low-level memory management. 
 - A variable that stores the memory address of another variable.


Syntax:
```
type* pointerName;
```
<br>

Example,
```
int x = 10;
int* ptr = &x;
```
<br>


#### References
 - An alias for another variable. It is a reference to an existing variable, allowing indirect access to it without using pointers.
 - An alias for another variable, providing another name for the same memory location.

Syntax:
```
type& referenceName = originalVariable;
```
<br>

Example,
```
int y = 20;
int& ref = y;
```
<br>
<br>


### [3. User-Defined Data Types](#3-user-defined-data-types)

You can define your own data types in C++.

#### Structures (struct)
 - A group of related variables under one name. It is a collection of variables (of different types) that are grouped together, similar to a record in a database. 
 - Similar to a class but with public members by default.

Example,
```
struct Point {
    int x, y;
};
```
<br>


#### Classes (class)
 - A blueprint for creating objects that encapsulate data and functions. Like a structure but with added features for Object-Oriented Programming (OOP).
 - It defines a data structure that contains both data members (variables) and member functions (methods) to operate on the data.

Example,
```
class Car {
    public:
        string brand;
        int year;
};
```
<br>


#### Enumerations (enum)
 - A user-defined type consisting of a set of named integral constants. Used to define a set of named integral constants.
 - An enumeration defines a type that can take one of a set of predefined values, each of which is a constant.

Example,
```
enum Color { RED, GREEN, BLUE };
```
<br>


#### Typedefs and Aliases
 - Used to give a new name to an existing type. typedef and using keywords are used to create type aliases for easier code readability and maintainability.
 - Used to create a new name (alias) for an existing type.

Example,
```
typedef unsigned int uint;
using uint = unsigned int;
```
<br>
<br>


### [4. Abstract or Void Data Type](#4-abstract-or-void-data-type)

#### void
Used for functions that do not return a value or to specify a generic pointer (void*).

Example,
```
void printMessage() {
    cout << "Hello, World!";
}
```

