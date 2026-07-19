# Abstraction in Java

Abstraction is one of the four pillars of Object-Oriented Programming (OOP). It is the process of **hiding implementation details** and showing only the essential features to the user.

In Java, abstraction is mainly achieved using:

* Abstract Classes
* Interfaces

---

# Why Use Abstraction?

Abstraction helps to:

* Hide unnecessary implementation details.
* Reduce code complexity.
* Improve security.
* Focus on what an object does rather than how it does it.
* Improve maintainability.

---

# Real-World Example

Consider a **Car**.

When you drive a car, you use:

* Steering Wheel
* Accelerator
* Brake

You don't need to know how the engine works internally.

This is abstraction—you interact with the essential features without knowing the internal implementation.

---

# Abstract Class

An **abstract class** is a class declared using the `abstract` keyword.

* It cannot be instantiated (you cannot create its object).
* It can contain both abstract and concrete methods.
* It can also contain constructors and variables.

### Syntax

```java
abstract class ClassName {

}
```

---

# Abstract Method

An abstract method is a method without a body. It is declared using the `abstract` keyword.

### Syntax

```java
abstract void methodName();
```

A child class **must** implement all abstract methods unless the child class is also abstract.

---

# Example

```java
abstract class Animal {

    abstract void sound();

}

class Dog extends Animal {

    @Override
    void sound() {

        System.out.println("Dog Barks");

    }

}

public class Main {

    public static void main(String[] args) {

        Animal a = new Dog();

        a.sound();

    }

}
```

### Output

```text
Dog Barks
```

---

# Concrete Method in Abstract Class

An abstract class can contain normal (concrete) methods.

```java
abstract class Animal {

    void sleep() {

        System.out.println("Sleeping");

    }

}
```

The child class automatically inherits this method.

---

# Constructor in Abstract Class

An abstract class can have constructors.

```java
abstract class Animal {

    Animal() {

        System.out.println("Animal Constructor");

    }

}
```

The constructor is executed when a child object is created.

---

# Rules of Abstract Classes

* Declared using the `abstract` keyword.
* Cannot be instantiated.
* Can contain abstract and concrete methods.
* Can have constructors.
* Can have variables.
* Can contain static methods.
* A subclass must implement all abstract methods.

---

# Advantages of Abstraction

* Hides implementation details.
* Reduces complexity.
* Improves code readability.
* Makes programs easier to maintain.
* Encourages code reuse.

---

# Abstract Class vs Concrete Class

| Abstract Class               | Concrete Class                  |
| ---------------------------- | ------------------------------- |
| Cannot create objects        | Can create objects              |
| May contain abstract methods | Cannot contain abstract methods |
| Used as a blueprint          | Used for implementation         |

---

# Abstraction vs Encapsulation

| Abstraction                                    | Encapsulation                                        |
| ---------------------------------------------- | ---------------------------------------------------- |
| Hides implementation                           | Hides data                                           |
| Focuses on what an object does                 | Focuses on protecting data                           |
| Achieved using abstract classes and interfaces | Achieved using private variables and getters/setters |

---

# Important Points

* Abstract classes cannot be instantiated.
* Abstract methods do not have a body.
* Child classes must implement abstract methods.
* Abstract classes can have constructors and concrete methods.
* Abstraction focuses on hiding implementation details.

---

# Common Mistakes

## Creating an Object of an Abstract Class

❌ Incorrect

```java
abstract class Animal {

}

public class Main {

    public static void main(String[] args) {

        Animal a = new Animal();

    }

}
```

This causes a compilation error.

✔ Correct

```java
Animal a = new Dog();
```

---

## Forgetting to Implement an Abstract Method

```java
abstract class Animal {

    abstract void sound();

}

class Dog extends Animal {

}
```

The `Dog` class must implement the `sound()` method or be declared as `abstract`.

---

## Declaring an Abstract Method in a Non-Abstract Class

❌ Incorrect

```java
class Animal {

    abstract void sound();

}
```

A class containing an abstract method must itself be declared as `abstract`.

---

# Interview Notes

### What is Abstraction?

Abstraction is the process of hiding implementation details while exposing only the essential features.

---

### How is Abstraction Achieved in Java?

Using:

* Abstract Classes
* Interfaces

---

### Can We Create an Object of an Abstract Class?

No.

An abstract class cannot be instantiated.

---

### Can an Abstract Class Have a Constructor?

Yes.

The constructor is called when a child class object is created.

---

### Can an Abstract Class Have Static Methods?

Yes.

Static methods are allowed inside abstract classes.

---

# Summary

* Abstraction is one of the four pillars of OOP.
* It hides implementation details and exposes only the necessary functionality.
* Java achieves abstraction using abstract classes and interfaces.
* Abstract classes can contain abstract methods, concrete methods, constructors, and variables.
* Child classes must implement all abstract methods unless they are also abstract.
