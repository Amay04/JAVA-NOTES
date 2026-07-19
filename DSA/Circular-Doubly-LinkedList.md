# Circular Doubly Linked List in Java

## What is a Circular Doubly Linked List?

A **Circular Doubly Linked List (CDLL)** is a type of linked list where:

* Each node has a **previous (`prev`) pointer**.
* Each node has a **next (`next`) pointer**.
* The **last node points to the first node (head)**.
* The **first node points back to the last node**.

This allows traversal in both **forward** and **backward** directions without reaching `NULL`.

---

# Structure

```text
            +---------------------------+
            |                           |
            ▼                           |
NULL ← [10] ⇄ [20] ⇄ [30]
 ▲                           ▼
 |___________________________|
```

Or more accurately:

```text
        Head
         ↓
+----+------+------+
|Prev| Data | Next |
+----+------+------+
   ▲             │
   │             ▼
+----+------+------+
|Prev| Data | Next |
+----+------+------+
   ▲             │
   │             ▼
+----+------+------+
|Prev| Data | Next |
+----+------+------+
   └───────────────┘
```

---

# Node Class

```java
class Node {

    int data;
    Node prev;
    Node next;

    Node(int data) {

        this.data = data;
        this.prev = null;
        this.next = null;

    }

}
```

---

# Circular Doubly Linked List Class

```java
class CircularDoublyLinkedList {

    Node head;

}
```

Initially

```text
head
 ↓
NULL
```

---

# Forward Traversal

```java
void displayForward() {

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
10 ⇄ 20 ⇄ 30
```

Output

```text
10 20 30
```

---

# Backward Traversal

```java
void displayBackward() {

    if (head == null)
        return;

    Node last = head.prev;

    Node temp = last;

    do {

        System.out.print(temp.data + " ");

        temp = temp.prev;

    } while (temp != last);

}
```

Output

```text
30 20 10
```

---

# Insert at Beginning

Before

```text
10 ⇄ 20 ⇄ 30
```

After inserting **5**

```text
5 ⇄ 10 ⇄ 20 ⇄ 30
```

## Code

```java
void insertFirst(int data) {

    Node newNode = new Node(data);

    if (head == null) {

        head = newNode;
        head.next = head;
        head.prev = head;
        return;

    }

    Node last = head.prev;

    newNode.next = head;
    newNode.prev = last;

    last.next = newNode;
    head.prev = newNode;

    head = newNode;

}
```

---

# Insert at End

Before

```text
10 ⇄ 20 ⇄ 30
```

After inserting **40**

```text
10 ⇄ 20 ⇄ 30 ⇄ 40
```

## Code

```java
void insertLast(int data) {

    Node newNode = new Node(data);

    if (head == null) {

        head = newNode;
        head.next = head;
        head.prev = head;
        return;

    }

    Node last = head.prev;

    newNode.next = head;
    newNode.prev = last;

    last.next = newNode;
    head.prev = newNode;

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
    newNode.prev = temp;

    temp.next.prev = newNode;
    temp.next = newNode;

}
```

---

# Delete First Node

```java
void deleteFirst() {

    if (head == null)
        return;

    if (head.next == head) {

        head = null;
        return;

    }

    Node last = head.prev;

    head = head.next;

    head.prev = last;
    last.next = head;

}
```

---

# Delete Last Node

```java
void deleteLast() {

    if (head == null)
        return;

    if (head.next == head) {

        head = null;
        return;

    }

    Node last = head.prev;

    last.prev.next = head;
    head.prev = last.prev;

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

    for (int i = 1; i < position; i++) {

        temp = temp.next;

    }

    temp.prev.next = temp.next;
    temp.next.prev = temp.prev;

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
| Forward Traversal     | O(n)       |
| Backward Traversal    | O(n)       |
| Search                | O(n)       |
| Insert at Beginning   | O(1)       |
| Insert at End         | O(1)       |
| Insert at Position    | O(n)       |
| Delete from Beginning | O(1)       |
| Delete from End       | O(1)       |
| Delete from Position  | O(n)       |
| Count Nodes           | O(n)       |

---

# Advantages

* Forward traversal.
* Backward traversal.
* No `NULL` pointer.
* Efficient insertion and deletion at both ends.
* Ideal for circular navigation.

---

# Disadvantages

* More memory required.
* Complex pointer manipulation.
* Harder to debug than other linked lists.

---

# Applications

* Browser Navigation
* Image Carousel
* Music Playlist (Loop Mode)
* Operating System Scheduling
* Round Robin Scheduling
* Undo / Redo Systems

---

# Comparison of Linked List Types

| Feature            | Singly | Doubly | Circular | Circular Doubly |
| ------------------ | ------ | ------ | -------- | --------------- |
| Next Pointer       | ✅      | ✅      | ✅        | ✅               |
| Previous Pointer   | ❌      | ✅      | ❌        | ✅               |
| Circular           | ❌      | ❌      | ✅        | ✅               |
| Forward Traversal  | ✅      | ✅      | ✅        | ✅               |
| Backward Traversal | ❌      | ✅      | ❌        | ✅               |

---

# Common Interview Questions

* Insert into a Circular Doubly Linked List.
* Delete from a Circular Doubly Linked List.
* Reverse traversal in a Circular Doubly Linked List.
* Convert a Doubly Linked List to a Circular Doubly Linked List.
* Implement an LRU Cache using a Doubly Linked List.

---

# Summary

* A Circular Doubly Linked List combines the features of a **Doubly Linked List** and a **Circular Linked List**.
* Every node has both `prev` and `next` pointers.
* The first and last nodes are connected, forming a circle.
* It supports efficient insertion, deletion, and traversal in both directions.
* It is commonly used in applications requiring continuous navigation and bidirectional movement.
