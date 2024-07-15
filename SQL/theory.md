# SQL Theoretical Questions

### Q1: List in a tabular form the difference between `Truncate` and `Delete`? 

**Answer**: The following table lists the difference between Truncate and delete

| Feature           | Truncate           | Delete                     |
| ----------------- | ------------------ | -------------------------- |
| Scope of Deletion | *Removes all rows* | *Can remove specific rows* |
| Performance       | *Faster*           | *Slower*                   |

### Q2: What is indexing ?

**Answer**: Creating a *data structure* that enhances the *speed of data retreival operations on a table*

### Q3:What are views ? 

**Answer**: *virtual tables that display data retreived from one or more actual tables* , but they *do not store any data themselves*

### Q4:What are MySQL Triggers ? 

**Answer**: *Automatic actions* that occur in response to certain events like *inserting, updating or deleting data in a table*

### Q5: What is a blob ? 

**Answer**: blob is used for storing *large binary objects*  such as *images or files*

### Q6:What is a text ? 

**Answer**: text is *used for storing large text strings*

### Q7:List 5 Constraint types and their definations 

| Constraint Type | Definition                                                   | Example                                                      |
| --------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Primary Key     | Ensures each row is uniquely identified                      | CREATE TABLE students (<br/>    student_id INT PRIMARY KEY,<br/>    name VARCHAR(100),<br/>    age INT<br/>); |
| Foreign Key     | Links 2 tables                                               | CREATE TABLE students (<br/>    student_id INT PRIMARY KEY,<br/>    name VARCHAR(100),<br/>    age INT<br/>);<br />CREATE TABLE enrollments (  <br>  enrollment_id INT PRIMARY KEY,  <br>  student_id INT,   <br>     FOREIGN KEY (student_id) REFERENCES students(student_id),  <br>   ); |
| Unique          | Ensures values in a column are unique                        | CREATE TABLE employees (<br/>    employee_id INT PRIMARY KEY,<br/>    email VARCHAR(100) UNIQUE,<br/>    phone_number VARCHAR(15) UNIQUE<br/>); |
| Check           | Ensures that all values in a column satisfy a specific condition. | CREATE TABLE products (<br/>    product_id INT PRIMARY KEY,<br/>    price DECIMAL(10, 2),<br/>    stock_quantity INT,<br/>    CHECK (price > 0),<br/>    CHECK (stock_quantity >= 0)<br/>); |
| NOT NULL        | Ensures that a column cannot have a null value               | CREATE TABLE orders (<br/>    order_id INT PRIMARY KEY,<br/>    order_date DATE NOT NULL,<br/>    customer_id INT NOT NULL<br/>); |

###  Q8: Primary Key vs Unique ? 

| Feature | Primary Key                    | Unique Constraint         |
| ------- | ------------------------------ | ------------------------- |
| purpose | *Identifies each row uniquely* | *Ensures data uniqueness* |

### Q9: What is the use of UNION keyword in SQL ?

**Answer**: The UNION keyword is used to *merge the results of multiple SELECT queries into a single result set*

### Q10: What is normalisation of database ?

**Answer**: Process of dividing large table into smaller tables and defining relations between them

### Q11:What is  indexing  ?

**Answer**: Indexing in databases is a technique used to *improve the speed of data retrieval operations on tables by creating a quick-access structure (index) on one or more columns.*

#### Q12:List 2 advantages and 2 disadvantages of indexing ? 

**Answer**: 

**Advantages of Indexing:**

1. **Faster Data Retrieval:** Indexing speeds up SELECT queries by allowing the database to quickly locate rows based on the indexed columns, rather than scanning the entire table.
2. **Improved Performance for Joins:** Indexes can enhance the performance of JOIN operations by facilitating faster lookup and matching of rows across tables.

**Disadvantages of Indexing:**

1. **Increased Storage Space:** Indexes require additional storage space on disk or in memory to store the index structures, which can increase storage requirements for the database.
2. **Overhead on Data Modification:** Indexes need to be updated whenever data in the indexed columns is inserted, updated, or deleted. This overhead can slow down data modification operations (INSERT, UPDATE, DELETE).

