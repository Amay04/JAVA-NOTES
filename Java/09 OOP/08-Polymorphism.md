# Polymorphism in Java

Polymorphism is one of the four pillars of Object-Oriented Programming (OOP). The word **Polymorphism** comes from the Greek words:

* **Poly** → Many
* **Morph** → Forms

It means **one interface, many forms**. The same method or object can behave differently depending on the situation.

---

# Why Use Polymorphism?

Polymorphism makes programs more flexible and reusable.

It helps to:

* Write generic code.
* Reduce code duplication.
* Improve maintainability.
* Achieve runtime flexibility.

---

# Types of Polymorphism

Java supports two types of polymorphism:

1. Compile-Time Polymorphism (Method Overloading)
2. Runtime Polymorphism (Method Overriding)

---

# 1. Compile-Time Polymorphism

Compile-time polymorphism is achieved through **Method Overloading**.

The compiler decides which method to call based on the method signature.

### Example

```java
class Calculator {

    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }

}

public class Main {

    public static void main(String[] args) {

        Calculator c = new Calculator();

        System.out.println(c.add(10, 20));
        System.out.println(c.add(10, 20, 30));

    }

}
```

### Output

```text
30
60
```

---

# Rules for Method Overloading

Methods must differ in:

* Number of parameters
* Type of parameters
* Order of parameters

Changing only the return type is **not allowed**.

❌ Incorrect

```java
int add() { }

double add() { }
```

---

# 2. Runtime Polymorphism

Runtime polymorphism is achieved through **Method Overriding**.

The JVM decides which method to execute at runtime based on the actual object.

### Example

```java
class Animal {

    void sound() {
        System.out.println("Animal Sound");
    }

}

class Dog extends Animal {

    @Override
    void sound() {
        System.out.println("Bark");
    }

}

public class Main {

    public static void main(String[] args) {

        Animal obj = new Dog();

        obj.sound();

    }

}
```

### Output

```text
Bark
```

Although the reference type is `Animal`, the object type is `Dog`, so the overridden method is executed.

---

# Dynamic Method Dispatch

Dynamic Method Dispatch is the mechanism through which Java decides at runtime which overridden method should be executed.

```java
Animal a = new Dog();

a.sound();
```

The JVM checks the **actual object type**, not the reference type.

---

# Upcasting

Upcasting means converting a child object into a parent reference.

```java
Animal a = new Dog();
```

Advantages:

* Supports runtime polymorphism.
* Makes code more flexible.

---

# Downcasting

Downcasting means converting a parent reference back to a child reference.

```java
Animal a = new Dog();

Dog d = (Dog) a;
```

Downcasting requires explicit type casting.

---

# `instanceof` Operator

The `instanceof` operator checks whether an object belongs to a particular class.

### Example

```java
Animal a = new Dog();

System.out.println(a instanceof Dog);
```

### Output

```text
true
```

---

# Method Overloading vs Method Overriding

| Method Overloading   | Method Overriding             |
| -------------------- | ----------------------------- |
| Same class           | Parent and child class        |
| Compile-time         | Runtime                       |
| Different parameters | Same parameters               |
| Improves readability | Supports runtime polymorphism |

---

# Advantages of Polymorphism

* Improves code flexibility.
* Promotes code reuse.
* Makes programs easier to maintain.
* Supports dynamic behavior.
* Reduces code duplication.

---

# Important Points

* Polymorphism means one interface, many forms.
* Method Overloading provides compile-time polymorphism.
* Method Overriding provides runtime polymorphism.
* Runtime polymorphism works through inheritance.
* Dynamic Method Dispatch happens at runtime.

---

# Common Mistakes

## Changing Only the Return Type

❌ Incorrect

```java
int add() { }

double add() { }
```

This is not valid method overloading.

---

## Forgetting Inheritance

Method overriding requires inheritance.

```java
class A {

    void display() { }

}

class B {

    void display() { }

}
```

This is **not** method overriding because `B` does not extend `A`.

---

## Accessing Child-Specific Methods

```java
Animal a = new Dog();

a.bark();
```

This causes a compilation error because the reference type is `Animal`.

Correct:

```java
Dog d = (Dog) a;

d.bark();
```

---

# Interview Notes

### What is Polymorphism?

Polymorphism allows the same method or object to behave differently in different situations.

---

### How Many Types of Polymorphism Does Java Support?

* Compile-Time Polymorphism
* Runtime Polymorphism

---

### Which Feature Provides Compile-Time Polymorphism?

Method Overloading.

---

### Which Feature Provides Runtime Polymorphism?

Method Overriding.

---

### What is Dynamic Method Dispatch?

It is the mechanism through which the JVM selects the overridden method at runtime based on the actual object.

---

### Can Static Methods Be Overridden?

No.

Static methods are hidden, not overridden.

---

# Summary

* Polymorphism means **one interface, many forms**.
* Java supports compile-time and runtime polymorphism.
* Method Overloading is resolved by the compiler.
* Method Overriding is resolved by the JVM at runtime.
* Dynamic Method Dispatch enables runtime polymorphism.
* Upcasting and Downcasting are commonly used with polymorphism.
