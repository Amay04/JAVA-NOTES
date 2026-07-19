# Interface in Java

An **interface** is a blueprint of a class that defines a set of methods which a class must implement.

It is used to achieve **100% abstraction** (before Java 8) and supports **multiple inheritance** in Java.

Interfaces define **what a class should do**, but not **how it should do it**.

---

# Why Use Interfaces?

Interfaces are used to:

* Achieve abstraction.
* Support multiple inheritance.
* Define a common contract for different classes.
* Reduce code dependency.
* Improve flexibility and scalability.

---

# Syntax

```java
interface InterfaceName {

    void methodName();

}
```

A class implements an interface using the `implements` keyword.

```java
class ClassName implements InterfaceName {

}
```

---

# Simple Example

```java
interface Animal {

    void sound();

}

class Dog implements Animal {

    @Override
    public void sound() {

        System.out.println("Dog Barks");

    }

}

public class Main {

    public static void main(String[] args) {

        Dog d = new Dog();

        d.sound();

    }

}
```

### Output

```text
Dog Barks
```

---

# Rules of an Interface

* Declared using the `interface` keyword.
* Cannot create objects directly.
* Variables are automatically:

  * `public`
  * `static`
  * `final`
* Methods are automatically:

  * `public`
  * `abstract` (before Java 8)
* A class uses the `implements` keyword.
* A class can implement multiple interfaces.

---

# Interface Variables

```java
interface College {

    String NAME = "NMITD";

}
```

Java automatically treats it as:

```java
public static final String NAME = "NMITD";
```

These values cannot be modified.

---

# Multiple Inheritance Using Interfaces

Java does not support multiple inheritance through classes, but it allows it through interfaces.

```java
interface A {

    void display();

}

interface B {

    void show();

}

class Demo implements A, B {

    public void display() {

        System.out.println("Display");

    }

    public void show() {

        System.out.println("Show");

    }

}
```

This avoids the **Diamond Problem** found in some other languages.

---

# Default Methods (Java 8)

Java 8 introduced **default methods**.

A default method has an implementation inside the interface.

```java
interface Animal {

    default void sleep() {

        System.out.println("Sleeping");

    }

}
```

A class implementing the interface automatically inherits this method.

---

# Static Methods in Interface

Interfaces can contain static methods.

```java
interface MathUtil {

    static void display() {

        System.out.println("Static Method");

    }

}
```

Call using:

```java
MathUtil.display();
```

---

# Functional Interface

A functional interface contains **exactly one abstract method**.

It is mainly used with **Lambda Expressions**.

```java
@FunctionalInterface
interface Calculator {

    int add(int a, int b);

}
```

Examples:

* Runnable
* Callable
* Comparator

---

# Marker Interface

A marker interface contains **no methods or variables**.

It simply provides information to the JVM or compiler.

Example:

```java
interface Serializable {

}
```

Some commonly used marker interfaces:

* Serializable
* Cloneable
* Remote

---

# Interface vs Abstract Class

| Interface                           | Abstract Class                         |
| ----------------------------------- | -------------------------------------- |
| Uses `interface` keyword            | Uses `abstract` keyword                |
| Supports multiple inheritance       | Does not support multiple inheritance  |
| Variables are `public static final` | Variables can have any access modifier |
| Cannot have constructors            | Can have constructors                  |
| A class uses `implements`           | A class uses `extends`                 |

---

# Interface vs Class

| Interface                     | Class                                 |
| ----------------------------- | ------------------------------------- |
| Defines a contract            | Provides implementation               |
| Cannot create objects         | Can create objects                    |
| Uses `implements`             | Uses `extends` for inheritance        |
| Supports multiple inheritance | Does not support multiple inheritance |

---

# Advantages of Interfaces

* Achieves abstraction.
* Supports multiple inheritance.
* Promotes loose coupling.
* Improves flexibility.
* Makes applications easier to extend and maintain.

---

# Important Points

* Interfaces cannot be instantiated.
* A class can implement multiple interfaces.
* Interface variables are always `public static final`.
* Interface methods are `public`.
* Use `implements` to implement an interface.

---

# Common Mistakes

## Creating an Object of an Interface

❌ Incorrect

```java
interface Animal {

}

public class Main {

    public static void main(String[] args) {

        Animal a = new Animal();

    }

}
```

Interfaces cannot be instantiated.

---

## Forgetting to Implement Interface Methods

```java
interface Animal {

    void sound();

}

class Dog implements Animal {

}
```

The `Dog` class must implement `sound()` or be declared as `abstract`.

---

## Modifying Interface Variables

```java
interface Demo {

    int VALUE = 10;

}

public class Main {

    public static void main(String[] args) {

        Demo.VALUE = 20;

    }

}
```

This causes a compilation error because interface variables are `final`.

---

# Interview Notes

### What is an Interface?

An interface is a blueprint that defines methods a class must implement.

---

### Why Use Interfaces?

Interfaces provide abstraction, support multiple inheritance, and promote loose coupling.

---

### Can an Interface Have Constructors?

No.

Interfaces cannot have constructors because objects cannot be created from them.

---

### Can an Interface Extend Another Interface?

Yes.

```java
interface A {

}

interface B extends A {

}
```

---

### Difference Between `extends` and `implements`

| `extends`                   | `implements`                                |
| --------------------------- | ------------------------------------------- |
| Used for class inheritance  | Used to implement interfaces                |
| One class extends one class | One class can implement multiple interfaces |

---

### Why Does Java Support Multiple Inheritance Through Interfaces?

Interfaces contain method declarations rather than conflicting implementations, avoiding ambiguity and the Diamond Problem.

---

# Summary

* An interface defines a contract that implementing classes must follow.
* Interfaces help achieve abstraction and support multiple inheritance.
* A class implements an interface using the `implements` keyword.
* Interface variables are automatically `public static final`.
* Default and static methods were introduced in Java 8.
* Functional interfaces are widely used with lambda expressions.

