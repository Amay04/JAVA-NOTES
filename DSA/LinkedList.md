# Singly Linked List in Java

## What is a Linked List?

A **Linked List** is a linear data structure where elements (called **nodes**) are stored in **non-contiguous memory locations**.

Each node contains:

* Data
* Reference (Pointer) to the next node

Unlike arrays, linked lists do not require contiguous memory.

---

# Structure of a Node

```text
+--------+---------+
|  Data  |  Next   |
+--------+---------+
```

Example:

```text
Head
 ↓
+----+------+    +----+------+    +----+------+
| 10 |   •-------->20 |   •-------->30 | NULL |
+----+------+    +----+------+    +----+------+
```

---

# Java Node Class

```java
class Node {

    int data;
    Node next;

    Node(int data) {
        this.data = data;
        this.next = null;
    }

}
```

## Explanation

* `int data` stores the value.
* `Node next` stores the address of the next node.
* Constructor initializes the node with the given value.

---

# Linked List Class

```java
class LinkedList {

    Node head;

}
```

## Explanation

`head` stores the address of the first node.

Initially:

```text
head
 ↓
NULL
```

---

# Creating the First Node

```java
public class Main {

    public static void main(String[] args) {

        LinkedList list = new LinkedList();

        list.head = new Node(10);

    }

}
```

Memory:

```text
Head
 ↓
+----+------+
| 10 | NULL |
+----+------+
```

---

# Traversing a Linked List

Traversal means visiting every node one by one.

## Code

```java
void display() {

    Node temp = head;

    while (temp != null) {

        System.out.print(temp.data + " ");

        temp = temp.next;

    }

}
```

### Dry Run

```text
Head

↓

10 → 20 → 30 → NULL
```

Output

```text
10 20 30
```

---

# Insert at Beginning

Before

```text
10 → 20 → 30
```

After inserting **5**

```text
5 → 10 → 20 → 30
```

## Code

```java
void insertFirst(int data) {

    Node newNode = new Node(data);

    newNode.next = head;

    head = newNode;

}
```

### Explanation

1. Create a new node.
2. Make its `next` point to the current head.
3. Update `head` to the new node.

---

# Insert at End

Before

```text
10 → 20 → 30
```

After inserting **40**

```text
10 → 20 → 30 → 40
```

## Code

```java
void insertLast(int data) {

    Node newNode = new Node(data);

    if (head == null) {

        head = newNode;
        return;

    }

    Node temp = head;

    while (temp.next != null) {

        temp = temp.next;

    }

    temp.next = newNode;

}
```

### Explanation

* Traverse to the last node.
* Attach the new node at the end.

---

# Insert at Position

Before

```text
10 → 20 → 40
```

Insert **30** at position **3**

After

```text
10 → 20 → 30 → 40
```

## Code

```java
void insertPosition(int position, int data) {

    if (position == 1) {

        insertFirst(data);
        return;

    }

    Node newNode = new Node(data);

    Node temp = head;

    for (int i = 1; i < position - 1; i++) {

        temp = temp.next;

    }

    newNode.next = temp.next;

    temp.next = newNode;

}
```

---

# Delete First Node

Before

```text
10 → 20 → 30
```

After

```text
20 → 30
```

## Code

```java
void deleteFirst() {

    if (head == null)
        return;

    head = head.next;

}
```

---

# Delete Last Node

Before

```text
10 → 20 → 30
```

After

```text
10 → 20
```

## Code

```java
void deleteLast() {

    if (head == null)
        return;

    if (head.next == null) {

        head = null;
        return;

    }

    Node temp = head;

    while (temp.next.next != null) {

        temp = temp.next;

    }

    temp.next = null;

}
```

---

# Search an Element

## Code

```java
boolean search(int key) {

    Node temp = head;

    while (temp != null) {

        if (temp.data == key)
            return true;

        temp = temp.next;

    }

    return false;

}
```

---

# Count Nodes

## Code

```java
int count() {

    int count = 0;

    Node temp = head;

    while (temp != null) {

        count++;

        temp = temp.next;

    }

    return count;

}
```

---

# Reverse a Linked List

Before

```text
10 → 20 → 30
```

After

```text
30 → 20 → 10
```

## Code

```java
void reverse() {

    Node prev = null;
    Node current = head;
    Node next = null;

    while (current != null) {

        next = current.next;
        current.next = prev;
        prev = current;
        current = next;

    }

    head = prev;

}
```

---

# Find the Middle Node

Uses the **Fast and Slow Pointer** technique.

## Code

```java
Node middle() {

    Node slow = head;
    Node fast = head;

    while (fast != null && fast.next != null) {

        slow = slow.next;
        fast = fast.next.next;

    }

    return slow;

}
```

---

# Detect a Cycle

Uses **Floyd's Cycle Detection Algorithm**.

## Code

```java
boolean hasCycle() {

    Node slow = head;
    Node fast = head;

    while (fast != null && fast.next != null) {

        slow = slow.next;
        fast = fast.next.next;

        if (slow == fast)
            return true;

    }

    return false;

}
```

---

# Time Complexity

| Operation             | Complexity |
| --------------------- | ---------- |
| Traversal             | O(n)       |
| Search                | O(n)       |
| Insert at Beginning   | O(1)       |
| Insert at End         | O(n)       |
| Insert at Position    | O(n)       |
| Delete from Beginning | O(1)       |
| Delete from End       | O(n)       |
| Delete from Position  | O(n)       |
| Reverse               | O(n)       |
| Find Middle           | O(n)       |
| Detect Cycle          | O(n)       |

---

# Applications

* Stack Implementation
* Queue Implementation
* Browser History
* Music Playlist
* HashMap Chaining
* Graph Adjacency List
* LRU Cache
* Memory Management

---

# Common Interview Questions

* Reverse a Linked List
* Find the Middle Node
* Detect a Cycle
* Merge Two Sorted Linked Lists
* Remove Nth Node from End
* Reverse Nodes in K Groups
* Check if Linked List is Palindrome
* Find the Intersection of Two Linked Lists

---

# Summary

* A Linked List is a dynamic linear data structure.
* Each node stores **data** and a **reference to the next node**.
* It allows efficient insertion and deletion.
* Random access is not possible.
* Singly Linked Lists are the foundation for learning Doubly and Circular Linked Lists.
