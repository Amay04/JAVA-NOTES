# File Handling in Java

File Handling in Java is used to create, read, write, update, and delete files stored on the computer.

Java provides the **`java.io`** package and the **`java.nio.file`** package for performing file operations.

---

# Why Use File Handling?

File handling is useful when we want to:

* Store data permanently.
* Read data from text files.
* Save application logs.
* Generate reports.
* Process configuration files.

Unlike variables, data stored in files remains available even after the program ends.

---

# Common File Classes

| Class            | Purpose                          |
| ---------------- | -------------------------------- |
| `File`           | Represents a file or directory   |
| `FileReader`     | Reads character data from a file |
| `FileWriter`     | Writes character data to a file  |
| `BufferedReader` | Reads text efficiently           |
| `BufferedWriter` | Writes text efficiently          |
| `Scanner`        | Reads data from a file           |
| `PrintWriter`    | Writes formatted text            |

---

# Creating a File

```java
import java.io.File;
import java.io.IOException;

public class Main {

    public static void main(String[] args) throws IOException {

        File file = new File("student.txt");

        if (file.createNewFile()) {
            System.out.println("File Created");
        } else {
            System.out.println("File Already Exists");
        }

    }

}
```

### Output

```text
File Created
```

---

# Writing to a File

```java
import java.io.FileWriter;
import java.io.IOException;

public class Main {

    public static void main(String[] args) throws IOException {

        FileWriter writer = new FileWriter("student.txt");

        writer.write("Hello Java");

        writer.close();

    }

}
```

The `close()` method should always be called to save the data properly.

---

# Reading from a File

```java
import java.io.File;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) throws Exception {

        File file = new File("student.txt");

        Scanner sc = new Scanner(file);

        while (sc.hasNextLine()) {

            System.out.println(sc.nextLine());

        }

        sc.close();

    }

}
```

### Output

```text
Hello Java
```

---

# Appending Data

Instead of replacing existing data, we can append new data.

```java
FileWriter writer = new FileWriter("student.txt", true);

writer.write("\nWelcome");

writer.close();
```

---

# Deleting a File

```java
import java.io.File;

public class Main {

    public static void main(String[] args) {

        File file = new File("student.txt");

        if (file.delete()) {

            System.out.println("File Deleted");

        }

    }

}
```

---

# BufferedReader Example

```java
import java.io.BufferedReader;
import java.io.FileReader;

public class Main {

    public static void main(String[] args) throws Exception {

        BufferedReader br = new BufferedReader(
                new FileReader("student.txt"));

        String line;

        while ((line = br.readLine()) != null) {

            System.out.println(line);

        }

        br.close();

    }

}
```

---

# Important File Methods

| Method              | Description                  |
| ------------------- | ---------------------------- |
| `createNewFile()`   | Creates a file               |
| `exists()`          | Checks whether a file exists |
| `delete()`          | Deletes a file               |
| `length()`          | Returns file size            |
| `getName()`         | Returns file name            |
| `getAbsolutePath()` | Returns complete file path   |
| `mkdir()`           | Creates a directory          |

---

# Exception Handling in File Handling

Most file operations throw checked exceptions such as `IOException`.

```java
try {

    FileWriter writer = new FileWriter("student.txt");

} catch (IOException e) {

    System.out.println(e.getMessage());

}
```

---

# Important Points

* File handling is available in the `java.io` package.
* Always close streams after use.
* File operations may throw checked exceptions.
* Use `BufferedReader` or `BufferedWriter` for better performance.

---

# Common Mistakes

## Forgetting to Close the File

```java
FileWriter writer = new FileWriter("student.txt");

writer.write("Hello");
```

Always call:

```java
writer.close();
```

---

## Reading a File That Doesn't Exist

```java
FileReader reader = new FileReader("abc.txt");
```

This throws `FileNotFoundException`.

---

# Interview Notes

### What is File Handling?

File handling is the process of creating, reading, writing, updating, and deleting files.

---

### Which Package is Used?

* `java.io`
* `java.nio.file`

---

### Why Use BufferedReader?

It improves reading performance by reducing the number of disk accesses.

---

### Why Close a File?

Closing a file:

* Saves data.
* Releases system resources.
* Prevents memory leaks.

---

# Summary

* File handling allows Java programs to store and retrieve data from files.
* Java provides classes such as `File`, `FileReader`, `FileWriter`, `BufferedReader`, and `BufferedWriter`.
* Always handle exceptions and close files after use.
