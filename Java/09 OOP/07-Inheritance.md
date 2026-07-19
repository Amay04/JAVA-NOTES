# Inheritance in Java

Inheritance is one of the four pillars of Object-Oriented Programming (OOP). It allows one class to acquire the properties (variables) and behaviors (methods) of another class.

The class that provides the properties and methods is called the **Parent (Superclass)**, and the class that inherits them is called the **Child (Subclass)**.

---

# Why Use Inheritance?

Without inheritance, common code has to be written repeatedly in different classes.

Inheritance helps to:

* Reuse existing code.
* Reduce code duplication.
* Improve maintainability.
* Build hierarchical relationships between classes.
* Support method overriding and runtime polymorphism.

---

# Syntax

Inheritance is implemented using the `extends` keyword.

```java
class Parent {

}

class Child extends Parent {

}
```

---

# Basic Example

```java
class Animal {

    void eat() {

        System.out.println("Animal is eating.");

    }

}

class Dog extends Animal {

    void bark() {

        System.out.println("Dog is barking.");

    }

}

public class Main {

    public static void main(String[] args) {

        Dog d = new Dog();

        d.eat();
        d.bark();

    }

}
```

### Output

```text
Animal is eating.
Dog is barking.
```

The `Dog` class inherits the `eat()` method from the `Animal` class.

---

# Parent Class (Superclass)

The class whose members are inherited is called the **Parent Class** or **Superclass**.

```java
class Animal {

}
```

---

# Child Class (Subclass)

The class that inherits from another class is called the **Child Class** or **Subclass**.

```java
class Dog extends Animal {

}
```

---

# Types of Inheritance in Java

## 1. Single Inheritance

One child class inherits from one parent class.

```text
Animal
   │
   ▼
 Dog
```

---

## 2. Multilevel Inheritance

A class inherits from another child class.

```text
Animal
   │
   ▼
 Dog
   │
   ▼
 Puppy
```

---

## Example

```java
class Animal {

    void eat() {

        System.out.println("Eating");

    }

}

class Dog extends Animal {

}

class Puppy extends Dog {

}

public class Main {

    public static void main(String[] args) {

        Puppy p = new Puppy();

        p.eat();

    }

}
```

### Output

```text
Eating
```

---

## 3. Hierarchical Inheritance

Multiple child classes inherit from the same parent class.

```text
        Animal
       /      \
      ▼        ▼
    Dog      Cat
```

---

## Example

```java
class Animal {

    void eat() {

        System.out.println("Eating");

    }

}

class Dog extends Animal {

}

class Cat extends Animal {

}
```

Both `Dog` and `Cat` inherit the `eat()` method.

---

## Multiple Inheritance

Java **does not support multiple inheritance using classes**.

❌ Not Allowed

```java
class A {

}

class B {

}

class C extends A, B {

}
```

Reason:

It may cause ambiguity (Diamond Problem).

Java supports multiple inheritance using **interfaces**, not classes.

---

# `super` Keyword

The `super` keyword refers to the parent class.

It is used to:

* Access parent class variables.
* Call parent class methods.
* Invoke the parent class constructor.

---

## Calling Parent Method

```java
class Animal {

    void sound() {

        System.out.println("Animal Sound");

    }

}

class Dog extends Animal {

    void sound() {

        super.sound();

        System.out.println("Dog Bark");

    }

}

public class Main {

    public static void main(String[] args) {

        Dog d = new Dog();

        d.sound();

    }

}
```

### Output

```text
Animal Sound
Dog Bark
```

---

## Calling Parent Constructor

```java
class Animal {

    Animal() {

        System.out.println("Animal Constructor");

    }

}

class Dog extends Animal {

    Dog() {

        super();

        System.out.println("Dog Constructor");

    }

}
```

### Output

```text
Animal Constructor
Dog Constructor
```

If `super()` is not written explicitly, Java automatically inserts it as the first statement in the child constructor.

---

# Method Overriding

A child class can provide its own implementation of a parent class method.

```java
class Animal {

    void sound() {

        System.out.println("Animal Sound");

    }

}

class Dog extends Animal {

    @Override
    void sound() {

        System.out.println("Bark");

    }

}
```

This is called **Method Overriding**.

---

# Advantages of Inheritance

* Code reusability
* Easier maintenance
* Reduces duplicate code
* Supports runtime polymorphism
* Creates logical class relationships

---

# Important Points

* Inheritance is implemented using `extends`.
* Java supports single, multilevel, and hierarchical inheritance using classes.
* Java does not support multiple inheritance with classes.
* Every class in Java directly or indirectly inherits from the `Object` class.
* Constructors are not inherited.
* Private members are not directly accessible in child classes.

---

# Common Mistakes

## Trying Multiple Inheritance

❌ Incorrect

```java
class A {

}

class B {

}

class C extends A, B {

}
```

Java does not allow this.

---

## Accessing Private Members

```java
class Animal {

    private int age = 5;

}

class Dog extends Animal {

    void show() {

        System.out.println(age);

    }

}
```

Private members cannot be accessed directly in child classes.

---

## Forgetting `super()` Must Be First

❌ Incorrect

```java
Dog() {

    System.out.println("Dog");

    super();

}
```

✔ Correct

```java
Dog() {

    super();

    System.out.println("Dog");

}
```

---

# Interview Notes

### What is Inheritance?

Inheritance is the process of acquiring the properties and methods of another class.

---

### Which Keyword is Used for Inheritance?

The `extends` keyword.

---

### Why Doesn't Java Support Multiple Inheritance Through Classes?

To avoid ambiguity, also known as the **Diamond Problem**.

---

### Can Constructors Be Inherited?

No.

Constructors are not inherited, but they can be called using `super()`.

---

### Which Class is the Parent of All Classes in Java?

The `Object` class.

---

# Summary

* Inheritance allows one class to reuse the properties and methods of another class.
* It is implemented using the `extends` keyword.
* Java supports single, multilevel, and hierarchical inheritance.
* The `super` keyword is used to access parent class members and constructors.
* Method overriding allows a child class to provide its own implementation of a parent class method.
* Inheritance improves code reusability and maintainability.
