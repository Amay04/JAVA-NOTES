# Strings in Java

A **String** is a sequence of characters used to store and manipulate text in Java.

Unlike primitive data types, a String is an **object** of the `String` class.

---

# Why Use Strings?

Strings are used whenever we need to work with text.

Examples:

* Store a person's name
* Store an email address
* Store a password
* Display messages
* Process user input

---

# Creating Strings

There are two ways to create a String.

## 1. Using String Literal (Recommended)

```java
String name = "Amay";
```

The String is stored in the **String Pool**, which improves memory usage.

---

## 2. Using the `new` Keyword

```java
String name = new String("Amay");
```

This creates a new String object in the heap memory.

---

# String Immutability

Strings in Java are **immutable**, which means their value **cannot be changed** after creation.

Example:

```java
String name = "Java";

name = "Python";

System.out.println(name);
```

### Output

```text
Python
```

A new String object is created instead of modifying the existing one.

---

# Common String Methods

## `length()`

Returns the number of characters.

```java
String name = "Java";

System.out.println(name.length());
```

### Output

```text
4
```

---

## `charAt()`

Returns the character at a specified index.

```java
String name = "Java";

System.out.println(name.charAt(2));
```

### Output

```text
v
```

---

## `toUpperCase()`

Converts all characters to uppercase.

```java
String name = "java";

System.out.println(name.toUpperCase());
```

### Output

```text
JAVA
```

---

## `toLowerCase()`

Converts all characters to lowercase.

```java
String name = "JAVA";

System.out.println(name.toLowerCase());
```

### Output

```text
java
```

---

## `equals()`

Compares the content of two strings.

```java
String s1 = "Java";
String s2 = "Java";

System.out.println(s1.equals(s2));
```

### Output

```text
true
```

---

## `equalsIgnoreCase()`

Ignores uppercase and lowercase differences.

```java
String s1 = "JAVA";
String s2 = "java";

System.out.println(s1.equalsIgnoreCase(s2));
```

### Output

```text
true
```

---

## `contains()`

Checks whether a string contains another string.

```java
String language = "Java Programming";

System.out.println(language.contains("Java"));
```

### Output

```text
true
```

---

## `substring()`

Extracts part of a string.

```java
String language = "Programming";

System.out.println(language.substring(3, 8));
```

### Output

```text
gramm
```

---

## `replace()`

Replaces characters or words.

```java
String text = "Java";

System.out.println(text.replace("Java", "Python"));
```

### Output

```text
Python
```

---

## `trim()`

Removes leading and trailing spaces.

```java
String text = "  Java  ";

System.out.println(text.trim());
```

### Output

```text
Java
```

---

## `split()`

Splits a string into an array.

```java
String text = "Apple,Banana,Mango";

String[] fruits = text.split(",");

System.out.println(fruits[1]);
```

### Output

```text
Banana
```

---

# String Comparison

## Using `==`

Compares object references.

```java
String a = "Java";
String b = "Java";

System.out.println(a == b);
```

Output

```text
true
```

---

## Using `equals()`

Compares actual content.

```java
String a = new String("Java");
String b = new String("Java");

System.out.println(a.equals(b));
```

Output

```text
true
```

---

# StringBuilder

`StringBuilder` is used when strings need to be modified frequently.

Example:

```java
StringBuilder sb = new StringBuilder("Java");

sb.append(" Programming");

System.out.println(sb);
```

### Output

```text
Java Programming
```

---

# StringBuffer

`StringBuffer` is similar to `StringBuilder` but is **thread-safe**.

```java
StringBuffer sb = new StringBuffer("Java");

sb.append(" Notes");

System.out.println(sb);
```

---

# String vs StringBuilder vs StringBuffer

| Feature     | String                   | StringBuilder | StringBuffer    |
| ----------- | ------------------------ | ------------- | --------------- |
| Mutable     | ❌ No                     | ✅ Yes         | ✅ Yes           |
| Thread Safe | ❌ No                     | ❌ No          | ✅ Yes           |
| Performance | Slower for modifications | Faster        | Slightly Slower |

---

# Important Points

* String is an object in Java.
* Strings are immutable.
* String literals are stored in the String Pool.
* Use `equals()` to compare string content.
* Use `StringBuilder` when frequent modifications are required.

---

# Common Mistakes

## Comparing Strings Using `==`

❌ Incorrect

```java
String s1 = new String("Java");
String s2 = new String("Java");

System.out.println(s1 == s2);
```

✔ Correct

```java
System.out.println(s1.equals(s2));
```

---

## Using an Invalid Index

```java
String text = "Java";

System.out.println(text.charAt(10));
```

This throws a `StringIndexOutOfBoundsException`.

---

# Interview Notes

### Why are Strings Immutable?

Strings are immutable to improve:

* Security
* Performance
* Thread safety
* String Pool optimization

---

### Difference Between `==` and `equals()`

| `==`                | `equals()`       |
| ------------------- | ---------------- |
| Compares references | Compares content |

---

### When Should You Use StringBuilder?

Use `StringBuilder` when the string is modified frequently because it provides better performance than repeatedly creating new `String` objects.

---

# Summary

* A String is an object used to store text.
* Strings are immutable.
* Java provides many built-in methods for string manipulation.
* Use `equals()` instead of `==` to compare string content.
* Use `StringBuilder` for frequent string modifications.
* Use `StringBuffer` when thread safety is required.
