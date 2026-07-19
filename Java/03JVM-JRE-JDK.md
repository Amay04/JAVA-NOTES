# Operators in Java

Operators are symbols that perform operations on variables and values.

Example:

```java
int sum = 10 + 20;
```

Here, `+` is an operator used to add two numbers.

---

# Table of Contents

1. What are Operators?
2. Arithmetic Operators
3. Unary Operators
4. Assignment Operators
5. Relational Operators
6. Logical Operators
7. Bitwise Operators
8. Shift Operators
9. Ternary Operator
10. Operator Precedence
11. Examples
12. Common Mistakes
13. Interview Tips
14. Quick Revision

---

# 1. What are Operators?

Operators are special symbols used to perform operations on operands (variables or values).

Example:

```java
int a = 10;
int b = 20;
int sum = a + b;
```

* `a` and `b` are operands.
* `+` is the operator.

---

# 2. Arithmetic Operators

These operators perform mathematical calculations.

| Operator | Description         | Example |
| -------- | ------------------- | ------- |
| +        | Addition            | `a + b` |
| -        | Subtraction         | `a - b` |
| *        | Multiplication      | `a * b` |
| /        | Division            | `a / b` |
| %        | Modulus (Remainder) | `a % b` |

### Example

```java
public class Main {
    public static void main(String[] args) {

        int a = 15;
        int b = 4;

        System.out.println(a + b);
        System.out.println(a - b);
        System.out.println(a * b);
        System.out.println(a / b);
        System.out.println(a % b);

    }
}
```

### Output

```
19
11
60
3
3
```

---

# 3. Unary Operators

Unary operators work on a single operand.

| Operator | Description |
| -------- | ----------- |
| +        | Unary Plus  |
| -        | Unary Minus |
| ++       | Increment   |
| --       | Decrement   |
| !        | Logical NOT |

### Increment

```java
int x = 5;
x++;
System.out.println(x);
```

Output

```
6
```

### Decrement

```java
int x = 5;
x--;
System.out.println(x);
```

Output

```
4
```

---

## Pre-Increment vs Post-Increment

### Pre-Increment

```java
int a = 5;
System.out.println(++a);
```

Output

```
6
```

---

### Post-Increment

```java
int a = 5;
System.out.println(a++);
System.out.println(a);
```

Output

```
5
6
```

---

# 4. Assignment Operators

Used to assign values to variables.

| Operator | Example  |
| -------- | -------- |
| =        | `a = 10` |
| +=       | `a += 5` |
| -=       | `a -= 5` |
| *=       | `a *= 2` |
| /=       | `a /= 2` |
| %=       | `a %= 2` |

Example

```java
int x = 10;

x += 5;

System.out.println(x);
```

Output

```
15
```

---

# 5. Relational Operators

Used to compare two values.

| Operator | Meaning               |
| -------- | --------------------- |
| ==       | Equal to              |
| !=       | Not Equal to          |
| >        | Greater than          |
| <        | Less than             |
| >=       | Greater than or Equal |
| <=       | Less than or Equal    |

Example

```java
int a = 10;
int b = 20;

System.out.println(a < b);
```

Output

```
true
```

---

# 6. Logical Operators

Used with boolean values.

| Operator | Meaning     |   |            |
| -------- | ----------- | - | ---------- |
| &&       | Logical AND |   |            |
|          |             |   | Logical OR |
| !        | Logical NOT |   |            |

Example

```java
boolean a = true;
boolean b = false;

System.out.println(a && b);
System.out.println(a || b);
System.out.println(!a);
```

Output

```
false
true
false
```

---

# 7. Bitwise Operators

Operate on binary values.

| Operator | Meaning     |
| -------- | ----------- |
| &        | Bitwise AND |
| |        | Bitwise OR  |
| ^        | XOR         |
| ~        | Complement  |

Example

```java
int a = 5;
int b = 3;

System.out.println(a & b);
System.out.println(a | b);
System.out.println(a ^ b);
```

Output

```
1
7
6
```

---

# 8. Shift Operators

| Operator | Description          |
| -------- | -------------------- |
| <<       | Left Shift           |
| >>       | Right Shift          |
| >>>      | Unsigned Right Shift |

Example

```java
System.out.println(5 << 1);
System.out.println(10 >> 1);
```

Output

```
10
5
```

---

# 9. Ternary Operator

A shorthand for `if-else`.

### Syntax

```java
condition ? value1 : value2;
```

Example

```java
int age = 18;

String result = (age >= 18) ? "Adult" : "Minor";

System.out.println(result);
```

Output

```
Adult
```

---

# 10. Operator Precedence

Higher precedence operators are evaluated first.

| Priority | Operators   |   |   |
| -------- | ----------- | - | - |
| Highest  | `()`        |   |   |
|          | `++ -- !`   |   |   |
|          | `* / %`     |   |   |
|          | `+ -`       |   |   |
|          | `< <= > >=` |   |   |
|          | `== !=`     |   |   |
|          | `&&`        |   |   |
|          | `           |   | ` |
| Lowest   | `=`         |   |   |

Example

```java
int result = 10 + 5 * 2;
```

Output

```
20
```

---

# 11. Practice Example

```java
public class Main {

    public static void main(String[] args) {

        int a = 10;
        int b = 5;

        System.out.println(a + b);
        System.out.println(a > b);
        System.out.println(a == b);

        a += 5;

        System.out.println(a);

    }

}
```

Output

```
15
true
false
15
```

---

# Common Mistakes

### Using `=` instead of `==`

❌ Incorrect

```java
if (a = 10)
```

✔ Correct

```java
if (a == 10)
```

---

### Confusing `&&` and `&`

* `&&` performs **short-circuit evaluation**.
* `&` always evaluates both operands.

---

### Integer Division

```java
System.out.println(10 / 3);
```

Output

```
3
```

To get a decimal result:

```java
System.out.println(10.0 / 3);
```

Output

```
3.3333333333333335
```

---

# Interview Tips

* `%` returns the remainder.
* `++i` increments first, then uses the value.
* `i++` uses the current value, then increments.
* `&&` is preferred over `&` for logical conditions.
* The ternary operator is a concise alternative to simple `if-else` statements.

---

# Quick Revision

* Operators perform operations on operands.
* Arithmetic operators are used for calculations.
* Relational operators return `true` or `false`.
* Logical operators combine boolean expressions.
* Bitwise operators work at the binary level.
* Shift operators move bits left or right.
* The ternary operator is a shorthand for `if-else`.
* Understanding operator precedence helps avoid unexpected results.
