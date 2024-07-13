## These are all the final Notes on SQL Queries 

#### Q1: You are required to demonstrate your understanding of various SQL clauses and functions by writing a generalized SQL query that includes the following components:

1. A **SELECT** statement with an **INNER JOIN** between two tables.
2. A WHERE clause that includes:
   - A condition with the **LIKE** operator using both '%' and '_' patterns.
   - Logical operators **AND**, **OR**, and **NOT**.
   - A check for null values using **IS  NULL**.
   - A condition that uses the **MOD()** numeric function.
3. A **GROUP BY** clause.
4. An **ORDER BY** clause that sorts the result set.
5. Pagination using **LIMIT** and **OFFSET**.

Write a general SQL query that incorporates all of the above components.

**Answer**: The SQL query is written below 

```sql
-- SELECT statement with JOIN*
SELECT table1.column1,
    table2.column2
FROM  table1
    INNER JOIN table2
        ON table1.common_column = table2.common_column
-- WHERE clause with LIKE, AND, OR, NOT operators*
WHERE table1.column1 LIKE 'pattern%'
    AND table2.column2 LIKE '_pattern'
    OR table1.column3 > value
      AND NOT table1.column4 = value
      AND table1.column5 IS NOT NULL
      AND **MOD**(table1.column6, 2) = 0
-- GROUP BY clause with aggregate function*
GROUP BY table1.column1
-- ORDER BY clause*
ORDER BY table1.column3 DESC
-- LIMIT and OFFSET for pagination*
LIMIT 10 offset 5; 
```

