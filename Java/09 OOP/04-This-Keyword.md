# `this` Keyword in Java

The `this` keyword is a reference variable that refers to the **current object** of a class.

Whenever an object calls a method or constructor, `this` refers to that object.

---

# Why Do We Need `this`?

Sometimes a local variable (parameter) and an instance variable have the same name. In such cases, Java gives priority to the local variable.

The `this` keyword is used to refer to the instance variable of the current object.

---

# Syntax

```java id="p5v7na"
this.variableName;
```

---

# Using `this` to Access Instance Variables

```java id="yuzcs8"
class Student {

    String name;

    Student(String name) {

        this.name = name;

    }

    void display() {

        System.out.println(this.name);

    }

}

public class Main {

    public static void main(String[] args) {

        Student s = new Student("Amay");

        s.display();

    }

}
```

### Output

```text id="8hy8k0"
Amay
```

### Explanation

Here,

```java
this.name = name;
```

* `this.name` → Instance variable
* `name` → Constructor parameter

---

# Without `this`

```java id="nkh8oe"
class Student {

    String name;

    Student(String name) {

        name = name;

    }

}
```

Here, both `name` refer to the constructor parameter.

The instance variable is **not initialized**.

---

# Calling Methods Using `this`

A method of the current object can be called using `this`.

```java id="5ejjwo"
class Student {

    void display() {

        System.out.println("Display Method");

    }

    void show() {

        this.display();

    }

}
```

The `this` keyword is optional here because Java automatically calls methods of the current object.

---

# Calling Constructors Using `this()`

One constructor can call another constructor of the same class.

```java id="dk42pq"
class Student {

    Student() {

        this("Amay");

        System.out.println("Default Constructor");

    }

    Student(String name) {

        System.out.println(name);

    }

}
```

### Output

```text id="1mwrmt"
Amay
Default Constructor
```

### Rules

* `this()` must be the **first statement** in the constructor.
* Used only for constructor chaining.

---

# Returning the Current Object

A method can return the current object using `this`.

```java id="jgb0vz"
class Student {

    Student getObject() {

        return this;

    }

}
```

This is commonly used in **method chaining**.

---

# Passing the Current Object as an Argument

The current object can be passed as an argument to another method.

```java id="xj5wfm"
class Student {

    void display(Student s) {

        System.out.println("Object Received");

    }

    void show() {

        display(this);

    }

}
```

---

# Passing the Current Object to a Constructor

```java id="skh0pi"
class Demo {

    Demo(Student s) {

        System.out.println("Student Object Received");

    }

}

class Student {

    void send() {

        Demo d = new Demo(this);

    }

}
```

---

# `this` vs Local Variable

```java
class Student {

    String name;

    Student(String name) {

        this.name = name;

    }

}
```

| Expression  | Refers To             |
| ----------- | --------------------- |
| `name`      | Constructor parameter |
| `this.name` | Instance variable     |

---

# When Can We Use `this`?

The `this` keyword can be used to:

* Refer to the current object's instance variable.
* Call another method of the current object.
* Call another constructor using `this()`.
* Pass the current object as a method argument.
* Pass the current object to a constructor.
* Return the current object.

---

# Important Points

* `this` refers to the current object.
* `this()` is used for constructor chaining.
* `this` cannot be used inside a static method.
* `this()` must always be the first statement inside a constructor.

---

# Common Mistakes

## Forgetting `this`

❌ Incorrect

```java id="ek15r7"
class Student {

    String name;

    Student(String name) {

        name = name;

    }

}
```

The instance variable remains uninitialized.

✔ Correct

```java id="3fyjlwm"
this.name = name;
```

---

## Using `this` Inside a Static Method

❌ Incorrect

```java id="b0gkdt"
static void show() {

    System.out.println(this);

}
```

This causes a compilation error because static methods belong to the class, not to any object.

---

## Calling `this()` After Another Statement

❌ Incorrect

```java id="i79r6u"
Student() {

    System.out.println("Hello");

    this("Amay");

}
```

✔ Correct

```java id="ykqfut"
Student() {

    this("Amay");

    System.out.println("Hello");

}
```

---

# Interview Notes

### What is the `this` Keyword?

The `this` keyword is a reference to the current object of a class.

---

### Can We Use `this` in a Static Method?

No.

Static methods belong to the class and do not have a current object.

---

### What is Constructor Chaining?

Constructor chaining is the process of calling one constructor from another constructor of the same class using `this()`.

---

### Difference Between `this` and `this()`

| `this`                          | `this()`                                    |
| ------------------------------- | ------------------------------------------- |
| Refers to the current object    | Calls another constructor in the same class |
| Used with variables and methods | Used only inside constructors               |

---

# Summary

* `this` refers to the current object.
* It is mainly used to distinguish instance variables from local variables.
* `this()` is used to call another constructor in the same class.
* `this` can also be used to call methods, return the current object, and pass the current object as an argument.
* `this` cannot be used in static methods.
