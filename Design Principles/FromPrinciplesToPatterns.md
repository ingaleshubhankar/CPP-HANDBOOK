# [Principle To Pattern With Example](#principle-to-pattern-with-example)


## [Where Patterns Come From](#where-patterns-come-from)

Let’s not start with patterns.<br>
Let’s start with a simple example.

A simple design

```
class Card {
    long cardNo;
    char type;

public:
    void save() {
        // save to file
    }
};
```
Looks fine. We have a Card, and it knows how to save itself.
<br>

This class has two reasons to change:<br>
 - Card structure changes
 - Storage mechanism changes

And <i>SRP violation</i><br>
**"A Class should have one one Reason to change"**
<br>

**Fix (SRP applied)**
```
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
<br>
✔ Clean separation
❗ No pattern yet



Design principles like **SRP** and **OCP** don’t give solutions.<br>
They create **constraints.**, And constraints create **pressure**.
<br>
