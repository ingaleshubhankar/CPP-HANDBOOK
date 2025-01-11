# [C++ Language Features](#c-language-features)

## [Data Types](#data-types)

###  [1. Basic Primitive Data Types](#1-basic-primitive-data-types)
These are the fundamental types provided by C++.

#### int (Integer)
 - Represents whole numbers without a decimal point.Used for whole numbers like 1, 2, 3, or -5.
 - Size: Typically 4 bytes (varies by system).
 - Range: It represents a signed 32-bit integer on most systems. range -2,147,483,648 to 2,147,483,647 (for 4 bytes).

Ex,
```
int age = 25;
```
<br>

#### float (Floating Point)
 - Represents floating-point numbers, which are numbers with a fractional part. Used for numbers with decimals like 3.14 or -0.01.
 - It represents a single-precision floating-point number, typically 32 bits.
 - Size: Typically 4 bytes.
 - Precision: Up to 7 decimal digits

Ex,
```
float height = 5.75f;
```
<br>

#### double (Double Precision Floating Point)
 - Represents double-precision floating-point numbers, allowing more precise fractional values. Like float, but with more precision for decimals (e.g., 3.14159). 
 - It represents a double-precision floating-point number, usually 64 bits.
 - Size: Typically 8 bytes.
 - Precision: Up to 15 decimal digits.

Ex,
```
double pi = 3.141592653589793;
```
<br>

#### char (Character)
 - Represents a single character from the ASCII set. Used to store a single character like 'a' or 'Z'. 
 - It represents a single byte (8 bits), which can store an ASCII character.
 - Size: 1 byte.
 - Range: -128 to 127 or 0 to 255 (depending on whether it's signed or unsigned).

Ex,
```
char grade = 'A';
```
<br>

#### bool (Boolean)
 - Represents a boolean value, which can be true or false. Used to store true or false. It typically represents a single bit of information (though it may take up more space in memory).
 - Size: Typically 1 byte.

Ex,
```
bool isPassed = true;
```
<br>
<br>


