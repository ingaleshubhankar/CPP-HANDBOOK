# Introduction
I’m not here to overwhelm you with a list of tools you must use. As long as you’ve got **a C++ compiler** and **an editor**, you’re **good to go**! Here, we’re diving straight into the core concepts, taking a **fresh perspective** that’s a bit different from the usual.<br>

I’m excited about this journey, and I’m sure you will be too once you explore the first few chapters. Let’s get started!
<br>
<br>

## CPP Introduction
 - C++ is an **Object-Oriented Programming** Language.<br>
 - Object-Priented Programming is **NOT** just a concept; it’s a **way of thinking.**<br>
 - We use object-oriented concepts to solve real-life problems by modeling them as objects.<br>
 - Smalltalk is considered the first object-oriented programming language.<br>
 - The concept of Classes in C++ was derived from Smalltalk, while the structural and syntactical approaches were borrowed from C.Because of this, C++ is often referred to as **"C with classes"**.<br>
 - **C++** is developed by **Bjarne Stroustrup**. Stroustrup was working on his Ph.D. in computer science at the University of Cambridge. He started the development of C++ in 1979 as an extension of the C programming language to support object-oriented programming (OOP) features.<br>
 - Initially, C++ was called "C with Classes.". Stroustrup introduced key concepts like **classes**, **objects**, and **inheritance** into the C language to enable better modularity and maintainability.<br>
 - The **first commercial release of C++** was in **1985**. Over time, it evolved to include additional features like templates, exceptions, and the Standard Template Library (STL), making it one of the most powerful and widely used programming languages today.<br>
 - C++ is generally used in **team development**.
 <br>

### Important THREE Points
Below are 3 points that need to be taken into consideration whenever you are asked to write a program in C++
<br>

1. Whether C++ is **applicable** or **NOT**.
2. **Which things are required** to **solve** the problem.
3. **How can** we solve the problem statements.
 <br>

### C++ Versions History
- The C++ has gone through several major versions since its inception, each version adding new features and improvements. The C++ is standardized in **1998 as C++98**, This is the first standardized version of C++, which was based on the original C++ language developed by Bjarne Stroustrup in the early 1980s.

 - In **2003 as C++03**, C++03 was a bug-fix release of C++98. It did not introduce any new features, but it fixed several ambiguities and inconsistencies present in the C++98 standard.

 - In 2007, The year 2007 is notable for the development of C++0x, which was an early working name for what would later become C++11. However, **C++0x was never formally released in 2007**.

 - In **2011 as C++11, C++11** was a major update to the C++ language. Introducing a wide range of new features like : Auto, nullptr, Lambda expressions, Range-based for loops, New smart pointers, etc.

 - In **2014 as C++14, C++14** was a smaller update compared to C++11. Focusing mostly on bug fixes, performance improvements, and small feature enhancements.

 - In **2017 as C++17**, C++17 added several new features and improvements.<br>
 Including Inline variables, Structured bindings, Filesystem library and more.

 - In **2020 as C++20**, C++20 introduced some of the most significant changes in the history of C++ like: Calendar and timezone library, type-safe string formatting and more.

 - In **2023 as C++23**, C++23 is the latest version, focusing on additional improvements and fixes to features introduced in C++20.<br>
 It focusing on library fixes and optimizations.
<br>

 ## The four pillars of Object-Oriented Programming
 1. [Abstraction](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Introduction/AbstractionReadMe.md)
 2. [Encapsulation](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Introduction/EncapsulationReadMe.md)
 3. [Inheritance](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Introduction/InheritanceReadMe.md)
 4. [Polymorphism](https://github.com/ingaleshubhankar/CPP-HANDBOOK/blob/main/Introduction/PolymorphismReadMe.md)
<br> 
<br>


## Problem Statement

### Procedural Way (Add & Sub)

```
#include<studio.h>

int Add(int No1, int No2)
{
	int Ans = 0;
	Ans = No1 + No2;
	return Ans;
}

int Sub(int No1, int No2)
{
	int Ans = 0;
	Ans = No1 - No2;
	return Ans;
}

int main()
{
	int Num1, Num2, Answer;
	printf("Enter 2 Numbers :");
	scanf("%d %d",&Num1, &Num2);
	
	Answer = Add(Num1,Num2);
	printf("Addition = %d",Answer);
	
	Answer = Sub(Num1,Num2);
	printf("Substraction = %d",Answer);
	
	return 0;
}
```

#### Note:
As it is Procedural approach, it should be invoked in sequence. If you want to perform same task again and again, We have to follow same procedure again & again.



### Object-Oriented Approach (Add & Sub)
```
#include<iostream>
using namespace std;
class Math
{
    private:
        int val1,val2;
    public:
        int ans;
        void Add();
        void Sub();
};

Math::Math(int a, int b)
{
    val1 = a;
    val2 = b;
}

void Math::Add()
{
    Ans = val1 + val2;
}

void Math::Sub()
{
    Ans = val1 - val2;
}

Math::~Math()
{
    //destructor
}

int main()
{
    Math obj1(100,20);
    Math obj2(10,10);

    obj1.Add();
    obj2.Sub();

    cout << "Addition is : " << obj1.Ans <<endl;
    cout << "Substraction is : " << obj2.Ans <<endl;
}
```


