# Constructors in Java

A constructor is a special member of a class that is automatically called when an object is created. It is mainly used to initialize the object's data.

---

# Why Use Constructors?

Without constructors, we need to initialize object data manually after creating every object.

Example without a constructor:

```java
Student s = new Student();

s.name = "Amay";
s.age = 22;
```

Using a constructor:

```java
Student s = new Student("Amay", 22);
```

Constructors make object initialization easier and cleaner.

---

# Characteristics of a Constructor

* Has the **same name as the class**.
* Does **not have a return type**, not even `void`.
* Called automatically when an object is created.
* Can be overloaded.
* Cannot be inherited.

---

# Syntax

```java
class ClassName {

    ClassName() {

        // Initialization

    }

}
```

---

# Default Constructor

If no constructor is written by the programmer, Java automatically provides a **default constructor**.

Example:

```java
class Student {

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

        System.out.println("Object Created");

    }

}
```

### Output

```text
Object Created
```

> The compiler creates the default constructor only when no constructor is explicitly defined.

---

# No-Argument Constructor

A constructor that does not accept any parameters.

```java
class Student {

    Student() {

        System.out.println("Constructor Called");

    }

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student();

    }

}
```

### Output

```text
Constructor Called
```

---

# Parameterized Constructor

A constructor that accepts parameters.

```java
class Student {

    String name;
    int age;

    Student(String n, int a) {

        name = n;
        age = a;

    }

    void display() {

        System.out.println(name);
        System.out.println(age);

    }

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student("Amay", 22);

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

# Constructor Overloading

A class can have multiple constructors with different parameter lists.

```java
class Student {

    Student() {

        System.out.println("Default Constructor");

    }

    Student(String name) {

        System.out.println(name);

    }

}

public class Main {

    public static void main(String[] args) {

        new Student();

        new Student("Amay");

    }

}
```

### Output

```text
Default Constructor
Amay
```

---

# Constructor Chaining

One constructor can call another constructor in the same class using the `this()` keyword.

```java
class Student {

    Student() {

        this("Amay");

        System.out.println("Default");

    }

    Student(String name) {

        System.out.println(name);

    }

}

public class Main {

    public static void main(String[] args) {

        new Student();

    }

}
```

### Output

```text
Amay
Default
```

> `this()` must be the **first statement** inside a constructor.

---

# Copy Constructor

Java does not provide a built-in copy constructor like C++, but we can create one manually.

```java
class Student {

    String name;

    Student(String name) {

        this.name = name;

    }

    Student(Student s) {

        this.name = s.name;

    }

}
```

This constructor copies the values from one object to another.

---

# Difference Between Constructor and Method

| Constructor                       | Method                            |
| --------------------------------- | --------------------------------- |
| Initializes an object             | Performs a task                   |
| Same name as class                | Any valid name                    |
| No return type                    | Must have a return type or `void` |
| Called automatically              | Called explicitly                 |
| Executes once per object creation | Can be called many times          |

---

# Important Points

* Every class has a constructor.
* Constructors are automatically called during object creation.
* Constructors can be overloaded.
* Constructors cannot be inherited.
* Constructors cannot be `static`, `final`, or `abstract`.

---

# Common Mistakes

## Giving a Return Type

❌ Incorrect

```java
class Student {

    void Student() {

    }

}
```

This is **not** a constructor—it is a method.

✔ Correct

```java
class Student {

    Student() {

    }

}
```

---

## Constructor Name Doesn't Match Class Name

❌ Incorrect

```java
class Student {

    StudentData() {

    }

}
```

`StudentData()` is treated as a method, not a constructor.

---

## Calling `this()` Anywhere

❌ Incorrect

```java
Student() {

    System.out.println("Hello");

    this("Amay");

}
```

✔ Correct

```java
Student() {

    this("Amay");

    System.out.println("Hello");

}
```

---

# Interview Notes

### What is a Constructor?

A constructor is a special member of a class used to initialize objects. It is called automatically when an object is created.

---

### Can a Constructor Be Private?

Yes.

Private constructors are commonly used in the **Singleton Design Pattern** to prevent object creation from outside the class.

---

### Can We Overload Constructors?

Yes.

A class can have multiple constructors with different parameter lists.

---

### Can Constructors Be Inherited?

No.

Constructors are **not inherited**, but they can be called using `super()` from a child class.

---

### Can We Call a Constructor Manually?

No.

Constructors are automatically invoked when an object is created using the `new` keyword.

---

# Summary

* A constructor initializes an object.
* It has the same name as the class.
* It has no return type.
* Java provides a default constructor if none is defined.
* Constructors can be overloaded.
* `this()` is used for constructor chaining.
* Constructors are not inherited but can be invoked using `super()` in inheritance.
