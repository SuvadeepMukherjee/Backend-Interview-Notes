## These are all the final Notes on SQL Queries 

#### Q1: Write a generalized SQL Query 

**Answer**: A generalized sql query incorporates the following 

1. A statement to select specific columns from two tables, incorporating a join condition.
2. A clause to filter records based on specific patterns, logical operators, non-null values, and a numeric function.
3. A clause to group the results by one or more columns.
4. A clause to sort the results.
5. Clauses to limit the number of results and specify an offset for pagination.

A sample query is shown below 

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

