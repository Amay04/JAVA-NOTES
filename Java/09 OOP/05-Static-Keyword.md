# Static Keyword in Java

The `static` keyword is used to make variables, methods, blocks, and nested classes belong to the **class** instead of individual objects.

A static member is created only **once** and is shared among all objects of the class.

---

# Why Use `static`?

Normally, every object gets its own copy of instance variables.

Sometimes, we need a variable or method that is common to all objects.

For example:

* College Name
* Company Name
* PI Value
* Counter of Objects

Instead of creating multiple copies, we declare them as `static`.

---

# Static Variable

A **static variable** belongs to the class rather than an object.

There is only **one copy** of a static variable, shared by all objects.

### Example

```java
class Student {

    String name;
    static String college = "ABC College";

    Student(String name) {
        this.name = name;
    }

    void display() {
        System.out.println(name + " - " + college);
    }

}

public class Main {

    public static void main(String[] args) {

        Student s1 = new Student("Amay");
        Student s2 = new Student("Rahul");

        s1.display();
        s2.display();

    }

}
```

### Output

```text
Amay - ABC College
Rahul - ABC College
```

Both objects share the same `college` variable.

---

# Static Method

A **static method** belongs to the class and can be called without creating an object.

### Syntax

```java
className.methodName();
```

### Example

```java
class Student {

    static void greet() {
        System.out.println("Welcome!");
    }

}

public class Main {

    public static void main(String[] args) {

        Student.greet();

    }

}
```

### Output

```text
Welcome!
```

---

# Why is `main()` Static?

The JVM starts program execution by calling the `main()` method.

Since no object exists at that time, `main()` must be declared as `static`.

```java
public static void main(String[] args)
```

---

# Static Block

A **static block** executes automatically when the class is loaded into memory.

It runs only once, before the `main()` method.

### Example

```java
class Main {

    static {

        System.out.println("Static Block");

    }

    public static void main(String[] args) {

        System.out.println("Main Method");

    }

}
```

### Output

```text
Static Block
Main Method
```

---

# Static Nested Class

A class declared with the `static` keyword inside another class is called a **static nested class**.

```java
class Outer {

    static class Inner {

        void display() {
            System.out.println("Static Nested Class");
        }

    }

}
```

---

# Static vs Instance Variable

| Static Variable         | Instance Variable             |
| ----------------------- | ----------------------------- |
| Belongs to the class    | Belongs to an object          |
| One copy                | Separate copy for each object |
| Shared by all objects   | Unique for every object       |
| Access using class name | Access using object           |

---

# Static vs Non-Static Method

| Static Method                           | Non-Static Method                           |
| --------------------------------------- | ------------------------------------------- |
| Belongs to class                        | Belongs to object                           |
| Called without object                   | Requires object                             |
| Can access only static members directly | Can access both static and instance members |

---

# Memory Representation

```text
            Heap Memory

 Student Object 1
 -----------------
 name = "Amay"

 Student Object 2
 -----------------
 name = "Rahul"


            Method Area

 Student Class
 -----------------
 static college = "ABC College"
 static greet()
```

* Instance variables are stored with each object.
* Static members are stored once in the **Method Area** (Class Area).

---

# Rules of Static Members

* Static methods can directly access only static variables and static methods.
* Static methods cannot directly access instance variables.
* Static methods cannot use `this` or `super`.
* Static variables are initialized when the class is loaded.

---

# Important Points

* Static members belong to the class.
* Static variables are shared among all objects.
* Static methods can be called without creating an object.
* Static blocks execute before the `main()` method.
* The `main()` method is static because the JVM calls it without creating an object.

---

# Common Mistakes

## Accessing Instance Variables Inside a Static Method

❌ Incorrect

```java
class Student {

    int age = 20;

    static void display() {
        System.out.println(age);
    }

}
```

This causes a compilation error.

✔ Correct

```java
class Student {

    static int age = 20;

    static void display() {
        System.out.println(age);
    }

}
```

---

## Using `this` in a Static Method

❌ Incorrect

```java
static void show() {

    System.out.println(this);

}
```

A static method does not belong to any object.

---

## Calling a Static Method Using an Object

```java
Student s = new Student();

s.greet();
```

Although this works, it is not recommended.

Preferred way:

```java
Student.greet();
```

---

# Interview Notes

### What is a Static Variable?

A variable shared by all objects of a class.

---

### What is a Static Method?

A method that belongs to the class and can be called without creating an object.

---

### Why is `main()` Static?

Because the JVM calls it before creating any object.

---

### Can a Static Method Access Instance Variables?

No.

A static method can directly access only static members.

---

### Can We Override a Static Method?

No.

Static methods are **hidden**, not overridden.

---

# Summary

* The `static` keyword makes a member belong to the class instead of an object.
* Static variables are shared among all objects.
* Static methods can be called using the class name.
* Static blocks execute only once when the class is loaded.
* Static methods cannot use `this` or directly access instance members.
* The `main()` method is static because it is called directly by the JVM.
