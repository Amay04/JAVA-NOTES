# Java Collections Framework (JCF)

## Definition

The **Java Collections Framework (JCF)** is a unified architecture provided by Java to store, manage, and manipulate groups of objects efficiently.

It consists of **interfaces**, **implementation classes**, and **algorithms** that provide ready-made data structures such as **List**, **Set**, **Queue**, **Deque**, and **Map**. These data structures make it easy to perform operations like adding, removing, searching, sorting, and traversing data.

Instead of creating your own data structures from scratch, the Collections Framework provides optimized and reusable implementations that improve code readability, performance, and maintainability.

---

## Components of Java Collections Framework

The Java Collections Framework consists of three main components:

### 1. Interfaces
Interfaces define the blueprint or contract for different types of collections.

Examples:
- Collection
- List
- Set
- Queue
- Deque
- Map

---

### 2. Implementation Classes

Implementation classes provide the actual implementation of the interfaces.

Examples:
- ArrayList
- LinkedList
- Vector
- Stack
- HashSet
- LinkedHashSet
- TreeSet
- PriorityQueue
- ArrayDeque
- HashMap
- LinkedHashMap
- TreeMap
- Hashtable

---

### 3. Algorithms

The framework provides built-in algorithms through the `Collections` class.

Examples:
- Sorting
- Searching
- Reversing
- Shuffling
- Swapping
- Finding Maximum/Minimum

---

## Advantages of Java Collections Framework

- Dynamic size (unlike arrays)
- Ready-made data structures
- Easy insertion and deletion
- Built-in searching and sorting
- Better performance
- Reusable and maintainable code
- Reduces development time

---

## Collection Framework Hierarchy

```text
                Iterable
                    |
               Collection
          __________|__________
         |          |          |
       List        Set       Queue
         |          |          |
 ArrayList      HashSet    PriorityQueue
 LinkedList     LinkedHashSet
 Vector         TreeSet
 Stack

             Map (Separate Interface)
                    |
        ___________________________
       |            |             |
    HashMap    LinkedHashMap    TreeMap
                                 Hashtable
```

> **Note:** `Map` is part of the Java Collections Framework but **does not extend the Collection interface**.

# List Interface

## Definition

A **List** is an interface in the Java Collections Framework that represents an **ordered collection of elements**.

A List stores elements in the order they are inserted, allows duplicate elements, and provides **index-based access**, making it easy to retrieve, update, insert, or remove elements using their position.

### Features
- Maintains insertion order.
- Allows duplicate elements.
- Supports index-based access.
- Allows multiple `null` values.
- Dynamic in size.

---

# Types of List

The `List` interface has four main implementations:

1. ArrayList
2. LinkedList
3. Vector
4. Stack

---

# 1. ArrayList

## Definition

`ArrayList` is a resizable array implementation of the `List` interface. It stores elements in a dynamic array whose size grows automatically when needed.

### Features
- Fast random access (`get()`).
- Dynamic size.
- Allows duplicates.
- Maintains insertion order.
- Not synchronized.

### Example

```java
import java.util.*;

public class ArrayListExample {
    public static void main(String[] args) {

        ArrayList<String> list = new ArrayList<>();

        list.add("Java");
        list.add("Python");
        list.add("Java");

        System.out.println(list);
    }
}
```

**Output**

```
[Java, Python, Java]
```

---

# 2. LinkedList

## Definition

`LinkedList` is a doubly linked list implementation of the `List` interface. It stores elements as nodes connected using links.

### Features
- Fast insertion and deletion.
- Slower random access than ArrayList.
- Allows duplicates.
- Maintains insertion order.
- Can also be used as a Queue and Deque.

### Example

```java
import java.util.*;

public class LinkedListExample {
    public static void main(String[] args) {

        LinkedList<String> list = new LinkedList<>();

        list.add("Mumbai");
        list.add("Pune");
        list.add("Nashik");

        System.out.println(list);
    }
}
```

**Output**

```
[Mumbai, Pune, Nashik]
```

---

# 3. Vector

## Definition

`Vector` is a synchronized dynamic array that automatically increases its size when required.

### Features
- Thread-safe (Synchronized).
- Dynamic size.
- Maintains insertion order.
- Allows duplicate elements.
- Slower than ArrayList due to synchronization.

### Example

