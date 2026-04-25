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




