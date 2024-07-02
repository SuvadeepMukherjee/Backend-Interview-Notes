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