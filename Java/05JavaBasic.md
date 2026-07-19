# Java Basics

This section covers the basic concepts required to start programming in Java.

---

# 1. Comments

## Definition

Comments are non-executable statements used to explain the code. They improve readability and are ignored by the Java compiler.

## Types of Comments

### Single-Line Comment

```java
// This is a single-line comment
```

### Multi-Line Comment

```java
/*
This is a
multi-line comment.
*/
```

### Documentation Comment

```java
/**
 * This is a documentation comment.
 */
```

---

# 2. Variables

## Definition

A variable is a named memory location used to store data. Its value can change during program execution.

## Syntax

```java
dataType variableName = value;
```

## Example

```java
int age = 20;
String name = "Amay";

System.out.println(age);
System.out.println(name);
```

---

# 3. Data Types

## Definition

A data type specifies the type of data a variable can store.

## Primitive Data Types

| Data Type | Example   |
| --------- | --------- |
| byte      | `10`      |
| short     | `200`     |
| int       | `1000`    |
| long      | `100000L` |
| float     | `12.5f`   |
| double    | `99.99`   |
| char      | `'A'`     |
| boolean   | `true`    |

## Non-Primitive Data Types

* String
* Array
* Class
* Object
* Interface

## Example

```java
int marks = 95;
double salary = 50000.50;
char grade = 'A';
boolean passed = true;
```

---

# 4. Literals

## Definition

Literals are fixed values written directly in the source code.

## Example

```java
int age = 20;
double pi = 3.14;
char grade = 'A';
String name = "Java";
boolean flag = true;
```

---

# 5. Type Casting

## Definition

Type casting is the process of converting one data type into another.

### Implicit Casting (Widening)

```java
int num = 10;
double value = num;

System.out.println(value);
```

### Explicit Casting (Narrowing)

```java
double price = 99.99;
int amount = (int) price;

System.out.println(amount);
```

---

# 6. Operators

## Definition

Operators are special symbols used to perform operations on variables and values.

### Arithmetic Operators

```java
+, -, *, /, %
```

### Relational Operators

```java
==, !=, >, <, >=, <=
```

### Logical Operators

```java
&&, ||, !
```

### Assignment Operators

```java
=, +=, -=, *=, /=, %=
```

### Example

```java
int a = 10;
int b = 5;

System.out.println(a + b);
System.out.println(a > b);
System.out.println(a == b);
```

---

# 7. Input & Output

## Definition

Java provides input and output operations to interact with the user.

### Output

```java
System.out.print("Hello ");
System.out.println("Java");
System.out.printf("Age: %d", 20);
```

### Input

```java
import java.util.Scanner;

Scanner sc = new Scanner(System.in);

int age = sc.nextInt();
String name = sc.next();
```

---

# 8. Escape Sequences

## Definition

Escape sequences are special characters used inside strings.

| Escape Sequence | Description  |
| --------------- | ------------ |
| `\n`            | New Line     |
| `\t`            | Tab          |
| `\"`            | Double Quote |
| `\\`            | Backslash    |

## Example

```java
System.out.println("Hello\nJava");
System.out.println("Java\tProgramming");
```

---

# 9. Keywords

## Definition

Keywords are reserved words that have predefined meanings in Java and cannot be used as identifiers.

### Common Keywords

```text
class
public
private
static
void
if
else
for
while
return
new
this
super
try
catch
```

---

# 10. Naming Conventions

## Definition

Naming conventions are standard rules followed while naming classes, methods, variables, and constants.

### Class

Use **PascalCase**

```java
StudentDetails
Employee
```

### Variable

Use **camelCase**

```java
studentName
totalMarks
```

### Method

Use **camelCase**

```java
calculateSum()
displayResult()
```

### Constant

Use **UPPER_CASE**

```java
MAX_SIZE
PI
```

---

# 11. Command Line Compilation

## Compile a Java Program

```bash
javac Main.java
```

This command converts the source code (`.java`) into bytecode (`.class`).

---

## Run a Java Program

```bash
java Main
```

The JVM loads the `.class` file and executes the program.

---

# Quick Revision

* Comments improve code readability.
* Variables store data.
* Data types define the type of value stored.
* Literals are fixed values written directly in code.
* Type casting converts one data type into another.
* Operators perform operations on operands.
* Scanner is used for input.
* `System.out.println()` displays output.
* Escape sequences format strings.
* Keywords are reserved words.
* Follow Java naming conventions for clean code.
* `javac` compiles Java programs, and `java` runs them.
