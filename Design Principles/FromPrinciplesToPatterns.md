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
In the first glance it looks fine. Basically We have a Card & it knows how to save itself.
<br>

This class has two reasons to change:
 - Card structure changes
 - Storage mechanism changes
<br>

And <i>SRP violation</i><br>
**"A Class should have one one Reason to change"**
<br>

If Saving logic changes, Card should NOT change. If you have 2 reasons to change for same class then we have to split the functionality into two classes. because in future if we have to make changes in one area that might affect other area. So prevent that we should follow the SRP.<br>

We solved it as follows,<br>

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
