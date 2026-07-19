# Methods in Java

A method is a block of code that performs a specific task. Instead of writing the same code multiple times, you can write it once inside a method and call it whenever needed.

---

# Why Use Methods?

Methods help to:

* Avoid code duplication.
* Improve code readability.
* Make programs easier to maintain.
* Divide large programs into smaller reusable parts.

---

# Syntax

```java
returnType methodName(parameters) {

    // Method Body

}
```

### Example

```java
public class Main {

    static void greet() {
        System.out.println("Welcome to Java!");
    }

    public static void main(String[] args) {

        greet();

    }

}
```

### Output

```text
Welcome to Java!
```

---

# Parts of a Method

```java
public static int add(int a, int b) {

    return a + b;

}
```

| Part             | Description                 |
| ---------------- | --------------------------- |
| `public`         | Access modifier             |
| `static`         | Method belongs to the class |
| `int`            | Return type                 |
| `add`            | Method name                 |
| `(int a, int b)` | Parameters                  |
| `return`         | Returns a value             |

---

# Types of Methods

## 1. Method Without Parameters and Without Return Value

```java
public class Main {

    static void display() {

        System.out.println("Hello");

    }

    public static void main(String[] args) {

        display();

    }

}
```

---

## 2. Method With Parameters

```java
public class Main {

    static void greet(String name) {

        System.out.println("Hello " + name);

    }

    public static void main(String[] args) {

        greet("Amay");

    }

}
```

### Output

```text
Hello Amay
```

---

## 3. Method With Return Value

```java
public class Main {

    static int square(int number) {

        return number * number;

    }

    public static void main(String[] args) {

        System.out.println(square(5));

    }

}
```

### Output

```text
25
```

---

# Method Parameters vs Arguments

## Parameter

A parameter is a variable declared in the method definition.

```java
static void display(String name)
```

Here, `name` is a **parameter**.

---

## Argument

An argument is the actual value passed when calling the method.

```java
display("Amay");
```

Here, `"Amay"` is an **argument**.

---

# Method Overloading

Method overloading means creating multiple methods with the same name but different parameters.

### Example

```java
public class Main {

    static int add(int a, int b) {

        return a + b;

    }

    static double add(double a, double b) {

        return a + b;

    }

    public static void main(String[] args) {

        System.out.println(add(10, 20));
        System.out.println(add(5.5, 4.5));

    }

}
```

### Output

```text
30
10.0
```

---

# Method Call

A method is executed only when it is called.

```java
display();
```

The control goes to the method, executes the statements, and then returns to the calling method.

---

# Important Points

* Every Java program starts from the `main()` method.
* A method can return only one value.
* `void` methods do not return any value.
* Parameters are optional.
* A method can be called multiple times.

---

# Common Mistakes

## Forgetting to Call the Method

```java
public class Main {

    static void display() {

        System.out.println("Hello");

    }

    public static void main(String[] args) {

    }

}
```

The method is never executed because it is not called.

---

## Missing Return Statement

```java
static int add() {

}
```

This causes a compilation error because the method has a return type of `int`.

Correct:

```java
static int add() {

    return 10;

}
```

---

# Interview Notes

### What is a Method?

A method is a reusable block of code that performs a specific task.

---

### Difference Between Parameter and Argument

| Parameter                     | Argument                  |
| ----------------------------- | ------------------------- |
| Declared in method definition | Passed during method call |

---

### Can We Overload the `main()` Method?

Yes.

However, the JVM always calls:

```java
public static void main(String[] args)
```

---

### Difference Between Method Overloading and Method Overriding

| Overloading               | Overriding             |
| ------------------------- | ---------------------- |
| Same class                | Parent and Child class |
| Different parameters      | Same parameters        |
| Compile-time polymorphism | Runtime polymorphism   |

---

# Summary

* Methods help organize code into reusable blocks.
* They improve readability and reduce duplication.
* Methods can have parameters and return values.
* Method overloading allows multiple methods with the same name but different parameter lists.
* Every Java application begins execution from the `main()` method.
