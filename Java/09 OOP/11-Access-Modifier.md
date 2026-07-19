# Access Modifiers in Java

Access Modifiers are keywords used to control the visibility and accessibility of classes, variables, methods, and constructors.

They help implement **data hiding** and **encapsulation** by restricting access to class members.

---

# Why Use Access Modifiers?

Access modifiers help to:

* Protect data from unauthorized access.
* Control the visibility of classes and members.
* Improve security.
* Support encapsulation.
* Make code easier to maintain.

---

# Types of Access Modifiers

Java provides four access modifiers:

1. `public`
2. `protected`
3. `default` (Package-Private)
4. `private`

---

# 1. Public

Members declared as `public` can be accessed from **any class** in **any package**.

### Example

```java
class Student {

    public String name = "Amay";

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
Amay
```

### Use Case

Use `public` when the member should be accessible from anywhere.

---

# 2. Private

Members declared as `private` can only be accessed **within the same class**.

### Example

```java
class Student {

    private int age = 22;

    public int getAge() {

        return age;

    }

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        System.out.println(s.getAge());

    }

}
```

### Output

```text
22
```

### Use Case

Use `private` for sensitive data that should not be modified directly.

---

# 3. Protected

Members declared as `protected` are accessible:

* Within the same class.
* Within the same package.
* In subclasses, even if they are in a different package.

### Example

```java
class Animal {

    protected void sound() {

        System.out.println("Animal Sound");

    }

}

class Dog extends Animal {

    void display() {

        sound();

    }

}
```

---

# 4. Default (Package-Private)

If no access modifier is specified, Java uses the **default** access level.

Members with default access are accessible only within the **same package**.

### Example

```java
class Student {

    String name = "Amay";

}
```

Here, `name` has default access.

---

# Accessibility Table

| Access Modifier | Same Class | Same Package | Subclass (Different Package) | Different Package |
| --------------- | :--------: | :----------: | :--------------------------: | :---------------: |
| `private`       |      ✅     |       ❌      |               ❌              |         ❌         |
| `default`       |      ✅     |       ✅      |               ❌              |         ❌         |
| `protected`     |      ✅     |       ✅      |               ✅              |         ❌         |
| `public`        |      ✅     |       ✅      |               ✅              |         ✅         |

---

# Access Modifiers for Classes

Only two access modifiers can be used with top-level classes:

* `public`
* `default`

Example:

```java
public class Student {

}
```

or

```java
class Student {

}
```

A top-level class **cannot** be declared as `private` or `protected`.

---

# Real-World Example

Imagine a **Bank Account**.

```java
class BankAccount {

    private double balance;

    public void deposit(double amount) {

        balance += amount;

    }

    public double getBalance() {

        return balance;

    }

}
```

The `balance` is hidden from direct access. Users must use methods like `deposit()` and `getBalance()`.

This improves security and follows encapsulation.

---

# Important Points

* `private` provides the highest level of access restriction.
* `public` provides the least restriction.
* `protected` is mainly used with inheritance.
* Default access is limited to the same package.
* Top-level classes cannot be `private` or `protected`.

---

# Common Mistakes

## Accessing a Private Variable Directly

❌ Incorrect

```java
class Student {

    private int age = 20;

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        System.out.println(s.age);

    }

}
```

This causes a compilation error.

✔ Correct

```java
class Student {

    private int age = 20;

    public int getAge() {

        return age;

    }

}
```

---

## Assuming Default Means Public

```java
class Student {

    String name;

}
```

The variable `name` is **not public**. It is accessible only within the same package.

---

# Interview Notes

### What are Access Modifiers?

Access modifiers control the visibility of classes, variables, methods, and constructors.

---

### Which Access Modifier is the Most Restrictive?

`private`

---

### Which Access Modifier is the Least Restrictive?

`public`

---

### Can a Top-Level Class Be Private?

No.

A top-level class can only be `public` or `default`.

---

### What is the Difference Between `protected` and `default`?

| `protected`                                  | `default`                          |
| -------------------------------------------- | ---------------------------------- |
| Accessible in subclasses outside the package | Not accessible outside the package |

---

# Summary

* Java provides four access modifiers: `public`, `protected`, `default`, and `private`.
* Access modifiers control the visibility of class members.
* `private` is commonly used to achieve encapsulation.
* `protected` is useful in inheritance.
* `public` allows access from anywhere.
* Default access restricts access to the same package.
