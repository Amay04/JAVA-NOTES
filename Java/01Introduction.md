# Introduction to Java

## Definition

Java is a **high-level, object-oriented, class-based, and platform-independent** programming language developed by **Sun Microsystems** in **1995**. It is currently owned and maintained by **Oracle Corporation**.

Java follows the principle **"Write Once, Run Anywhere (WORA)"**, meaning a Java program can run on any operating system that has a **Java Virtual Machine (JVM)**.

---

# Why Java?

Java is one of the most widely used programming languages because it is reliable, secure, and easy to maintain. It is used in various domains such as:

* Desktop Applications
* Web Applications
* Android Development
* Enterprise Applications
* Banking Systems
* Cloud Computing
* IoT Applications
* Backend Development

---

# History of Java

* Java was developed by **James Gosling** and his team at **Sun Microsystems**.
* The project was initially named **Oak**.
* Since the name **Oak** was already registered, it was renamed to **Java**.
* In **2010**, **Oracle Corporation** acquired Sun Microsystems and became the owner of Java.

---

# How Java Works

Unlike many programming languages, Java does not directly generate machine code.

```text
Java Source Code (.java)
        │
        ▼
Java Compiler (javac)
        │
        ▼
Bytecode (.class)
        │
        ▼
Java Virtual Machine (JVM)
        │
        ▼
Machine Code
        │
        ▼
Program Output
```

The JVM makes Java platform independent by converting bytecode into machine code suitable for the operating system.

---

# First Java Program

```java
public class Main {

    public static void main(String[] args) {

        System.out.println("Hello, Java!");

    }

}
```

### Output

```text
Hello, Java!
```

---

# Understanding the Program

## `public class Main`

```java
public class Main {
```

* `public` → Access modifier that allows the class to be accessed from anywhere.
* `class` → Keyword used to declare a class.
* `Main` → Name of the class.

---

## `main()` Method

```java
public static void main(String[] args)
```

The `main()` method is the **entry point** of every Java application. The JVM starts program execution from this method.

### Components of the `main()` Method

| Keyword         | Description                                |
| --------------- | ------------------------------------------ |
| `public`        | Accessible from anywhere                   |
| `static`        | JVM can call it without creating an object |
| `void`          | Method does not return any value           |
| `main`          | Predefined method name recognized by JVM   |
| `String[] args` | Stores command-line arguments              |

---

## `System.out.println()`

```java
System.out.println("Hello, Java!");
```

This statement prints text on the console and moves the cursor to the next line.

### Components

| Component   | Description                            |
| ----------- | -------------------------------------- |
| `System`    | Built-in Java class                    |
| `out`       | Standard output stream                 |
| `println()` | Prints the text followed by a new line |

---

# Advantages of Java

* Platform Independent
* Object-Oriented
* Secure
* Robust
* Portable
* Architecture Neutral
* Multithreaded
* Distributed
* Dynamic
* High Performance (using JIT Compiler)
* Automatic Garbage Collection

---

# Applications of Java

Java is widely used for developing:

* Android Applications
* Web Applications
* Enterprise Software
* Banking Applications
* E-commerce Platforms
* Cloud Applications
* Big Data Technologies
* Scientific Applications
* Embedded Systems
* Desktop Applications

---

# Important Points

* Java source files use the **`.java`** extension.
* Compiled Java files use the **`.class`** extension.
* Java programs are compiled into **bytecode**.
* The JVM converts bytecode into machine code.
* Java follows the **Write Once, Run Anywhere (WORA)** principle.
* Java is both **compiled and interpreted**.

---

# Common Mistakes

## 1. File Name Does Not Match the Class Name

### Incorrect

```java
// File Name: Demo.java

public class Main {

}
```

### Correct

```java
// File Name: Main.java

public class Main {

}
```

---

## 2. Missing `main()` Method

```java
public class Main {

}
```

The program compiles successfully but cannot be executed because there is no entry point.

---

## 3. Incorrect `main()` Method Signature

### Incorrect

```java
public void main(String args[])
```

### Correct

```java
public static void main(String[] args)
```

---

# Interview Notes

### Why is Java Platform Independent?

Java source code is compiled into **bytecode**, which is executed by the **Java Virtual Machine (JVM)**. Since every operating system has its own JVM implementation, the same bytecode can run on Windows, Linux, or macOS without modification.

---

### Why is Java Called Both Compiled and Interpreted?

* The **Java Compiler (`javac`)** compiles source code into bytecode.
* The **JVM** interprets or Just-In-Time (JIT) compiles the bytecode into machine code before execution.

---

### What is WORA?

**Write Once, Run Anywhere (WORA)** means that Java code needs to be written and compiled only once. The generated bytecode can run on any platform that has a compatible JVM.

---

# Summary

* Java is a high-level, object-oriented, and platform-independent programming language.
* It was developed by James Gosling at Sun Microsystems and is now maintained by Oracle.
* Java programs are compiled into bytecode and executed by the JVM.
* The `main()` method is the entry point of every Java program.
* Java is widely used in web, mobile, enterprise, cloud, and desktop application development.
* The principle **Write Once, Run Anywhere (WORA)** is one of Java's biggest advantages.
