# Arrays in Java

An array is a collection of elements of the same data type stored in contiguous memory locations. Each element is accessed using an index.

---

# Why Use Arrays?

Without arrays, we need separate variables to store multiple values.

Example without an array:

```java
int mark1 = 80;
int mark2 = 75;
int mark3 = 90;
```

Using an array:

```java
int[] marks = {80, 75, 90};
```

Arrays make programs shorter, easier to manage, and suitable for handling large amounts of data.

---

# Features of Arrays

* Stores multiple values of the same data type.
* Elements are stored in contiguous memory.
* Array size is fixed after creation.
* Indexing starts from **0**.
* Supports random access using index.

---

# Array Declaration

### Syntax

```java
dataType[] arrayName;
```

### Example

```java
int[] numbers;
String[] names;
```

---

# Array Creation

### Syntax

```java
arrayName = new dataType[size];
```

### Example

```java
int[] numbers = new int[5];
```

This creates an array capable of storing **5 integers**.

---

# Array Initialization

Arrays can be initialized while creating them.

```java
int[] numbers = {10, 20, 30, 40, 50};
```

---

# Accessing Array Elements

Each element is accessed using its index.

```java
int[] numbers = {10, 20, 30};

System.out.println(numbers[0]);
System.out.println(numbers[2]);
```

### Output

```text
10
30
```

---

# Updating Array Elements

Values inside an array can be modified using their index.

```java
int[] numbers = {10, 20, 30};

numbers[1] = 100;

System.out.println(numbers[1]);
```

### Output

```text
100
```

---

# Traversing an Array

Arrays are commonly traversed using loops.

### Using `for` Loop

```java
int[] numbers = {10, 20, 30, 40};

for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
}
```

---

### Using Enhanced `for` Loop

```java
int[] numbers = {10, 20, 30, 40};

for (int num : numbers) {
    System.out.println(num);
}
```

---

# Array Length

The `length` property returns the total number of elements in an array.

```java
int[] numbers = {10, 20, 30};

System.out.println(numbers.length);
```

### Output

```text
3
```

---

# Types of Arrays

## One-Dimensional Array

Stores data in a single row.

```java
int[] numbers = {10, 20, 30};
```

---

## Two-Dimensional Array

Stores data in rows and columns.

```java
int[][] matrix = {
    {1, 2},
    {3, 4}
};
```

Accessing an element:

```java
System.out.println(matrix[1][0]);
```

### Output

```text
3
```

---

# Default Values in Arrays

| Data Type | Default Value |
| --------- | ------------- |
| byte      | 0             |
| short     | 0             |
| int       | 0             |
| long      | 0L            |
| float     | 0.0f          |
| double    | 0.0           |
| char      | '\u0000'      |
| boolean   | false         |
| Object    | null          |

---

# Common Array Operations

* Insert elements
* Update elements
* Traverse elements
* Search elements
* Sort elements
* Reverse elements

These operations are widely used in Data Structures and Algorithms (DSA).

---

# Important Points

* Arrays store elements of the same data type.
* Array indexing starts from **0**.
* The size of an array cannot be changed after creation.
* Arrays are objects in Java.
* Use the `length` property to get the array size.

---

# Common Mistakes

## Accessing an Invalid Index

```java
int[] numbers = {10, 20, 30};

System.out.println(numbers[5]);
```

This throws an `ArrayIndexOutOfBoundsException`.

---

## Confusing `length` with `length()`

Correct:

```java
numbers.length
```

Incorrect:

```java
numbers.length()
```

Arrays use the `length` property, while strings use the `length()` method.

---

# Interview Notes

### Why Does Array Indexing Start from 0?

Array indexing starts from 0 because the first element is stored at the base memory address. This makes element access efficient.

---

### Can We Change the Size of an Array?

No. Once an array is created, its size is fixed. To store more elements, create a new array or use a dynamic collection like `ArrayList`.

---

### Difference Between Array and ArrayList

| Array                 | ArrayList      |
| --------------------- | -------------- |
| Fixed size            | Dynamic size   |
| Stores same data type | Stores objects |
| Faster                | More flexible  |

---

# Summary

* An array stores multiple values of the same data type.
* Elements are accessed using indexes starting from 0.
* Arrays have a fixed size after creation.
* Use loops to traverse arrays.
* Arrays are one of the most important data structures in Java and are the foundation of DSA.