```java
import java.util.*;

public class VectorExample {
    public static void main(String[] args) {

        Vector<Integer> vector = new Vector<>();

        vector.add(10);
        vector.add(20);
        vector.add(30);

        System.out.println(vector);
    }
}
```

**Output**

```
[10, 20, 30]
```

---

# 4. Stack

## Definition

`Stack` is a class that extends `Vector` and follows the **LIFO (Last In First Out)** principle.

The last element inserted into the stack is the first element removed.

### Features
- LIFO data structure.
- Supports push and pop operations.
- Thread-safe because it extends Vector.

### Example

```java
import java.util.*;

public class StackExample {
    public static void main(String[] args) {

        Stack<Integer> stack = new Stack<>();

        stack.push(10);
        stack.push(20);
        stack.push(30);

        System.out.println(stack);
    }
}
```

**Output**

```
[10, 20, 30]
```

---

# Methods of List Interface

The following methods are available in all classes that implement the `List` interface.

| Method | Description | Example |
|---------|-------------|---------|
| `add(E e)` | Adds an element at the end | `list.add("Java");` |
| `add(int index, E e)` | Inserts an element at a specific index | `list.add(1, "Python");` |
| `addAll(Collection c)` | Adds all elements from another collection | `list.addAll(list2);` |
| `get(int index)` | Returns the element at the specified index | `list.get(0);` |
| `set(int index, E e)` | Replaces the element at the specified index | `list.set(1, "C++");` |
| `remove(int index)` | Removes an element using its index | `list.remove(2);` |
| `remove(Object o)` | Removes the first occurrence of an element | `list.remove("Java");` |
| `contains(Object o)` | Checks whether an element exists | `list.contains("Java");` |
| `indexOf(Object o)` | Returns the first occurrence index | `list.indexOf("Java");` |
| `lastIndexOf(Object o)` | Returns the last occurrence index | `list.lastIndexOf("Java");` |
| `size()` | Returns the number of elements | `list.size();` |
| `isEmpty()` | Checks whether the list is empty | `list.isEmpty();` |
| `clear()` | Removes all elements | `list.clear();` |
| `subList(int from, int to)` | Returns a portion of the list | `list.subList(0,2);` |
| `iterator()` | Returns an iterator for traversal | `list.iterator();` |
| `toArray()` | Converts the list into an array | `list.toArray();` |

---

# Example Using List Methods

```java
import java.util.*;

public class ListMethodsExample {

    public static void main(String[] args) {

        List<String> list = new ArrayList<>();

        // add()
        list.add("Java");
        list.add("Python");
        list.add("C++");

        // add(index, element)
        list.add(1, "JavaScript");

        // get()
        System.out.println("Element at index 2: " + list.get(2));

        // set()
        list.set(2, "React");

        // contains()
        System.out.println(list.contains("React"));

        // indexOf()
        System.out.println(list.indexOf("React"));

        // size()
        System.out.println(list.size());

        // remove()
        list.remove("Java");

        // remove(index)
        list.remove(0);

        System.out.println(list);

        // clear()
        list.clear();

        System.out.println(list.isEmpty());
    }
}
```

**Output**

```
Element at index 2: Python
true
2
4
[React, C++]
true
```

---

# Quick Comparison of List Implementations

| Feature | ArrayList | LinkedList | Vector | Stack |
|---------|-----------|------------|--------|--------|
| Data Structure | Dynamic Array | Doubly Linked List | Dynamic Array | Dynamic Array |
| Maintains Order | ✅ | ✅ | ✅ | ✅ |
| Allows Duplicates | ✅ | ✅ | ✅ | ✅ |
| Thread Safe | ❌ | ❌ | ✅ | ✅ |
| Random Access | Fast | Slow | Fast | Fast |
| Insert/Delete | Slow | Fast | Slow | Top Only |
| Special Use | General Purpose | Frequent Insert/Delete | Thread-safe List | LIFO Operations |

# HashSet

## Definition

**HashSet** is a class in the Java Collections Framework that implements the **Set** interface. It stores **unique elements** and does **not maintain the insertion order**.

Internally, HashSet uses a **HashMap** to store elements, making operations like insertion, deletion, and searching very fast.

---

# Features of HashSet

- Stores only unique elements (No duplicates).
- Does not maintain insertion order.
- Allows **one `null` value**.
- Provides fast insertion, deletion, and searching.
- Not synchronized (Not thread-safe).
- Implements the `Set` interface.

---

# Hierarchy

```text
Iterable
    |
Collection
    |
   Set
    |
 HashSet
```

