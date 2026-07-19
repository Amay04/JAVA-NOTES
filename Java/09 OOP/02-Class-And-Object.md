# Class and Object in Java

Classes and objects are the foundation of Object-Oriented Programming (OOP). Every Java program is built around classes, and objects are created from these classes.

---

# What is a Class?

A **class** is a blueprint or template used to create objects.

It defines:

* Data (Variables)
* Behavior (Methods)

A class itself does not occupy memory. Memory is allocated only when an object of the class is created.

### Syntax

```java
class ClassName {

    // Variables

    // Methods

}
```

### Example

```java
class Student {

    String name;
    int age;

    void display() {
        System.out.println("Student Details");
    }

}
```

In the above example:

* `Student` is the class.
* `name` and `age` are instance variables.
* `display()` is a method.

---

# What is an Object?

An **object** is an instance of a class.

An object occupies memory and can access the variables and methods defined in the class.

### Syntax

```java
ClassName objectName = new ClassName();
```

### Example

```java
Student s = new Student();
```

Here:

* `Student` → Class Name
* `s` → Object Reference
* `new` → Allocates memory for the object
* `Student()` → Constructor

---

# Creating and Using an Object

```java
class Student {

    String name = "Amay";
    int age = 22;

    void display() {

        System.out.println(name);
        System.out.println(age);

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
22
```

---

# Accessing Variables

Object variables are accessed using the **dot (`.`) operator**.

### Example

```java
class Student {

    String name = "Rahul";

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        System.out.println(s.name);

    }

}
```

### Output

```text
Rahul
```

---

# Accessing Methods

Methods are also accessed using the **dot (`.`) operator**.

```java
class Student {

    void study() {

        System.out.println("Studying Java");

    }

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        s.study();

    }

}
```

### Output

```text
Studying Java
```

---

# Creating Multiple Objects

A class can have multiple objects.

```java
class Student {

    String name;

}

public class Main {

    public static void main(String[] args) {

        Student s1 = new Student();
        Student s2 = new Student();

        s1.name = "Amay";
        s2.name = "Rahul";

        System.out.println(s1.name);
        System.out.println(s2.name);

    }

}
```

### Output

```text
Amay
Rahul
```

Each object has its own copy of instance variables.

---

# Object Reference

A variable that stores the address of an object is called an **object reference**.

```java
Student s = new Student();
```

Here:

* `Student` → Class
* `s` → Object Reference
* `new Student()` → Object

---

# Memory Representation

When an object is created:

```java
Student s = new Student();
```

Memory is allocated in the **Heap Memory**, and the reference variable stores the object's address.

```text
Stack Memory               Heap Memory

+---------+                +----------------+
| s ------|--------------->| Student Object |
+---------+                | name           |
                            | age            |
                            +----------------+
```

---

# Anonymous Object

An object without a reference variable is called an **anonymous object**.

```java
new Student().display();
```

Anonymous objects are generally used when the object is needed only once.

---

# Real-Life Example

Consider a **Car**.

### Class

```text
Car
```

Properties:

* Brand
* Model
* Color
* Speed

Methods:

* Start()
* Stop()
* Brake()

### Objects

```text
Car car1 = new Car();
Car car2 = new Car();
```

Each car has different values but belongs to the same class.

---

# Important Points

* A class is a blueprint.
* An object is an instance of a class.
* A class can create multiple objects.
* Objects occupy memory.
* The `new` keyword creates objects.
* The dot (`.`) operator is used to access members.

---

# Common Mistakes

## Forgetting to Create an Object

```java
class Student {

    void display() {

        System.out.println("Hello");

    }

}
```

Trying to call:

```java
display();
```

will cause an error.

Correct:

```java
Student s = new Student();

s.display();
```

---

## Confusing Class with Object

❌ Incorrect

```text
Student is an object.
```

✔ Correct

```text
Student is a class.

s is an object.
```

---

## Accessing Instance Variables Without an Object

Incorrect:

```java
System.out.println(name);
```

Correct:

```java
Student s = new Student();

System.out.println(s.name);
```

---

# Interview Notes

### Difference Between Class and Object

| Class                  | Object               |
| ---------------------- | -------------------- |
| Blueprint              | Instance             |
| Logical entity         | Physical entity      |
| No memory allocated    | Memory allocated     |
| Used to create objects | Created from a class |

---

### Where Are Objects Stored?

Objects are stored in **Heap Memory**.

Reference variables are stored in **Stack Memory**.

---

### Can One Class Have Multiple Objects?

Yes.

Every object has its own copy of instance variables.

---

### What Does the `new` Keyword Do?

The `new` keyword allocates memory for an object in the heap and returns its reference.

---

# Summary

* A class is a blueprint for creating objects.
* An object is an instance of a class.
* Objects access variables and methods using the dot (`.`) operator.
* Multiple objects can be created from the same class.
* Objects are stored in heap memory, while reference variables are stored in stack memory.
* Understanding classes and objects is the first step toward mastering OOP.
