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

### Change pressure increases

New requirement:

Support File, DB, API storage
```cpp
void save(const Card& c, string type) {
    if(type == "file") { }
    else if(type == "db") { }
    else if(type == "api") { }
}
```

What’s happening here?
Every new storage → modify code
Violates OCP
Change pressure increases

OCP forces abstraction

To avoid modifying code:

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

Add new type → extend class
No modification required

✔ OCP satisfied


Creation problem appears

Now question becomes:

Who creates the correct storage?


This is where pattern emerges

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

Design principles like **SRP** and **OCP** don’t give solutions.<br>
They create **constraints.**, And constraints create **pressure**.
<br>

Patterns are not the starting point.
They are what we recognize after solving the problem well.

---