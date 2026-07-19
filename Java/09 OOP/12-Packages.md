# Packages in Java

A **package** is a collection of related classes, interfaces, enums, and sub-packages. Packages are used to organize Java code and avoid naming conflicts.

Packages work like folders in a computer. Just as folders help organize files, packages help organize Java classes.

---

# Why Use Packages?

Packages are used to:

* Organize Java programs.
* Avoid class name conflicts.
* Improve code readability.
* Provide access protection.
* Make large projects easier to manage.

---

# Types of Packages

Java supports two types of packages:

1. Built-in Packages
2. User-Defined Packages

---

# Built-in Packages

Built-in packages are provided by Java.

Some commonly used packages are:

| Package     | Purpose                                       |
| ----------- | --------------------------------------------- |
| `java.lang` | Basic classes like `String`, `Math`, `System` |
| `java.util` | Collections, Scanner, Random                  |
| `java.io`   | File handling and input/output                |
| `java.net`  | Networking                                    |
| `java.sql`  | Database connectivity                         |
| `java.time` | Date and Time API                             |

Example:

```java
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Name: ");

        String name = sc.nextLine();

        System.out.println(name);

        sc.close();

    }

}
```

---

# User-Defined Packages

A user-defined package is created by the programmer.

### Syntax

```java
package packageName;
```

Example:

```java
package student;
```

This statement must always be the **first line** of the Java source file.

---

# Creating a Package

### Step 1

Create a Java file.

```java
package student;

public class Student {

    public void display() {

        System.out.println("Student Package");

    }

}
```

---

### Step 2

Compile the file.

```bash
javac -d . Student.java
```

The `-d` option creates the required package directory automatically.

---

### Step 3

Use the package in another class.

```java
import student.Student;

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        s.display();

    }

}
```

### Output

```text
Student Package
```

---

# Import Statement

The `import` keyword is used to access classes from another package.

### Syntax

```java
import packageName.ClassName;
```

Example:

```java
import java.util.Scanner;
```

Without import:

```java
java.util.Scanner sc = new java.util.Scanner(System.in);
```

With import:

```java
Scanner sc = new Scanner(System.in);
```

---

# Importing All Classes

Use `*` to import all classes from a package.

```java
import java.util.*;
```

This imports all classes from the `java.util` package.

---

# Static Import

Static import allows direct access to static members without using the class name.

Without static import:

```java
System.out.println(Math.sqrt(25));
```

With static import:

```java
import static java.lang.Math.sqrt;

public class Main {

    public static void main(String[] args) {

        System.out.println(sqrt(25));

    }

}
```

### Output

```text
5.0
```

---

# Package Naming Conventions

Java package names should:

* Use lowercase letters.
* Avoid spaces.
* Be meaningful.
* Follow reverse domain naming for large projects.

Examples:

```text
com.company.project

com.example.student

org.apache.commons
```

---

# Package Hierarchy

Packages can contain sub-packages.

Example:

```text
com
│
└── company
    │
    └── project
        │
        ├── models
        ├── services
        └── utils
```

This structure helps organize large applications.

---

# Advantages of Packages

* Better code organization.
* Avoids naming conflicts.
* Improves code reusability.
* Provides access protection.
* Simplifies project maintenance.

---

# Important Points

* A package statement must be the first line of the source file.
* Built-in packages are provided by Java.
* User-defined packages are created by programmers.
* The `import` statement allows access to classes from other packages.
* Static import provides direct access to static members.

---

# Common Mistakes

## Package Statement Not at the Top

❌ Incorrect

```java
import java.util.Scanner;

package student;
```

The package declaration must always be the first statement.

✔ Correct

```java
package student;

import java.util.Scanner;
```

---

## Wrong Package Name

```java
package Student Data;
```

Package names cannot contain spaces.

Correct:

```java
package studentdata;
```

---

## Forgetting to Import a Class

```java
Scanner sc = new Scanner(System.in);
```

Without:

```java
import java.util.Scanner;
```

the compiler cannot recognize `Scanner`.

---

# Interview Notes

### What is a Package?

A package is a collection of related classes and interfaces used to organize Java programs.

---

### Why Do We Use Packages?

Packages help organize code, prevent naming conflicts, and improve maintainability.

---

### What is the Difference Between Built-in and User-Defined Packages?

| Built-in Package     | User-Defined Package      |
| -------------------- | ------------------------- |
| Provided by Java     | Created by the programmer |
| Example: `java.util` | Example: `student`        |

---

### What is Static Import?

Static import allows direct access to static members without using the class name.

Example:

```java
import static java.lang.Math.PI;
```

---

### Which Package is Imported Automatically?

`java.lang`

It includes commonly used classes such as:

* String
* System
* Math
* Object

---

# Summary

* A package is a collection of related classes and interfaces.
* Packages help organize code and avoid naming conflicts.
* Java provides built-in packages, and programmers can create user-defined packages.
* The `import` statement is used to access classes from other packages.
* `java.lang` is imported automatically.
* Package names should follow Java naming conventions and remain lowercase.
