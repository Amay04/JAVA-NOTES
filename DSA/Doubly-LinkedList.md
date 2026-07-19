# Doubly Linked List in Java

## What is a Doubly Linked List?

A **Doubly Linked List (DLL)** is a linear data structure in which each node contains:

* Data
* Reference to the previous node (`prev`)
* Reference to the next node (`next`)

Unlike a Singly Linked List, a Doubly Linked List allows traversal in **both forward and backward directions**.

---

# Structure of a Node

```text
+------+-------+-------+
| Prev | Data  | Next  |
+------+-------+-------+
```

Example

```text
NULL <- [10] <-> [20] <-> [30] -> NULL
```

---

# Java Node Class

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

# Linked List Class

```java
class DoublyLinkedList {

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

## Code

```java
void displayForward() {

    Node temp = head;

    while (temp != null) {

        System.out.print(temp.data + " ");

        temp = temp.next;

    }

}
```

Output

```text
10 20 30
```

---

# Backward Traversal

## Code

```java
void displayBackward() {

    if (head == null)
        return;

    Node temp = head;

    while (temp.next != null) {

        temp = temp.next;

    }

    while (temp != null) {

        System.out.print(temp.data + " ");

        temp = temp.prev;

    }

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
10 <-> 20 <-> 30
```

After

```text
5 <-> 10 <-> 20 <-> 30
```

## Code

```java
void insertFirst(int data) {

    Node newNode = new Node(data);

    if (head != null)
        head.prev = newNode;

    newNode.next = head;

    head = newNode;

}
```

---

# Insert at End

Before

```text
10 <-> 20 <-> 30
```

After

```text
10 <-> 20 <-> 30 <-> 40
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

    newNode.prev = temp;

}
```

---

# Insert at Position

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

    if (temp.next != null)
        temp.next.prev = newNode;

    temp.next = newNode;

    newNode.prev = temp;

}
```

---

# Delete First Node

Before

```text
10 <-> 20 <-> 30
```

After

```text
20 <-> 30
```

## Code

```java
void deleteFirst() {

    if (head == null)
        return;

    head = head.next;

    if (head != null)
        head.prev = null;

}
```

---

# Delete Last Node

Before

```text
10 <-> 20 <-> 30
```

After

```text
10 <-> 20
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

    while (temp.next != null) {

        temp = temp.next;

    }

    temp.prev.next = null;

}
```

---

# Delete at Position

## Code

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

    if (temp.next != null)
        temp.next.prev = temp.prev;

}
```

---

# Search an Element

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

# Reverse a Doubly Linked List

```java
void reverse() {

    Node current = head;
    Node temp = null;

    while (current != null) {

        temp = current.prev;
        current.prev = current.next;
        current.next = temp;

        current = current.prev;

    }

    if (temp != null)
        head = temp.prev;

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

---

# Advantages

* Traverse in both directions.
* Easier insertion and deletion.
* Efficient reverse traversal.
* Better for navigation-based applications.

---

# Disadvantages

* Requires extra memory for the `prev` pointer.
* More pointer updates than a Singly Linked List.
* Slightly more complex implementation.

---

# Applications

* Browser Back & Forward navigation
* Undo/Redo functionality
* Music Playlist
* Image Viewer
* LRU Cache

---

# Linked List vs Doubly Linked List

| Singly Linked List             | Doubly Linked List           |
| ------------------------------ | ---------------------------- |
| One pointer                    | Two pointers                 |
| Forward traversal only         | Forward & Backward traversal |
| Less memory                    | More memory                  |
| Simpler                        | More complex                 |
| Reverse traversal is difficult | Reverse traversal is easy    |

---

# Common Interview Questions

* Reverse a Doubly Linked List
* Insert after a given node
* Delete a given node
* Find pairs with a given sum
* Convert DLL to BST
* Flatten a Multilevel Doubly Linked List

---

# Summary

* A Doubly Linked List stores **previous** and **next** pointers.
* It supports traversal in both directions.
* Insertion and deletion are easier than in a Singly Linked List because the previous node is directly accessible.
* It is commonly used in browser history, playlists, and undo/redo systems.
