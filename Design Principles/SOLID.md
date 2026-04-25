# [SOLID](#solid)

SOLID refered as 5 Principles of the Object Oriented Design. SOLID focus on class level object oriented design.

🔹**S** — Single Responsibility Principle (SRP) — <i> A class should have one reason to change.</i>
<br>
🔹**O** — Open/Closed Principle (OCP) — <i> Software should be open for extension but closed for modification.</i>
<br>
🔹**L** — Liskov Substitution Principle (LSP) — <i> A subtype should behave in a way that doesn’t break expectations of the base type.</i>
<br>
🔹**I** — Interface Segregation Principle (ISP) — <i> Don’t force a class to implement methods it doesn’t need.</i>
<br>
🔹**D** — Dependency Inversion Principle (DIP) — <i> Depend on abstractions, not concrete implementations.</i>
<br>
<br>

---

## [SOLID In Detail](#solid-in-detail)

### [1. Single Responsibility Principle (SRP)](#1-single-responsibility-principle-srp)

**Definition:** 
A class should have only one reason to change.

**Explanation:**
Each class should focus on a single responsibility. When a class handles multiple concerns, changes in one area can break another.

**Why it matters:**
 - Easier to maintain
 - Better readability
 - Reduced side effects


**Example:**<br>
Instead of one class handling both business logic + logging, separate them.
<br>
<br>


### [2. Open/Closed Principle (OCP)](#2-openclosed-principle-ocp)

**Definition:**
Software should be open for extension but closed for modification.

**Explanation:**
You should be able to add new functionality without modifying existing code.

**Why it matters:**
 - Prevents breaking existing code
 - Encourages extensibility

**Example:**<br>
Adding a new payment type without modifying existing payment logic.
<br>
<br>


### [3. Liskov Substitution Principle (LSP)](#3-liskov-substitution-principle-lsp)

**Definition:**
A subtype should behave in a way that doesn’t break expectations of the base type.

**Explanation:**
If a class extends another, it should be usable wherever the base class is expected—without surprises.

**Why it matters:**
 - Ensures reliable inheritance
 - Prevents unexpected runtime issues

**Example:**<br>
If a “Duck” suddenly needs batteries to quack, it violates expectations.
<br>
<br>


### [4. Interface Segregation Principle (ISP)](#4-interface-segregation-principle-isp)

**Definition:**
Don’t force a class to implement methods it doesn’t need.

**Explanation:**
Large interfaces should be split into smaller, specific ones.

**Why it matters:**
 - Avoids unnecessary implementation
 - Keeps classes focused

**Example:**<br>
Instead of one large interface, create smaller role-based interfaces.
<br>
<br>

### [5. Dependency Inversion Principle (DIP)](#5-dependency-inversion-principle-dip)

**Definition:**
Depend on abstractions, not concrete implementations.

**Explanation:**
High-level modules should not depend on low-level modules. Both should depend on abstractions.

**Why it matters:**
 - Makes code flexible
 - Easier to test and extend

**Example:**<br>
Using interfaces instead of directly instantiating classes.
<br>
<br>

