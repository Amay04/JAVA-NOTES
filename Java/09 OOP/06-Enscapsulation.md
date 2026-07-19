# Encapsulation in Java

Encapsulation is one of the four pillars of Object-Oriented Programming (OOP). It is the process of **wrapping data (variables) and methods (functions) into a single unit**, called a class.

Encapsulation also helps in **data hiding** by restricting direct access to an object's data.

---

# Why Use Encapsulation?

Without encapsulation, any part of the program can directly modify an object's data, which may lead to incorrect or invalid values.

Encapsulation helps to:

* Protect data from unauthorized access.
* Improve security.
* Control how data is accessed and modified.
* Make the code easier to maintain.
* Increase flexibility.

---

# How to Achieve Encapsulation?

Encapsulation is achieved by:

1. Declaring variables as `private`.
2. Providing public **getter** and **setter** methods.

---

# Private Variables

A `private` variable can only be accessed inside its own class.

```java
class Student {

    private String name;
    private int age;

}
```

The variables `name` and `age` cannot be accessed directly from outside the class.

---

# Getter and Setter Methods

A **getter** method is used to read the value of a private variable.

A **setter** method is used to update the value of a private variable.

### Example

```java
class Student {

    private String name;

    public void setName(String name) {

        this.name = name;

    }

    public String getName() {

        return name;

    }

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        s.setName("Amay");

        System.out.println(s.getName());

    }

}
```

### Output

```text
Amay
```

---

# Data Hiding

Data hiding means preventing direct access to an object's internal data.

Instead of:

```java
student.name = "Amay";
```

we use:

```java
student.setName("Amay");
```

This allows the class to validate the data before storing it.

---

# Example with Validation

```java
class Student {

    private int age;

    public void setAge(int age) {

        if (age > 0) {

            this.age = age;

        }

    }

    public int getAge() {

        return age;

    }

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        s.setAge(-5);

        System.out.println(s.getAge());

    }

}
```

### Output

```text
0
```

The invalid value is not stored because the setter checks the input.

---

# Real-World Example

Consider an **ATM Machine**.

You cannot directly change your account balance.

Instead, you use methods such as:

* Deposit()
* Withdraw()
* CheckBalance()

The account balance is hidden from direct access.

This is an example of **encapsulation**.

---

# Advantages of Encapsulation

* Improves data security.
* Prevents accidental modification of data.
* Makes the program more flexible.
* Improves code maintainability.
* Supports data validation.
* Follows object-oriented design principles.

---

# Encapsulation vs Data Hiding

| Encapsulation                        | Data Hiding                     |
| ------------------------------------ | ------------------------------- |
| Wraps data and methods into one unit | Restricts direct access to data |
| Achieved using classes               | Achieved using access modifiers |
| Focuses on code organization         | Focuses on security             |

---

# Important Points

* Encapsulation combines data and methods into a single class.
* Private variables cannot be accessed directly outside the class.
* Getter methods read private data.
* Setter methods modify private data.
* Validation can be added inside setter methods.

---

# Common Mistakes

## Making Variables Public

❌ Incorrect

```java
class Student {

    public int age;

}
```

Anyone can modify the value directly.

✔ Correct

```java
class Student {

    private int age;

}
```

---

## No Validation in Setter

❌ Incorrect

```java
public void setAge(int age) {

    this.age = age;

}
```

✔ Better

```java
public void setAge(int age) {

    if (age >= 0) {

        this.age = age;

    }

}
```

---

# Interview Notes

### What is Encapsulation?

Encapsulation is the process of combining data and methods into a single unit while restricting direct access to the data.

---

### How is Encapsulation Achieved in Java?

By:

* Declaring variables as `private`.
* Providing public getter and setter methods.

---

### What is Data Hiding?

Data hiding is the practice of restricting direct access to an object's data using access modifiers such as `private`.

---

### Why Use Getter and Setter Methods?

They provide controlled access to private variables and allow validation before updating data.

---

### Is Encapsulation the Same as Data Hiding?

No.

* **Encapsulation** is the overall concept of bundling data and methods together.
* **Data Hiding** is one benefit of encapsulation, achieved using access modifiers.

---

# Summary

* Encapsulation is one of the four pillars of OOP.
* It combines data and methods into a single class.
* Private variables cannot be accessed directly from outside the class.
* Getter and setter methods provide controlled access to private data.
* Encapsulation improves security, flexibility, and maintainability.
