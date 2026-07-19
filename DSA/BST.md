# Binary Search Tree (BST) in Java

## What is a Binary Search Tree?

A **Binary Search Tree (BST)** is a special type of Binary Tree in which every node follows the BST property.

### BST Property

* All nodes in the **left subtree** are **smaller** than the current node.
* All nodes in the **right subtree** are **greater** than the current node.
* Both left and right subtrees are also Binary Search Trees.

---

# Example

```text
             50
           /    \
         30      70
        /  \    /  \
      20   40  60   80
```

Notice:

* Left of 50 → 30,20,40 (All Smaller)
* Right of 50 → 70,60,80 (All Greater)

---

# Why Use BST?

BST provides faster searching compared to a normal Binary Tree.

Applications:

* Dictionary
* Phonebook
* Database Indexing
* Leaderboards
* Search Engines
* File Systems

---

# BST Node

```java
class Node {

    int data;
    Node left;
    Node right;

    Node(int data){

        this.data = data;
        left = null;
        right = null;

    }

}
```

---

# BST Class

```java
class BinarySearchTree{

    Node root;

}
```

Initially

```text
root

↓

NULL
```

---

# Creating a BST

Suppose we insert:

```text
50
30
70
20
40
60
80
```

The tree becomes

```text
             50
           /    \
         30      70
        /  \    /  \
      20   40  60   80
```

---

# Insert Operation

## Logic

Start from the root.

* If value is smaller → Go Left
* If value is greater → Go Right
* Repeat until NULL
* Create a new node

---

# Insert Algorithm

```text
If root is NULL

    Create Node

Else

    If data < root.data

         Insert Left

    Else

         Insert Right
```

---

# Java Code

```java
class BinarySearchTree {

    Node root;

    Node insert(Node root, int data){

        if(root == null){

            return new Node(data);

        }

        if(data < root.data){

            root.left = insert(root.left, data);

        }

        else if(data > root.data){

            root.right = insert(root.right, data);

        }

        return root;

    }

}
```

---

# Dry Run

Insert

```text
50
```

Tree

```text
50
```

Insert

```text
30
```

30 < 50

Go Left

```text
      50
     /
   30
```

Insert

```text
70
```

70 > 50

Go Right

```text
      50
     /  \
   30   70
```

Insert

```text
20
```

20 < 50

↓

20 < 30

↓

Left

```text
        50
       /  \
     30   70
    /
  20
```

Continue similarly for

```text
40

60

80
```

Final Tree

```text
             50
           /    \
         30      70
        /  \    /  \
      20   40  60   80
```

---

# Search Operation

## Logic

Compare the value with the current node.

* Equal → Found
* Smaller → Search Left
* Greater → Search Right

---

# Algorithm

```text
If root == NULL

    Not Found

If root.data == key

    Found

If key < root.data

    Search Left

Else

    Search Right
```

---

# Java Code

```java
boolean search(Node root, int key){

    if(root == null)

        return false;

    if(root.data == key)

        return true;

    if(key < root.data)

        return search(root.left, key);

    return search(root.right, key);

}
```

---

# Dry Run

Search

```text
60
```

Current

```text
50
```

60 > 50

↓

Go Right

```text
70
```

60 < 70

↓

Go Left

```text
60
```

Found

Output

```text
true
```

---

# Traversals in BST

Traversal is the same as a Binary Tree.

---

## Inorder Traversal

```java
void inorder(Node root){

    if(root == null)
        return;

    inorder(root.left);

    System.out.print(root.data + " ");

    inorder(root.right);

}
```

Output

```text
20 30 40 50 60 70 80
```

### Important

**Inorder Traversal of a BST always gives the elements in sorted order.**

---

## Preorder Traversal

```java
void preorder(Node root){

    if(root == null)
        return;

    System.out.print(root.data + " ");

    preorder(root.left);

    preorder(root.right);

}
```

Output

```text
50 30 20 40 70 60 80
```

---

## Postorder Traversal

```java
void postorder(Node root){

    if(root == null)
        return;

    postorder(root.left);

    postorder(root.right);

    System.out.print(root.data + " ");

}
```

Output

```text
20 40 30 60 80 70 50
```

---

## Level Order Traversal

```java
import java.util.*;

void levelOrder(Node root){

    if(root == null)
        return;

    Queue<Node> queue = new LinkedList<>();

    queue.offer(root);

    while(!queue.isEmpty()){

        Node current = queue.poll();

        System.out.print(current.data + " ");

        if(current.left != null)
            queue.offer(current.left);

        if(current.right != null)
            queue.offer(current.right);

    }

}
```

Output

```text
50 30 70 20 40 60 80
```

---

# Time Complexity

| Operation   | Average  | Worst |
| ----------- | -------- | ----- |
| Insert      | O(log n) | O(n)  |
| Search      | O(log n) | O(n)  |
| Inorder     | O(n)     | O(n)  |
| Preorder    | O(n)     | O(n)  |
| Postorder   | O(n)     | O(n)  |
| Level Order | O(n)     | O(n)  |

---

# Advantages

* Faster searching than Binary Tree.
* Data remains sorted.
* Easy insertion.
* Efficient searching.

---

# Disadvantages

* Can become skewed.
* Worst case becomes O(n).
* More complex than arrays.

---

# Applications

* Database Indexing
* Symbol Tables
* Search Engines
* Dictionaries
* Phonebooks
* Leaderboards

---

# Common Interview Questions

* Search in BST
* Insert into BST
* Validate BST
* Delete a Node
* Lowest Common Ancestor
* Kth Smallest Element
* Floor & Ceil
* Inorder Successor
* Inorder Predecessor

---

# Summary

* BST is a Binary Tree with an ordering property.
* Left subtree contains smaller values.
* Right subtree contains greater values.
* Searching and insertion take **O(log n)** on average.
* Inorder traversal always produces elements in sorted order.