---

# Syntax

```java
HashSet<DataType> set = new HashSet<>();
```

Example

```java
HashSet<String> languages = new HashSet<>();
```

---

# Example

```java
import java.util.*;

public class HashSetExample {

    public static void main(String[] args) {

        HashSet<String> set = new HashSet<>();

        set.add("Java");
        set.add("Python");
        set.add("Java");
        set.add("C++");

        System.out.println(set);
    }
}
```

### Output

```
[Java, Python, C++]
```

> **Note:** The output order may be different because `HashSet` does not preserve insertion order.

---

# HashSet Methods

| Method | Description | Example |
|---------|-------------|---------|
| `add(E e)` | Adds an element | `set.add("Java");` |
| `addAll(Collection c)` | Adds all elements from another collection | `set.addAll(set2);` |
| `remove(Object o)` | Removes an element | `set.remove("Java");` |
| `removeAll(Collection c)` | Removes matching elements | `set.removeAll(set2);` |
| `retainAll(Collection c)` | Keeps common elements | `set.retainAll(set2);` |
| `contains(Object o)` | Checks if an element exists | `set.contains("Java");` |
| `containsAll(Collection c)` | Checks if all elements exist | `set.containsAll(set2);` |
| `size()` | Returns number of elements | `set.size();` |
| `isEmpty()` | Checks whether the set is empty | `set.isEmpty();` |
| `clear()` | Removes all elements | `set.clear();` |
| `iterator()` | Returns an iterator | `set.iterator();` |
| `toArray()` | Converts set to array | `set.toArray();` |

---

# Example Using HashSet Methods

```java
import java.util.*;

public class HashSetMethods {

    public static void main(String[] args) {

        HashSet<String> set = new HashSet<>();

        // add()
        set.add("Java");
        set.add("Python");
        set.add("C++");

        // contains()
        System.out.println("Contains Java : " + set.contains("Java"));

        // size()
        System.out.println("Size : " + set.size());

        // remove()
        set.remove("Python");

        // add duplicate
        set.add("Java");

        // iterator()
        Iterator<String> it = set.iterator();

        while(it.hasNext()){
            System.out.println(it.next());
        }

        // isEmpty()
        System.out.println(set.isEmpty());

        // clear()
        set.clear();

        System.out.println("After clear : " + set);
    }
}
```

### Sample Output

```
Contains Java : true
Size : 3
Java
C++
false
After clear : []
```

---

# Traversing HashSet

## Using Enhanced For Loop

```java
HashSet<String> set = new HashSet<>();

set.add("Java");
set.add("Python");
set.add("C++");

for(String language : set){
    System.out.println(language);
}
```

---

## Using Iterator

```java
Iterator<String> it = set.iterator();

while(it.hasNext()){
    System.out.println(it.next());
}
```

---

# Advantages of HashSet

- Very fast insertion.
- Very fast searching.
- Prevents duplicate elements automatically.
- Dynamic size.
- Easy to use.

---

# Disadvantages of HashSet

- Does not maintain insertion order.
- Elements are not sorted.
- Only one `null` value is allowed.

---

# Time Complexity

| Operation | Time Complexity |
|-----------|-----------------|
| `add()` | O(1) Average |
| `remove()` | O(1) Average |
| `contains()` | O(1) Average |
| `size()` | O(1) |
| `iterator()` | O(n) |

---

# When to Use HashSet

Use `HashSet` when:

- Duplicate values are not allowed.
- Order of elements is not important.
- Fast insertion and searching are required.

---

# Quick Revision

| Feature | HashSet |
|---------|---------|
| Interface | Set |
| Duplicate Elements | ❌ No |
| Insertion Order | ❌ No |
| Sorted | ❌ No |
| Null Values | ✅ One Allowed |
| Thread Safe | ❌ No |
| Data Structure | Hash Table (internally uses HashMap) |
| Best For | Fast search and unique elements |



# Queue Interface

## Definition

A **Queue** is an interface in the Java Collections Framework that follows the **FIFO (First In First Out)** principle.

The element that is inserted first is removed first. A Queue is mainly used for scheduling tasks, processing requests, buffering data, and implementing breadth-first search (BFS).

---

# Features of Queue

- Follows **FIFO (First In First Out)**.
- Allows duplicate elements.
- Usually does **not allow `null` elements**.
- Elements are inserted at the **rear** and removed from the **front**.
- Dynamic in size.

