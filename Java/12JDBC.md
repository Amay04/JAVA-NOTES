# JDBC (Java Database Connectivity)

JDBC (Java Database Connectivity) is a Java API used to connect Java applications with relational databases such as MySQL, PostgreSQL, Oracle, and SQL Server.

It allows Java programs to perform database operations like:

* Insert data
* Retrieve data
* Update data
* Delete data

---

# Why Use JDBC?

JDBC helps Java applications communicate with databases.

Common use cases:

* Login Systems
* Student Management Systems
* Banking Applications
* E-commerce Applications
* Employee Management Systems

---

# JDBC Architecture

```text
Java Application
        │
        ▼
     JDBC API
        │
        ▼
   JDBC Driver
        │
        ▼
     Database
```

---

# JDBC Components

| Component         | Purpose                          |
| ----------------- | -------------------------------- |
| DriverManager     | Creates database connections     |
| Connection        | Represents a database connection |
| Statement         | Executes SQL queries             |
| PreparedStatement | Executes parameterized queries   |
| ResultSet         | Stores query results             |

---

# Steps to Connect Java with MySQL

1. Import JDBC package.
2. Load the JDBC driver.
3. Establish a connection.
4. Create a statement.
5. Execute SQL queries.
6. Process the result.
7. Close the connection.

---

# Import Package

```java
import java.sql.*;
```

---

# Loading the Driver

```java
Class.forName("com.mysql.cj.jdbc.Driver");
```

Modern JDBC drivers usually load automatically.

---

# Creating a Connection

```java
Connection con = DriverManager.getConnection(

    "jdbc:mysql://localhost:3306/college",

    "root",

    "password"

);
```

---

# Executing a Query

```java
Statement stmt = con.createStatement();

ResultSet rs = stmt.executeQuery("SELECT * FROM student");
```

---

# Reading Data

```java
while (rs.next()) {

    System.out.println(

        rs.getInt("id") + " " +

        rs.getString("name")

    );

}
```

---

# Inserting Data

```java
Statement stmt = con.createStatement();

stmt.executeUpdate(

    "INSERT INTO student VALUES(1,'Amay')"

);
```

---

# Updating Data

```java
stmt.executeUpdate(

    "UPDATE student SET name='Rahul' WHERE id=1"

);
```

---

# Deleting Data

```java
stmt.executeUpdate(

    "DELETE FROM student WHERE id=1"

);
```

---

# PreparedStatement

`PreparedStatement` is preferred over `Statement`.

Advantages:

* Faster execution
* Prevents SQL Injection
* Easier to reuse

Example:

```java
PreparedStatement ps = con.prepareStatement(

    "INSERT INTO student VALUES(?, ?)"

);

ps.setInt(1, 1);

ps.setString(2, "Amay");

ps.executeUpdate();
```

---

# Statement vs PreparedStatement

| Statement                   | PreparedStatement      |
| --------------------------- | ---------------------- |
| Simple SQL                  | Parameterized SQL      |
| Slower                      | Faster                 |
| Vulnerable to SQL Injection | Prevents SQL Injection |
| Compiled every time         | Precompiled            |

---

# Closing Resources

Always close JDBC resources.

```java
rs.close();

stmt.close();

con.close();
```

---

# Important JDBC Interfaces

| Interface         | Purpose                    |
| ----------------- | -------------------------- |
| Connection        | Database connection        |
| Statement         | Executes SQL               |
| PreparedStatement | Executes parameterized SQL |
| CallableStatement | Executes stored procedures |
| ResultSet         | Stores query results       |

---

# Important Points

* JDBC is part of the `java.sql` package.
* `Connection` establishes communication with the database.
* `PreparedStatement` is preferred over `Statement`.
* Always close database resources.
* Handle `SQLException` using exception handling.

---

# Common Mistakes

## Forgetting to Close the Connection

```java
Connection con = DriverManager.getConnection(...);
```

Always close it.

```java
con.close();
```

---

## Using Statement Instead of PreparedStatement

❌ Less Secure

```java
Statement stmt = con.createStatement();
```

✔ Better

```java
PreparedStatement ps = con.prepareStatement(...);
```

---

## Ignoring SQL Exceptions

Always use exception handling.

```java
try {

    // JDBC Code

} catch (SQLException e) {

    System.out.println(e.getMessage());

}
```

---

# Interview Notes

### What is JDBC?

JDBC is a Java API used to connect Java applications with relational databases.

---

### Which Package Contains JDBC Classes?

```text
java.sql
```

---

### Which Interface Represents a Database Connection?

```text
Connection
```

---

### Difference Between executeQuery() and executeUpdate()

| executeQuery()      | executeUpdate()                        |
| ------------------- | -------------------------------------- |
| Used with `SELECT`  | Used with `INSERT`, `UPDATE`, `DELETE` |
| Returns `ResultSet` | Returns number of affected rows        |

---

### Why is PreparedStatement Better?

* Faster execution
* Prevents SQL Injection
* Reusable
* Easier to read

---

# Summary

* JDBC connects Java applications to relational databases.
* The main JDBC components are `Connection`, `Statement`, `PreparedStatement`, and `ResultSet`.
* `PreparedStatement` is recommended for executing SQL queries securely.
* Always handle SQL exceptions and close all database resources after use.
