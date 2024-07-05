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

| Constraint Type | Definition                                                   |
| --------------- | ------------------------------------------------------------ |
| Primary Key     | Ensures each row in *uniquely identified*                    |
| Foreign Key     | *Links two tables*                                           |
| Unique          | *Ensures values in a column are unique*                      |
| Check           | *Imposes conditions on data values allowed in a column for each row* |
| Not Null        | *Requires a column to always have a value* , preventing NULL entries |

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

#### Q13:If we drop a table, does it also drop related objects like constraints, indexes, columns, default, views and sorted procedures?

**Answer**: Yes 

#### Q14: In a tabular form list the difference between IN and BETWEEN operator in sql ? 

**Answer**: The following table lists the difference between IN and BETWEEN operator 

| Operator  | Description                                   | Key Difference                                               |
| --------- | --------------------------------------------- | ------------------------------------------------------------ |
| `IN`      | Checks if a value matches any value in a list | Matches any value in the specified list.                     |
| `BETWEEN` | Checks if a value is within a range           | Checks if a value falls within the specified range inclusive. |

#### Q15:What is ACID in realtion to databases ?

**Answer**:The following table explains the ACID properties of database transactions in a table format:

| ACID Property   | Description                                                  |
| --------------- | ------------------------------------------------------------ |
| **Atomicity**   | Ensures that each transaction is treated as a single unit, either fully completed (committed) or fully aborted (rolled back) if an error occurs. |
| **Consistency** | Guarantees that a transaction brings the database from one valid state to another valid state. |
| **Isolation**   | Ensures that transactions are executed independently and are unaware of other transactions running concurrently. |
| **Durability**  | Once a transaction is committed, its changes are permanently saved and can withstand system failures. |

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
3. **Many to Many Relationship**  say between a books table and a authors table, a book can have multiple authors and an author can have multiple books

#### Q21:Create an Entity-Relationship diagram for a library database that tracks information about books and authors, including their relationships.

**Book Table:**

| BookID | Title                  | ISBN          | Genre     | Published Year |
| ------ | ---------------------- | ------------- | --------- | -------------- |
| 1      | To Kill a Mockingbird  | 9780061120084 | Fiction   | 1960           |
| 2      | The Catcher in the Rye | 0316769487    | Fiction   | 1951           |
| 3      | 1984                   | 9780451524935 | Dystopian | 1949           |

**Author Table:**

| AuthorID | Name          | Birthdate  | Nationality |
| -------- | ------------- | ---------- | ----------- |
| 1        | Harper Lee    | 1926-04-28 | American    |
| 2        | J.D. Salinger | 1919-01-01 | American    |
| 3        | George Orwell | 1903-06-25 | British     |



**AuthoredBy Table:**

| BookID | AuthorID |
| ------ | -------- |
| 1      | 1        |
| 2      | 2        |
| 3      | 3        |
| 3      | 2        |

**Answer**:Entities and Attributes:

1. **Book**
   - BookID (Primary Key)
   - Title
   - ISBN
   - Genre
   - Published Year
2. **Author**
   - AuthorID (Primary Key)
   - Name
   - Birthdate
   - Nationality
3. **AuthoredBy**
   - BookID (Foreign Key, references Book)
   - AuthorID (Foreign Key, references Author)

### Relationships:

- A **Book** can have one or more **Authors**.
- An **Author** can write one or more **Books**.

The relationship between **Book** and **Author** is many-to-many, which is represented by the **AuthoredBy** table.

### ER Diagram:

1. **Book** entity connected to **AuthoredBy** with a one-to-many relationship (One book can have many entries in AuthoredBy).
2. **Author** entity connected to **AuthoredBy** with a one-to-many relationship (One author can have many entries in AuthoredBy).
3. **AuthoredBy** entity that serves as a junction table between **Book** and **Author**.

[Book] --< (1,∞) AuthoredBy (∞,1) >-- [Author]

#### Q22:Create an Entity-Relationship Diagram for a User Management Database

#### User Table:

| id   | name       | email            | password  | isPremiumUser | totalExpenses |
| ---- | ---------- | ---------------- | --------- | ------------- | ------------- |
| 1    | John Doe   | john@example.com | password1 | true          | 1000          |
| 2    | Jane Smith | jane@example.com | password2 | false         | 500           |
| 3    | Bob Brown  | bob@example.com  | password3 | true          | 1500          |

#### Expense Table:

| id   | date       | category  | description      | amount | userId |
| ---- | ---------- | --------- | ---------------- | ------ | ------ |
| 1    | 2024-01-01 | Food      | Lunch            | 20     | 1      |
| 2    | 2024-01-02 | Transport | Bus fare         | 2      | 2      |
| 3    | 2024-01-03 | Food      | Dinner           | 30     | 1      |
| 4    | 2024-01-04 | Utilities | Electricity bill | 50     | 3      |

#### Order Table:

| id   | paymentid | orderid | status  | userId |
| ---- | --------- | ------- | ------- | ------ |
| 1    | pay123    | ord001  | Paid    | 1      |
| 2    | pay124    | ord002  | Pending | 2      |
| 3    | pay125    | ord003  | Paid    | 3      |

#### ResetPassword Table:

| id       | isActive | userId |
| -------- | -------- | ------ |
| reset001 | true     | 1      |
| reset002 | false    | 2      |
| reset003 | true     | 3      |

#### Downloads Table:

| id   | downloadUrl               | userId |
| ---- | ------------------------- | ------ |
| 1    | https://example.com/file1 | 1      |
| 2    | https://example.com/file2 | 2      |
| 3    | https://example.com/file3 | 3      |

**Answer**: Entities and Attributes:

1. **User**
   - id (Primary Key)
   - name
   - email
   - password
   - isPremiumUser
   - totalExpenses
2. **Expense**
   - id (Primary Key)
   - date
   - category
   - description
   - amount
   - userId (Foreign Key, references User)
3. **Order**
   - id (Primary Key)
   - paymentid
   - orderid
   - status
   - userId (Foreign Key, references User)
4. **ResetPassword**
   - id (Primary Key)
   - isActive
   - userId (Foreign Key, references User)
5. **Downloads**
   - id (Primary Key)
   - downloadUrl
   - userId (Foreign Key, references User)

### Relationships:

- A **User** can have many **Expenses**.
- An **Expense** belongs to one **User**.
- A **User** can have many **Orders**.
- An **Order** belongs to one **User**.
- A **User** can have many **ResetPassword** entries.
- A **ResetPassword** entry belongs to one **User**.
- A **User** can have many **Downloads**.
- A **Download** belongs to one **User**.

### ER Diagram:

1. **User** entity connected to **Expense**, **Order**, **ResetPassword**, and **Downloads** with one-to-many relationships.

```
plaintext
Copy code
[User] --< (1,∞) [Expense]
[User] --< (1,∞) [Order]
[User] --< (1,∞) [ResetPassword]
[User] --< (1,∞) [Downloads]
```