---

# Hierarchy

```text
Iterable
    |
Collection
    |
   Queue
   /    \
LinkedList  PriorityQueue
      \
    ArrayDeque (via Deque)
```

---

# Types of Queue

The Queue interface has several implementations:

1. LinkedList
2. PriorityQueue
3. ArrayDeque

---

# 1. LinkedList (Queue)

## Definition

`LinkedList` implements the Queue interface and follows the FIFO principle. It stores elements using a doubly linked list.

### Features

- Maintains insertion order.
- Allows duplicate elements.
- Fast insertion and deletion.
- Can also be used as a List and Deque.

### Example

```java
import java.util.*;

public class LinkedListQueueExample {

    public static void main(String[] args) {

        Queue<String> queue = new LinkedList<>();

        queue.offer("Java");
        queue.offer("Python");
        queue.offer("C++");

        System.out.println(queue);
    }
}
```

### Output

```
[Java, Python, C++]
```

---

# 2. PriorityQueue

## Definition

`PriorityQueue` is a Queue implementation that stores elements according to their **priority** instead of insertion order.

By default, the smallest element has the highest priority.

### Features

- Elements are automatically sorted.
- Duplicate elements are allowed.
- Does not allow null values.
- Does not maintain insertion order.

### Example

```java
import java.util.*;

public class PriorityQueueExample {

    public static void main(String[] args) {

        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.offer(30);
        pq.offer(10);
        pq.offer(20);

        System.out.println(pq);
    }
}
```

### Output

```
[10, 30, 20]
```

> **Note:** Internally, the smallest element is always at the front.

---

# 3. ArrayDeque

## Definition

`ArrayDeque` is a resizable array implementation of the Deque interface. It can also be used as a Queue.

### Features

- Faster than LinkedList in most cases.
- Does not allow null values.
- Dynamic size.
- Can be used as both Queue and Stack.

### Example

```java
import java.util.*;

public class ArrayDequeExample {

    public static void main(String[] args) {

        Queue<Integer> queue = new ArrayDeque<>();

        queue.offer(10);
        queue.offer(20);
        queue.offer(30);

        System.out.println(queue);
    }
}
```

### Output

```
[10, 20, 30]
```

---

# Queue Methods

These methods are available in the Queue interface.

| Method | Description | Example |
|---------|-------------|---------|
| `offer(E e)` | Inserts an element | `queue.offer(10);` |
| `add(E e)` | Inserts an element (throws exception if full) | `queue.add(20);` |
| `poll()` | Removes and returns the front element | `queue.poll();` |
| `remove()` | Removes the front element (throws exception if empty) | `queue.remove();` |
| `peek()` | Returns the front element without removing it | `queue.peek();` |
| `element()` | Returns the front element (throws exception if empty) | `queue.element();` |
| `contains(Object o)` | Checks whether an element exists | `queue.contains(20);` |
| `size()` | Returns the number of elements | `queue.size();` |
| `isEmpty()` | Checks whether the queue is empty | `queue.isEmpty();` |
| `clear()` | Removes all elements | `queue.clear();` |
| `iterator()` | Returns an iterator | `queue.iterator();` |

---

# Example Using Queue Methods

```java
import java.util.*;

public class QueueMethodsExample {

    public static void main(String[] args) {

        Queue<String> queue = new LinkedList<>();

        // offer()
        queue.offer("Java");
        queue.offer("Python");
        queue.offer("C++");

        // peek()
        System.out.println("Front Element : " + queue.peek());

        // poll()
        System.out.println("Removed : " + queue.poll());

        // contains()
        System.out.println("Contains Python : " + queue.contains("Python"));

        // size()
        System.out.println("Size : " + queue.size());

        // iterator()
        Iterator<String> it = queue.iterator();

        while(it.hasNext()){
            System.out.println(it.next());
        }

        // clear()
        queue.clear();

        System.out.println(queue.isEmpty());
    }
}
```

### Output

```
Front Element : Java
Removed : Java
Contains Python : true
Size : 2
Python
C++
true
```

---

# Traversing a Queue

## Using Enhanced For Loop

```java
Queue<Integer> queue = new LinkedList<>();

queue.offer(10);
queue.offer(20);
queue.offer(30);

for(Integer num : queue){
    System.out.println(num);
}
```

---

## Using Iterator

```java
Iterator<Integer> it = queue.iterator();

while(it.hasNext()){
    System.out.println(it.next());
}
```

