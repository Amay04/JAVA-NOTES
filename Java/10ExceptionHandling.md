# Exception Handling in Java

Exception Handling is a mechanism used to handle runtime errors so that the normal flow of the program is not interrupted.

Instead of terminating the program abruptly, Java allows us to catch and handle exceptions gracefully.

---

# Why Do We Need Exception Handling?

Consider the following program:

```java
public class Main {

    public static void main(String[] args) {

        int result = 10 / 0;

        System.out.println(result);

    }

}
```

### Output

```text
Exception in thread "main" java.lang.ArithmeticException: / by zero
```

The program terminates immediately because of the exception.

Using Exception Handling, we can prevent the program from crashing.

---

# What is an Exception?

An **exception** is an event that occurs during program execution and disrupts the normal flow of the program.

Examples:

* Dividing a number by zero
* Accessing an invalid array index
* Reading a file that doesn't exist
* Calling a method on a `null` object

---

# Exception Hierarchy

```text
Object
   │
Throwable
   ├── Error
   └── Exception
        ├── RuntimeException
        ├── IOException
        ├── SQLException
        └── ...
```

* **Error** → Serious problems that applications usually cannot recover from.
* **Exception** → Problems that can be handled by the program.

---

# Types of Exceptions

## 1. Checked Exceptions

Checked exceptions are checked by the compiler.

They must be handled using `try-catch` or declared using `throws`.

Examples:

* IOException
* SQLException
* FileNotFoundException

---

## 2. Unchecked Exceptions

Unchecked exceptions occur during runtime.

The compiler does not force you to handle them.

Examples:

* ArithmeticException
* NullPointerException
* ArrayIndexOutOfBoundsException

---

# try-catch Block

The `try` block contains code that may throw an exception.

The `catch` block handles the exception.

### Syntax

```java
try {

    // Risky Code

} catch (ExceptionType e) {

    // Handle Exception

}
```

---

# Example

```java
public class Main {

    public static void main(String[] args) {

        try {

            int result = 10 / 0;

        } catch (ArithmeticException e) {

            System.out.println("Cannot divide by zero.");

        }

    }

}
```

### Output

```text
Cannot divide by zero.
```

---

# Multiple Catch Blocks

A `try` block can have multiple `catch` blocks.

```java
try {

    int[] arr = new int[2];

    System.out.println(arr[5]);

} catch (ArithmeticException e) {

    System.out.println("Arithmetic Error");

} catch (ArrayIndexOutOfBoundsException e) {

    System.out.println("Invalid Array Index");

}
```

### Output

```text
Invalid Array Index
```

---

# finally Block

The `finally` block always executes whether an exception occurs or not.

It is mainly used to release resources such as files and database connections.

```java
try {

    System.out.println("Inside Try");

} finally {

    System.out.println("Finally Block");

}
```

### Output

```text
Inside Try
Finally Block
```

---

# throw Keyword

The `throw` keyword is used to manually create and throw an exception.

```java
public class Main {

    public static void main(String[] args) {

        throw new ArithmeticException("Invalid Operation");

    }

}
```

---

# throws Keyword

The `throws` keyword declares that a method may throw an exception.

```java
import java.io.IOException;

class Demo {

    void readFile() throws IOException {

        // File handling code

    }

}
```

---

# Difference Between `throw` and `throws`

| `throw`                        | `throws`                        |
| ------------------------------ | ------------------------------- |
| Used to throw an exception     | Declares possible exceptions    |
| Used inside a method           | Used in method declaration      |
| Throws one exception at a time | Can declare multiple exceptions |

---

# Custom Exception

Java allows us to create our own exceptions.

```java
class InvalidAgeException extends Exception {

    InvalidAgeException(String message) {

        super(message);

    }

}
```

Usage:

```java
if (age < 18) {

    throw new InvalidAgeException("Age must be 18 or above.");

}
```

---

# Common Runtime Exceptions

| Exception                      | Cause                     |
| ------------------------------ | ------------------------- |
| ArithmeticException            | Division by zero          |
| NullPointerException           | Accessing a null object   |
| ArrayIndexOutOfBoundsException | Invalid array index       |
| NumberFormatException          | Invalid number conversion |
| ClassCastException             | Invalid type casting      |

---

# Important Points

* Exception Handling prevents program termination.
* `try` contains risky code.
* `catch` handles exceptions.
* `finally` always executes.
* `throw` manually throws an exception.
* `throws` declares possible exceptions.

---

# Common Mistakes

## Catching the Wrong Exception

```java
try {

    int result = 10 / 0;

} catch (NullPointerException e) {

    System.out.println("Handled");

}
```

The exception is not caught because the wrong exception type is used.

---

## Placing `catch` Before `try`

❌ Incorrect

```java
catch(Exception e) {

}

try {

}
```

The `try` block must always come before the `catch` block.

---

## Ignoring Checked Exceptions

```java
FileReader file = new FileReader("data.txt");
```

This causes a compilation error unless the exception is handled or declared.

---

# Interview Notes

### What is Exception Handling?

Exception Handling is the process of handling runtime errors to prevent abnormal program termination.

---

### Difference Between Checked and Unchecked Exceptions

| Checked              | Unchecked                     |
| -------------------- | ----------------------------- |
| Checked by compiler  | Checked at runtime            |
| Must be handled      | Handling is optional          |
| Example: IOException | Example: NullPointerException |

---

### Difference Between Error and Exception

| Error                     | Exception           |
| ------------------------- | ------------------- |
| Serious problem           | Recoverable problem |
| Cannot usually be handled | Can be handled      |

---

### Difference Between `throw` and `throws`

* `throw` is used to throw an exception.
* `throws` is used to declare exceptions in a method.

---

### Does `finally` Always Execute?

Yes, except in rare cases such as JVM termination using `System.exit()`.

---

# Summary

* Exception Handling prevents unexpected program termination.
* Java provides `try`, `catch`, `finally`, `throw`, and `throws` for handling exceptions.
* Checked exceptions must be handled or declared.
* Unchecked exceptions occur during runtime.
* Custom exceptions allow developers to define application-specific error handling.
