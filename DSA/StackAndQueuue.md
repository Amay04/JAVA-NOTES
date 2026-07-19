# Stack and Queue in Java

Stack and Queue are two important linear data structures used in Data Structures and Algorithms (DSA). Although both store data linearly, they differ in the order in which elements are inserted and removed.

---

# Stack

## What is a Stack?

A **Stack** is a linear data structure that follows the **LIFO (Last In, First Out)** principle.

The element inserted last is removed first.

Example:

```text
Push: 10, 20, 30

        Top
         ↓
+-----+
| 30 |
+-----+
| 20 |
+-----+
| 10 |
+-----+

Pop → 30
```

---

# Stack Operations

* Push
* Pop
* Peek (Top)
* isEmpty
* Size

---

# Push Operation

Adds an element to the top of the stack.

```java
void push(int data)
```

---

# Pop Operation

Removes the top element.

```java
int pop()
```

---

# Peek Operation

Returns the top element without removing it.

```java
int peek()
```

---

# Stack Implementation Using Array

```java
class Stack {

    int[] arr;
    int top;

    Stack(int size) {

        arr = new int[size];
        top = -1;

    }

    void push(int data) {

        arr[++top] = data;

    }

    int pop() {

        return arr[top--];

    }

    int peek() {

        return arr[top];

    }

    boolean isEmpty() {

        return top == -1;

    }

}
```

---

# Stack Implementation Using Linked List

```java
class Node {

    int data;
    Node next;

    Node(int data) {

        this.data = data;

    }

}

class Stack {

    Node top;

    void push(int data) {

        Node newNode = new Node(data);

        newNode.next = top;

        top = newNode;

    }

    void pop() {

        if (top != null)

            top = top.next;

    }

}
```

---

# Applications of Stack

* Function Call Stack
* Undo / Redo
* Browser Back Button
* Parentheses Matching
* Infix to Postfix Conversion
* Expression Evaluation
* DFS (Depth First Search)
* Backtracking

---

# Time Complexity (Stack)

| Operation | Complexity |
| --------- | ---------- |
| Push      | O(1)       |
| Pop       | O(1)       |
| Peek      | O(1)       |
| isEmpty   | O(1)       |

---

# Advantages

* Fast insertion and deletion.
* Easy implementation.
* Used in recursion and expression evaluation.

---

# Disadvantages

* No random access.
* Fixed size when implemented using arrays.

---

# Queue

## What is a Queue?

A **Queue** is a linear data structure that follows the **FIFO (First In, First Out)** principle.

The element inserted first is removed first.

Example:

```text
Front                       Rear

10 → 20 → 30 → 40

Dequeue → 10
```

---

# Queue Operations

* Enqueue
* Dequeue
* Front (Peek)
* isEmpty
* Size

---

# Enqueue

Adds an element at the rear.

```java
void enqueue(int data)
```

---

# Dequeue

Removes an element from the front.

```java
int dequeue()
```

---

# Front

Returns the first element.

```java
int front()
```

---

# Queue Implementation Using Array

```java
class Queue {

    int[] arr;
    int front;
    int rear;

    Queue(int size) {

        arr = new int[size];

        front = 0;
        rear = -1;

    }

    void enqueue(int data) {

        arr[++rear] = data;

    }

    int dequeue() {

        return arr[front++];

    }

}
```

---

# Queue Implementation Using Linked List

```java
class Node {

    int data;
    Node next;

    Node(int data) {

        this.data = data;

    }

}

class Queue {

    Node front;
    Node rear;

    void enqueue(int data) {

        Node newNode = new Node(data);

        if (rear == null) {

            front = rear = newNode;
            return;

        }

        rear.next = newNode;

        rear = newNode;

    }

    void dequeue() {

        if (front == null)
            return;

        front = front.next;

        if (front == null)

            rear = null;

    }

}
```

---

# Types of Queue

## 1. Linear Queue

```text
Front → 10 → 20 → 30 ← Rear
```

Simple queue following FIFO.

---

## 2. Circular Queue

The last position is connected to the first position.

```text
+----------------------+
|                      |
↓                      |
10 → 20 → 30 → 40
```

Avoids memory wastage.

---

## 3. Deque (Double Ended Queue)

Insertion and deletion are allowed from both ends.

```text
Front ⇄ 10 ⇄ 20 ⇄ 30 ⇄ Rear
```

Types:

* Input Restricted Deque
* Output Restricted Deque

---

## 4. Priority Queue

Elements are removed based on priority instead of insertion order.

Example:

```text
Priority

90
70
40
20
```

Highest priority is removed first.

---

# Applications of Queue

* CPU Scheduling
* Printer Queue
* BFS (Breadth First Search)
* Call Center Systems
* Ticket Booking
* Task Scheduling

---

# Time Complexity (Queue)

| Operation | Complexity |
| --------- | ---------- |
| Enqueue   | O(1)       |
| Dequeue   | O(1)       |
| Front     | O(1)       |
| isEmpty   | O(1)       |

---

# Stack vs Queue

| Stack               | Queue                          |
| ------------------- | ------------------------------ |
| LIFO                | FIFO                           |
| Insert from Top     | Insert from Rear               |
| Delete from Top     | Delete from Front              |
| One Pointer (`top`) | Two Pointers (`front`, `rear`) |
| Used in DFS         | Used in BFS                    |

---

# Common Interview Questions

## Stack

* Valid Parentheses
* Next Greater Element
* Min Stack
* Largest Rectangle in Histogram
* Stock Span Problem
* Infix to Postfix
* Evaluate Postfix Expression

---

## Queue

* Implement Queue using Stack
* Implement Stack using Queue
* Circular Queue
* First Non-Repeating Character
* Sliding Window Maximum
* Rotten Oranges
* BFS Traversal

---

# Summary

## Stack

* Follows **LIFO**.
* Insertion and deletion happen from the **top**.
* Used in recursion, expression evaluation, and backtracking.

---

## Queue

* Follows **FIFO**.
* Insertion happens at the **rear**.
* Deletion happens at the **front**.
* Used in scheduling, BFS, and task management.