---

# Advantages of Queue

- Follows FIFO ordering.
- Fast insertion and deletion.
- Dynamic size.
- Easy to implement scheduling algorithms.
- Useful for BFS, task scheduling, and buffering.

---

# Disadvantages of Queue

- Random access is not supported.
- Elements can only be removed from the front.
- Some implementations do not maintain insertion order (e.g., PriorityQueue).

---

# Time Complexity

| Operation | LinkedList Queue | PriorityQueue |
|-----------|------------------|---------------|
| `offer()` | O(1) | O(log n) |
| `poll()` | O(1) | O(log n) |
| `peek()` | O(1) | O(1) |
| `contains()` | O(n) | O(n) |
| `size()` | O(1) | O(1) |

---

# When to Use Queue

Use a Queue when:

- Data should be processed in FIFO order.
- Implementing task scheduling.
- Handling printer queues.
- Performing Breadth-First Search (BFS).
- Processing requests in the order they arrive.

---

# Quick Revision

| Feature | Queue |
|---------|-------|
| Type | Interface |
| Principle | FIFO (First In First Out) |
| Duplicate Elements | ✅ Allowed |
| Null Values | ❌ Generally Not Allowed |
| Index-Based Access | ❌ No |
| Common Implementations | LinkedList, PriorityQueue, ArrayDeque |
| Best For | Scheduling, BFS, Request Processing |


# Map Interface

## Definition

A **Map** is an interface in the Java Collections Framework that stores data in the form of **Key-Value pairs**.

Each **key must be unique**, while **values can be duplicated**. A Map is used when you want to associate one object (key) with another object (value).

> **Note:** `Map` is part of the Java Collections Framework but **does not extend the Collection interface**.

---

# Features of Map

- Stores data as **Key-Value pairs**.
- Keys must be unique.
- Values can be duplicated.
- Provides fast searching using keys.
- Dynamic in size.
- Different implementations maintain different ordering.

---

# Hierarchy

```text
                Map
                 |
      ___________________________
     |            |             |
 HashMap   LinkedHashMap     TreeMap
                              |
                         Hashtable
```

---

# Types of Map

The Map interface has four main implementations:

1. HashMap
2. LinkedHashMap
3. TreeMap
4. Hashtable

---

# 1. HashMap

## Definition

**HashMap** is the most commonly used implementation of the Map interface. It stores key-value pairs using a hash table.

### Features

- Does not maintain insertion order.
- Keys must be unique.
- Allows one null key.
- Allows multiple null values.
- Not synchronized.
- Fast insertion and searching.

### Example

```java
import java.util.*;

public class HashMapExample {

    public static void main(String[] args) {

        HashMap<Integer, String> map = new HashMap<>();

        map.put(1, "Java");
        map.put(2, "Python");
        map.put(3, "C++");

        System.out.println(map);
    }
}
```

### Output

```
{1=Java, 2=Python, 3=C++}
```

---

# 2. LinkedHashMap

## Definition

**LinkedHashMap** maintains the insertion order of key-value pairs.

### Features

- Maintains insertion order.
- Allows one null key.
- Allows multiple null values.
- Slightly slower than HashMap.

### Example

```java
import java.util.*;

public class LinkedHashMapExample {

    public static void main(String[] args) {

        LinkedHashMap<Integer, String> map = new LinkedHashMap<>();

        map.put(2, "Python");
        map.put(1, "Java");
        map.put(3, "C++");

        System.out.println(map);
    }
}
```

### Output

```
{2=Python, 1=Java, 3=C++}
```

---

# 3. TreeMap

## Definition

**TreeMap** stores key-value pairs in **sorted order based on keys**.

### Features

- Keys are automatically sorted.
- Duplicate keys are not allowed.
- Null keys are not allowed.
- Slower than HashMap because it uses a Red-Black Tree.

### Example

```java
import java.util.*;

public class TreeMapExample {

    public static void main(String[] args) {

        TreeMap<Integer, String> map = new TreeMap<>();

        map.put(3, "C++");
        map.put(1, "Java");
        map.put(2, "Python");

        System.out.println(map);
    }
}
```

### Output

```
{1=Java, 2=Python, 3=C++}
```

---

# 4. Hashtable

## Definition

**Hashtable** is a synchronized implementation of the Map interface.

### Features

- Thread-safe.
- Does not allow null keys.
- Does not allow null values.
- Slower than HashMap.

