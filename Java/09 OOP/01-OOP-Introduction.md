# Object-Oriented Programming (OOP) in Java

Object-Oriented Programming (OOP) is a programming paradigm that organizes software around **objects** rather than functions or procedures. An object represents a real-world entity and contains both **data (attributes)** and **behavior (methods)**.

Java is a **purely object-oriented language** except for its primitive data types.

---

# Why OOP?

As software grows, managing code becomes difficult. OOP solves this problem by organizing code into reusable and maintainable objects.

### Advantages of OOP

* Improves code reusability.
* Makes code easier to maintain.
* Increases security through data hiding.
* Reduces code duplication.
* Makes debugging and testing easier.
* Models real-world entities effectively.

---

# Real-World Example

Consider a **Car**.

A car has:

### Properties (Attributes)

* Brand
* Color
* Model
* Speed

### Actions (Methods)

* Start()
* Stop()
* Accelerate()
* Brake()

In Java:

* **Car** → Class
* **My Car** → Object

---

# What is a Class?

A **class** is a blueprint or template used to create objects.

It defines:

* Variables (Data Members)
* Methods (Functions)

A class does not occupy memory until an object is created.

### Example

```java
class Student {

    String name;
    int age;

    void study() {
        System.out.println("Studying...");
    }

}
```

Here:

* `Student` is a class.
* `name` and `age` are attributes.
* `study()` is a method.

---

# What is an Object?

An **object** is an instance of a class.

Objects occupy memory and can access the variables and methods defined in the class.

### Example

```java
class Student {

    String name = "Amay";

    void display() {
        System.out.println(name);
    }

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        s.display();

    }

}
```

### Output

```text
Amay
```

---

# Class vs Object

| Class                  | Object               |
| ---------------------- | -------------------- |
| Blueprint              | Instance of a class  |
| Logical entity         | Physical entity      |
| Does not occupy memory | Occupies memory      |
| Used to create objects | Created from a class |

---

# Four Pillars of OOP

Object-Oriented Programming is based on four main principles.

## 1. Encapsulation

Encapsulation means **wrapping data and methods into a single unit (class)** and restricting direct access to the data.

Example:

```java
private int age;
```

Benefits:

* Data hiding
* Better security
* Controlled access

---

## 2. Inheritance

Inheritance allows one class to inherit properties and methods from another class.

Example:

```java
class Animal {

    void eat() {
        System.out.println("Eating...");
    }

}

class Dog extends Animal {

}
```

Benefits:

* Code reusability
* Reduced duplication
* Easier maintenance

---

## 3. Polymorphism

Polymorphism means **one interface, many forms**.

The same method can behave differently depending on the object.

Example:

```java
class Animal {

    void sound() {
        System.out.println("Animal Sound");
    }

}

class Dog extends Animal {

    void sound() {
        System.out.println("Bark");
    }

}
```

Benefits:

* Flexibility
* Easier code maintenance

---

## 4. Abstraction

Abstraction means **showing only essential details while hiding implementation details**.

Example:

```java
abstract class Vehicle {

    abstract void start();

}
```

Benefits:

* Reduces complexity
* Improves security
* Simplifies code

---

# OOP Features

* Class
* Object
* Constructor
* Method
* Encapsulation
* Inheritance
* Polymorphism
* Abstraction
* Interface
* Packages

---

# OOP vs Procedural Programming

| Procedural Programming               | Object-Oriented Programming       |
| ------------------------------------ | --------------------------------- |
| Focuses on functions                 | Focuses on objects                |
| Data and functions are separate      | Data and methods are together     |
| Less secure                          | More secure                       |
| Difficult to maintain large projects | Easier to maintain large projects |
| Less reusable                        | Highly reusable                   |

---

# Benefits of OOP

* Modular programming
* Better code organization
* Easy maintenance
* Code reusability
* Improved scalability
* Better security
* Easier debugging
* Supports real-world modeling

---

# Applications of OOP

OOP is widely used in:

* Banking Systems
* E-commerce Applications
* Hospital Management Systems
* Student Management Systems
* Mobile Applications
* Desktop Applications
* Game Development
* Enterprise Software

---

# Important Points

* Java is based on Object-Oriented Programming.
* Everything revolves around classes and objects.
* OOP helps write modular and reusable code.
* The four pillars of OOP are Encapsulation, Inheritance, Polymorphism, and Abstraction.
* Every object is created from a class.

---

# Common Mistakes

### Confusing Class and Object

❌ Incorrect Thinking

> A class is an object.

✔ Correct

* A **class** is a blueprint.
* An **object** is an instance created from that blueprint.

---

### Creating a Class but No Object

```java
class Student {

}
```

Without creating an object:

```java
Student s = new Student();
```

the class cannot be used to access its non-static members.

---

# Interview Notes

### What is OOP?

Object-Oriented Programming is a programming paradigm that organizes software around objects containing data and methods.

---

### What are the four pillars of OOP?

* Encapsulation
* Inheritance
* Polymorphism
* Abstraction

---

### Why is OOP important?

OOP improves code reusability, security, scalability, and maintainability while making programs easier to manage.

---

### Difference Between Class and Object

| Class                | Object                        |
| -------------------- | ----------------------------- |
| Blueprint            | Instance                      |
| Logical entity       | Physical entity               |
| No memory allocation | Memory allocated when created |

---

# Summary

* OOP is a programming paradigm based on objects.
* A class acts as a blueprint, while an object is an instance of that class.
* Java uses OOP to create modular and reusable applications.
* The four pillars of OOP are Encapsulation, Inheritance, Polymorphism, and Abstraction.
* Understanding OOP is essential for Java development and technical interviews.