#### Q13:If we drop a table, does it also drop related objects like constraints, indexes, columns,  views and sorted procedures?

**Answer**: Yes 

#### Q14: In a tabular form list the difference between IN and BETWEEN operator in sql ? 

**Answer**: The following table lists the difference between IN and BETWEEN operator 

| Operator  | Description                                   | Example                                                      |
| --------- | --------------------------------------------- | ------------------------------------------------------------ |
| `IN`      | Checks if a value matches any value in a list | SELECT * FROM students <br>WHERE student_id IN (1, 3, 5, 7);<br><br>This query retrieves all students whose `student_id` is either 1, 3, 5, or 7. |
| `BETWEEN` | Checks if a value is within a range           | SELECT name from students WHERE age betwee 10 and 15<br><br>Find students between the ages of 10 and 15 |

#### Q15:What is ACID in relation to databases ?

**Answer**:The following table explains the ACID properties of database transactions in a table format:

| Property        | Description                                                  |
| --------------- | ------------------------------------------------------------ |
| **Atomicity**   | All operations in a transaction are treated as one unit.     |
| **Consistency** | Database remains in a consistent state after the transaction. |
| **Isolation**   | Transactions do not interfere with each other.               |
| **Durability**  | Changes from committed transactions are permanent            |

#### Q16:What is a *deadlock* in SQL ? 

**Answer**: A deadlock in SQL occurs when *two or more transactions are unable to proceed because each transaction is waiting for a resource that is held by another transaction*. This situation creates a cycle where each transaction is waiting for a resource that is locked by another transaction in the cycle, leading to a standstill where none of the transactions can continue.

#### Q17:Is a blank space  the same as a NULL value?

**Answer**: No because blank space is treated as a empty string

#### Q18:Explain the `COALESCE()` function in sql ?

**Answer**: The `COALESCE()` function in SQL is used to return the first non-NULL value in a list of expressions

#### Q19:What are Entities and Relationships ?

**Answer**: 

**Entities**:

- An entity represents a *distinct object* 
-  entities are typically represented as *tables* where each row corresponds to a single instance of that entity, and each column represents an attribute or property of that entity.

**Relationships**:

- Relationships define *how entities are related to each other within the database*.
- There are three main types of relationships:
  - **One-to-One**
  - **One-to-Many (or Many-to-One)**
  - **Many-to-Many**: 
- Relationships are typically established using keys (primary and foreign keys)

#### Q20:What are the different types of relationships ?

**Answer**: There are three Relationships

1. **One to One Relationship**  say between a customers table (holding username and password) and the customers_details table(holding all the details of the customer )
2. **One To Many Relationship**  say between a customers table and a orders table , a customer can have many orders while each order belongs to a particular customer
3. **Many to Many Relationship**  say between a books table and an authors table, a book can have multiple authors and an author can have multiple books

#### Q21:What are DELETE , DROP And Truncate Keywords in SQL ? 

**Answer**: The following table explains the difference between DELETE,DROP and TRUNCATE 		

| Keyword  | Definition                                                   |
| -------- | ------------------------------------------------------------ |
| DELETE   | Removes specified rows from a table based on a condition. Data can be rolled back if needed. |
| TRUNCATE | Removes all rows from a table quickly without logging individual row deletions. Cannot be rolled back. |
| DROP     | Deletes an entire table, its structure, and all data. Cannot be rolled back and removes table definition. |

#### Q22:What is a subquery? What are its various types? Give an example where you might use a subquery ?

**Answer**: 

| Term     | Definition                                                   |
| -------- | ------------------------------------------------------------ |
| Subquery | A query nested inside another query.                         |
| Types    | 1. **Single-row Subquery**: Returns one row. <br> 2. **Multiple-row Subquery**: Returns multiple rows. <br> 3. **Correlated Subquery**: Depends on the outer query. |

### Example

To find employees with salaries higher than the average salary:

```sql
SELECT employee_name
FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```