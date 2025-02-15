# Stograge Classes
Think of C++ Storage Classes like different types of storage where variables and functions are kept. Each type of storage has specific rules about where the data is stored, how long it stays, and who can access it.

Storage classes in C++ primarily apply to **variables**, But some storage class specifiers can also be used with functions. However, not all storage classes are applicable to functions. Let's break it down:

## Storage Classes for Variables vs. Functions

| Storage Class  | Used with Variables? | Used with Functions? |
|--------------|------------------|-----------------|
| `auto`      | ✅ Yes | ❌ No (implied for local variables) |
| `static`    | ✅ Yes | ✅ Yes (makes function **local to file**) |
| `extern`    | ✅ Yes | ✅ Yes (makes function **available globally**) |
| `register`  | ✅ Yes (suggests CPU register storage) | ❌ No |
| `mutable`   | ✅ Yes (only in class members) | ❌ No |
<br>
<br>

## When you declare a variable in C++, its storage class defines:
 - **Where** it is stored (memory location).
 - **How long** it exists (lifetime).
 - **Who** can access it (scope/visibility).
 - What its **default value** is (if not initialized explicitly).
<br>
<br>


## C++ provides 6 different storage classes, which are as follows:
 1) auto Storage Class
 2) extern Storage Class
 3) static Storage Class
 4) register Storage Class
 5) mutable Storage Class
 6) thread_local Storage Class


### 1. auto Storage Class
The auto storage class is the default class of all the variables declared inside a block. The auto stands for automatic and all the local variables that are declared in a block automatically belong to this class.

**Properties** of auto Storage Class Objects
> **Scope:** Local
> **Default Value:** Garbage Value
> **Memory Location:** RAM
> **Lifetime:** Till the end of its scope


