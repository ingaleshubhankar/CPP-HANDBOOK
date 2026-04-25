# [Principle To Pattern With Example](#principle-to-pattern-with-example)


## [Where Patterns Come From](#where-patterns-come-from)

Let’s not start with patterns.<br>
Let’s start with a simple example.

**A simple design:**
```cpp
class Card {
    long cardNo;
    char type;

public:
    void save() {
        // save to file
    }
};
```
In the first glance it looks fine. Basically We have a Card & it knows how to save itself.
<br>

This class has **two reasons** to change:
 - Card structure changes
 - Storage mechanism changes
<br>

And <i>SRP violation</i><br>
**"A Class should have one one Reason to change"**
<br>

If the saving logic changes, the <i>Card</i> class should NOT be affected. If a single class has two reasons to change, **its responsibilities should be split into separate classes**. Otherwise, a change in one area may unintentionally impact another. To prevent this, we follow the **Single Responsibility Principle (SRP)**.<br>

We solved it as follows,<br>

**Fix (SRP applied)**
```cpp
class Card {
    long cardNo;
    char type;
};

class CardSaver {
public:
    void save(const Card& c);
};
```
Now:
 - Card → data responsibility
 - CardSaver → storage responsibility

✔ Clean separation<br>
❗ No pattern yet


### ❗Change pressure increases 

New requirement is we need to support File, DB, API storage. So basic implementation will look like this,
```cpp
void save(const Card& c, string type) {
    if(type == "file") { }
    else if(type == "db") { }
    else if(type == "api") { }
}
```
Which is **NOT enough**. Because every new storage the code gets modifed. And it **Violates Open Close Principle (OCP)**<br>

The Open/Closed Principle (OCP) promotes the use of abstraction. It states that a class should be open for extension but closed for modification.<br>

This means that new functionality should be added with **minimal or no changes** to the **existing code**. Instead of modifying already tested and stable code, we extend the system by introducing new implementations.<br>

This is typically achieved through abstraction, where behavior is defined using interfaces or base classes, allowing new features to be added without altering existing logic. <br>

**The OCP applied as follows,**
```cpp
class CardStorage {
public:
    virtual void save(const Card& c) = 0;
};
```

```cpp
class FileStorage : public CardStorage { ... };
class DBStorage   : public CardStorage { ... };
```

Now:
 - Add new type → extend class
 - No modification required

✔ OCP satisfied <br>

NOW, Who creates the correct storage?
```cpp
class StorageFactory {
public:
    static CardStorage* create(string type) {
        if(type == "file") return new FileStorage();
        if(type == "db")   return new DBStorage();
        return nullptr;
    }
};
```

**Factory appears*
<br>

And it applied as follows,
```cpp

class CardSaver {
    CardStorage* storage;

public:
    CardSaver(CardStorage* s) : storage(s) {}

    void save(const Card& c) {
        storage->save(c);
    }
};

```

OCP is NOT about Inheritance.<br>
OCP is about Polymorphism over conditionals.

Design principles like **SRP** and **OCP** don’t give solutions.<br>
They create **constraints.**, And constraints create **pressure**.
<br>

Patterns are not the starting point.
They are what we recognize after solving the problem well.

---