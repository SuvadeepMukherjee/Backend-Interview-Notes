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

- Relationships are typically established using keys (primary and foreign keys):

  