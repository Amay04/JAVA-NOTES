# Circular Linked List in Java

## What is a Circular Linked List?

A **Circular Linked List (CLL)** is a type of linked list where the **last node points back to the first node (head)** instead of pointing to `NULL`.

This creates a circular structure, allowing traversal to continue indefinitely until explicitly stopped.

---

# Structure of a Circular Linked List

Unlike a Singly Linked List:

```text
10 → 20 → 30 → NULL
```

A Circular Linked List looks like:

```text
           +-------------------+
           |                   |
           |                   |
Head       |                   |
 ↓         |                   |
10 → 20 → 30
↑           |
|___________|
```

Or,

```text
Head
 ↓
+----+------+    +----+------+    +----+------+
| 10 |   •-------->20 |   •-------->30 |   •---+
+----+------+    +----+------+    +----+------+
      ^_______________________________________|
```

---

# Node Structure

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

---

# Circular Linked List Class

```java
class CircularLinkedList {

    Node head;

}
```

Initially,

```text
head
 ↓
NULL
```

---

# Traversal

Since there is no `NULL`, we stop when we reach the `head` again.

## Code

```java
void display() {

    if (head == null)
        return;

    Node temp = head;

    do {

        System.out.print(temp.data + " ");

        temp = temp.next;

    } while (temp != head);

}
```

Example

```text
10 → 20 → 30 ↺
```

Output

```text
10 20 30
```

---

# Insert at Beginning

Before

```text
10 → 20 → 30 ↺
```

After inserting **5**

```text
5 → 10 → 20 → 30 ↺
```

## Code

```java
void insertFirst(int data) {

    Node newNode = new Node(data);

    if (head == null) {

        head = newNode;
        newNode.next = head;
        return;

    }

    Node temp = head;

    while (temp.next != head) {

        temp = temp.next;

    }

    newNode.next = head;

    temp.next = newNode;

    head = newNode;

}
```

---

# Insert at End

Before

```text
10 → 20 → 30 ↺
```

After inserting **40**

```text
10 → 20 → 30 → 40 ↺
```

## Code

```java
void insertLast(int data) {

    Node newNode = new Node(data);

    if (head == null) {

        head = newNode;
        newNode.next = head;
        return;

    }

    Node temp = head;

    while (temp.next != head) {

        temp = temp.next;

    }

    temp.next = newNode;

    newNode.next = head;

}
```

---

# Insert at Position

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
10 → 20 → 30 ↺
```

After

```text
20 → 30 ↺
```

## Code

```java
void deleteFirst() {

    if (head == null)
        return;

    if (head.next == head) {

        head = null;
        return;

    }

    Node temp = head;

    while (temp.next != head) {

        temp = temp.next;

    }

    temp.next = head.next;

    head = head.next;

}
```

---

# Delete Last Node

Before

```text
10 → 20 → 30 ↺
```

After

```text
10 → 20 ↺
```

## Code

```java
void deleteLast() {

    if (head == null)
        return;

    if (head.next == head) {

        head = null;
        return;

    }

    Node temp = head;

    while (temp.next.next != head) {

        temp = temp.next;

    }

    temp.next = head;

}
```

---

# Delete at Position

```java
void deletePosition(int position) {

    if (position == 1) {

        deleteFirst();
        return;

    }

    Node temp = head;

    for (int i = 1; i < position - 1; i++) {

        temp = temp.next;

    }

    temp.next = temp.next.next;

}
```

---

# Search an Element

```java
boolean search(int key) {

    if (head == null)
        return false;

    Node temp = head;

    do {

        if (temp.data == key)
            return true;

        temp = temp.next;

    } while (temp != head);

    return false;

}
```

---

# Count Nodes

```java
int count() {

    if (head == null)
        return 0;

    int count = 0;

    Node temp = head;

    do {

        count++;

        temp = temp.next;

    } while (temp != head);

    return count;

}
```

---

# Time Complexity

| Operation             | Complexity |
| --------------------- | ---------- |
| Traversal             | O(n)       |
| Search                | O(n)       |
| Insert at Beginning   | O(n)       |
| Insert at End         | O(n)       |
| Insert at Position    | O(n)       |
| Delete from Beginning | O(n)       |
| Delete from End       | O(n)       |
| Delete from Position  | O(n)       |
| Count Nodes           | O(n)       |

---

# Advantages

* No `NULL` pointer.
* Continuous traversal.
* Efficient for cyclic operations.
* Easy to move from the last node to the first node.

---

# Disadvantages

* More complex than a Singly Linked List.
* Traversal requires a special stopping condition.
* Risk of infinite loops if traversal is implemented incorrectly.

---

# Applications

* Round Robin CPU Scheduling
* Circular Queue
* Multiplayer Games
* Music Playlist (Loop Mode)
* Traffic Signal Systems

---

# Singly Linked List vs Circular Linked List

| Singly Linked List         | Circular Linked List                      |
| -------------------------- | ----------------------------------------- |
| Last node points to `NULL` | Last node points to `head`                |
| Traversal ends at `NULL`   | Traversal ends when reaching `head` again |
| One-way traversal          | Continuous traversal                      |

---

# Common Interview Questions

* Split a Circular Linked List into two halves.
* Detect whether a linked list is circular.
* Insert into a sorted Circular Linked List.
* Delete a node from a Circular Linked List.
* Solve the Josephus Problem using a Circular Linked List.

---

# Summary

* A Circular Linked List is a linked list where the last node points back to the first node.
* There is no `NULL` at the end of the list.
* Traversal is performed using a `do-while` loop.
* It is useful for applications involving repeated or cyclic processing, such as Round Robin Scheduling and Circular Queues.