### Example

```java
import java.util.*;

public class HashtableExample {

    public static void main(String[] args) {

        Hashtable<Integer, String> table = new Hashtable<>();

        table.put(1, "Java");
        table.put(2, "Python");

        System.out.println(table);
    }
}
```

### Output

```
{2=Python, 1=Java}
```

---

# Map Methods

The following methods are available in the `Map` interface.

| Method | Description | Example |
|---------|-------------|---------|
| `put(K key, V value)` | Inserts a key-value pair | `map.put(1,"Java");` |
| `putIfAbsent(K,V)` | Inserts only if key is absent | `map.putIfAbsent(2,"Python");` |
| `get(Object key)` | Returns value for a key | `map.get(1);` |
| `getOrDefault(K,V)` | Returns value or default | `map.getOrDefault(5,"NA");` |
| `remove(Object key)` | Removes a key-value pair | `map.remove(1);` |
| `replace(K,V)` | Replaces value of a key | `map.replace(2,"C++");` |
| `containsKey(Object key)` | Checks if key exists | `map.containsKey(2);` |
| `containsValue(Object value)` | Checks if value exists | `map.containsValue("Java");` |
| `keySet()` | Returns all keys | `map.keySet();` |
| `values()` | Returns all values | `map.values();` |
| `entrySet()` | Returns all key-value pairs | `map.entrySet();` |
| `size()` | Returns number of entries | `map.size();` |
| `isEmpty()` | Checks if map is empty | `map.isEmpty();` |
| `clear()` | Removes all entries | `map.clear();` |

---

# Example Using Map Methods

```java
import java.util.*;

public class MapMethodsExample {

    public static void main(String[] args) {

        Map<Integer, String> map = new HashMap<>();

        // put()
        map.put(1, "Java");
        map.put(2, "Python");
        map.put(3, "C++");

        // get()
        System.out.println("Value : " + map.get(2));

        // containsKey()
        System.out.println(map.containsKey(1));

        // containsValue()
        System.out.println(map.containsValue("Python"));

        // replace()
        map.replace(3, "JavaScript");

        // remove()
        map.remove(1);

        // keySet()
        System.out.println(map.keySet());

        // values()
        System.out.println(map.values());

        // entrySet()
        System.out.println(map.entrySet());

        // size()
        System.out.println(map.size());

        // clear()
        map.clear();

        System.out.println(map.isEmpty());
    }
}
```

### Output

```
Value : Python
true
true
[2, 3]
[Python, JavaScript]
[2=Python, 3=JavaScript]
2
true
```

---

# Traversing a Map

## Using keySet()

```java
for(Integer key : map.keySet()){
    System.out.println(key + " -> " + map.get(key));
}
```

---

## Using entrySet()

```java
for(Map.Entry<Integer, String> entry : map.entrySet()){

    System.out.println(entry.getKey() + " : " + entry.getValue());
}
```

---

## Using forEach()

```java
map.forEach((key, value) -> {

    System.out.println(key + " -> " + value);
});
```

---

# Advantages of Map

- Fast searching using keys.
- Stores data in key-value pairs.
- Dynamic size.
- Prevents duplicate keys.
- Multiple implementations for different needs.

---

# Disadvantages of Map

- Duplicate keys are not allowed.
- Some implementations do not maintain insertion order.
- Random index access is not supported.

---

# Time Complexity

| Operation | HashMap | LinkedHashMap | TreeMap | Hashtable |
|-----------|----------|---------------|----------|------------|
| `put()` | O(1) | O(1) | O(log n) | O(1) |
| `get()` | O(1) | O(1) | O(log n) | O(1) |
| `remove()` | O(1) | O(1) | O(log n) | O(1) |
| `containsKey()` | O(1) | O(1) | O(log n) | O(1) |

---

# When to Use Map

Use a Map when:

- You need to store data as **key-value pairs**.
- Keys must be unique.
- Fast searching is required.
- Associating one object with another (e.g., Student ID → Student Name).

---

# Quick Revision

| Feature | Map |
|---------|-----|
| Type | Interface |
| Stores | Key-Value Pairs |
| Duplicate Keys | ❌ Not Allowed |
| Duplicate Values | ✅ Allowed |
| Null Key | Depends on Implementation |
| Common Implementations | HashMap, LinkedHashMap, TreeMap, Hashtable |
| Best For | Fast Lookup Using Keys |