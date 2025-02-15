# Types of Recursion

## 1. [Head Recursion]()
Head recursion is special case of recursion. where first operation of function is recurive call.

### Example,
Show Head Recursion with the example of `Factorical Number`.
```cpp

int fact(int No, int result)
{
    if(No==1)
        return result; //Termination Condition
    else
        return fact(No-1,result*No); //recursive call No-1
}

```




## 2. [Tail Recursion]()
Tail recursion is special case of recursion. where last operation of the function is recursive call.

### Example,
Show Tail Recursion with the example of `Factorical Number`.
```cpp

int fact(int No, int result)
{
    if(No==1)
        return result; //Termination Condition
    else
        return fact(No-1,result*No); //recursive call No-1
}

```

