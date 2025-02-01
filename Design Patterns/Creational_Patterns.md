# Creational Patterns:-
This design pattern provides way of creating the objects while hiding creation logic. rather than than instatiating object directly using new operator.<br>

This gives flexibility to program, which object needs to create.

## 1) Singleton
The Singleton Pattern is a creational design pattern that ensures a class has only one instance and provides a global point of access to that instance. It is widely used in software development where only a single instance of a class is required throughout the application's lifecycle.<br>


|   Singleton    |
|:--------------:|
| <img src="singleton_design_pattern_img.png" alt="Centered Image" width="400"> |
<br>

Some components on our system only need to have single Instance.<br>

For ex,
Database Class Object. The DB that loads up from its constructor into program & gives info. Ince it is loaded, you dont really want more than one object.

Points to be note for making a Singleton Class,
 - Private Constructor.
 - Delete Copy Constructor & Copy Assignment Operator.
 - Static Object Creation & Static method Access.

### Example,

```
#include<iostream>
#include<cstdlib>
#include<time.h>

using namespace std;

class Random
{
    private:
        Random() {
            srand(time(NULL));
        }
    
    public:
        Random(Random& ref) = delete;
        Random& operator = (Random& ref) = delete;
        int getRandomNo(int limit=7)
        {
            int no=rand();
            no = no % limit;
            return no;
        }

        static Random& getInstance()
        {
            static Random instance;
            return instance;
        }
}; //class closed


int main()
{
    int RNo=Random::getInstance().getRandomNo();
    cout<<"Random Number :"<<RNo<<endl;
    return 0;
}

```

The above class & design is good and Idea example of Singleton Design Pattern, No problem till it face any dependency problem between Client and Service Implementation.<br>


## 2) Factory
