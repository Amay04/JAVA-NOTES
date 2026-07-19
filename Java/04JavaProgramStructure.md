# Java Program Structure

Every Java program follows a specific structure. Understanding this structure helps you write correct Java programs and understand the purpose of each keyword.

---

# Table of Contents

1. Introduction
2. Basic Structure of a Java Program
3. Package Declaration
4. Import Statement
5. Class Declaration
6. Main Method
7. Statements
8. Blocks
9. Complete Example
10. Important Points
11. Common Mistakes
12. Interview Notes
13. Summary

---

# 1. Introduction

A Java program is made up of different components, such as packages, import statements, classes, methods, and statements. While some components are optional, every executable Java program must contain a **class** and a **main()** method.

---

# 2. Basic Structure of a Java Program

```java
package packageName;          // Optional

import java.util.Scanner;     // Optional

public class Main {

    public static void main(String[] args) {

        System.out.println("Hello, Java!");

    }

}
```

The structure consists of:

1. Package Declaration (Optional)
2. Import Statements (Optional)
3. Class Declaration (Mandatory)
4. Main Method (Mandatory for execution)
5. Statements (Program Logic)

---

# 3. Package Declaration

A package is a collection of related Java classes and interfaces.

The package declaration, if used, must always be the **first line** of the Java program.

### Syntax

```java
package mypackage;
```

### Example

```java
package com.example;
```

### Why Use Packages?

* Organize Java files.
* Avoid naming conflicts.
* Improve code management.
* Provide access control.

> If no package is declared, the class belongs to the **default package**.

---

# 4. Import Statement

The `import` statement allows you to use predefined classes from Java libraries without writing their full package names.

### Syntax

```java
import packageName.ClassName;
```

### Example

```java
import java.util.Scanner;
```

Now you can directly use:

```java
Scanner sc = new Scanner(System.in);
```

instead of:

```java
java.util.Scanner sc = new java.util.Scanner(System.in);
```

---

# 5. Class Declaration

A Java program is built using classes.

### Syntax

```java
public class ClassName {

}
```

### Example

```java
public class Student {

}
```

### Explanation

* `public` → Access modifier.
* `class` → Keyword used to declare a class.
* `Student` → Class name.

> The public class name should match the file name.

Example:

```text
File Name → Student.java

Class Name → Student
```

---

# 6. Main Method

The `main()` method is the entry point of every Java application.

The JVM starts executing the program from this method.

### Syntax

```java
public static void main(String[] args) {

}
```

### Explanation

| Keyword         | Meaning                                    |
| --------------- | ------------------------------------------ |
| `public`        | Accessible from anywhere                   |
| `static`        | JVM can call it without creating an object |
| `void`          | Does not return any value                  |
| `main`          | Entry point of the program                 |
| `String[] args` | Stores command-line arguments              |

---

# 7. Statements

Statements are individual instructions that tell Java what to do.

Every statement ends with a semicolon (`;`).

### Example

```java
int age = 20;

System.out.println(age);
```

Here:

* Variable declaration is a statement.
* Print statement is another statement.

---

# 8. Blocks

A block is a group of statements enclosed within curly braces `{}`.

Blocks improve readability and define the scope of variables.

### Example

```java
public static void main(String[] args) {

    int age = 20;

    System.out.println(age);

}
```

The statements inside `{}` belong to the `main()` method.

---

# 9. Complete Example

```java
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter your name: ");

        String name = sc.nextLine();

        System.out.println("Welcome " + name);

        sc.close();

    }

}
```

### Sample Output

```text
Enter your name: Amay
Welcome Amay
```

---

# 10. Important Points

* A Java program must contain at least one class.
* Every executable Java program requires a `main()` method.
* Statements end with a semicolon (`;`).
* Curly braces `{}` define blocks.
* Package declaration must be the first statement (if used).
* Import statements come after the package declaration.
* The public class name should match the file name.

---

# 11. Common Mistakes

## 1. File Name and Class Name Do Not Match

❌ Incorrect

```java
// File Name: Demo.java

public class Main {

}
```

✔ Correct

```java
// File Name: Main.java

public class Main {

}
```

---

## 2. Missing Semicolon

❌ Incorrect

```java
int age = 20
```

✔ Correct

```java
int age = 20;
```

---

## 3. Missing Curly Braces

❌ Incorrect

```java
public class Main

public static void main(String[] args)

System.out.println("Hello");
```

✔ Correct

```java
public class Main {

    public static void main(String[] args) {

        System.out.println("Hello");

    }

}
```

---

## 4. Missing `main()` Method

```java
public class Main {

}
```

The program will compile, but it cannot be executed because there is no entry point.

---

# 12. Interview Notes

### Why is the `main()` method static?

The JVM calls the `main()` method before creating any object. Declaring it as `static` allows it to be called without creating an instance of the class.

---

### Can a Java program have multiple classes?

Yes. A Java file can contain multiple classes, but only **one public class**, and its name must match the file name.

---

### Is the package declaration mandatory?

No. If omitted, the class belongs to the **default package**.

---

# 13. Summary

* A Java program is organized into packages, imports, classes, methods, and statements.
* The `main()` method is the starting point of program execution.
* Packages help organize classes, while imports allow the use of predefined Java libraries.
* Statements perform individual tasks, and blocks group related statements.
* Following the correct program structure improves readability and avoids compilation errors.
