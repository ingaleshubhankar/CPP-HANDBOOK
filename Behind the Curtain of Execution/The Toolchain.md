# [The ToolChain](#the-toolchain)
Imagine you have a brilliant idea, and you decide to bring it to life with a C++ program. You open your favorite text editor, type out a simple program to greet the world, and save it with the .cpp extension. But have you ever wondered what happens behind the scenes to turn that plain text into a running application?

Let me take you on a journey through the toolchain that makes it all possible. Lets first discuss the components of the toolchain and then we will see stepwise description of execution.

 - A Toolchain is the set of Programming Tools that are used to create a softwares.
 - The Tools are used in a chain, So that the output of each tool becomes input for the next tool.

## [Components of the Toolchain](#components-of-the-toolchain)

### [Editor](#editor)
 ✓ Editor is program in which we can write our code and edit that code.
 <br>
 ✓ Gedit, kwrite are the example of editors.

#### [Example](#example)
```
//Header file inclusion
#include<stdio.h>
//Macro definition
#define MAX 10

int Add(int No1, int No2)
{
    //Local variable
    int Ans;

    Ans = No1 + No2 + MAX;
    printf("Addition of Two Numbers is %d",Ans);
    return Ans;
}
```
<br>

### [Preprocessor](#preprocessor)
 ✓ The Preprocessor provides the ability for the inclusion of the header files, macro expansion, conditional compilation and line control.
<br>
 ✓ Preprocessor take lines beginnering with `#` as directives. Because it knows nothing about the underlying language.
<br>
 ✓ After Preprocessing it will give the expanded code as a output having extention **.i**.
<br>
 ✓ Expanded output given by preprocessor is in human understandable format.
<br>

## [Stepwise execution of Toolchain](#stepwise-execution-of-toolchain)



