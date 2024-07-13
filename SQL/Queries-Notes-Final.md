## These are all the final Notes on SQL Queries 

#### Q1: Write a generalized SQL Query 

**Answer**: A generalized sql query incorporates the following 

1. A statement to select specific columns from two tables, incorporating a join condition.
2. A clause to filter records based on specific patterns, logical operators, non-null values, and a numeric function(WHERE clause with AND,OR,NOT,LIKE,MOD,IS NULL etc).
3. A clause to group the results by one or more columns.(GROUP BY clause often used with aggregate functions).
4. A clause to sort the results(ORDER BY clause)
5. Clauses to limit the number of results and specify an offset for pagination(LIMIT And OFFSET).

A sample query is shown below 

```sql
-- SELECT statement with JOIN
SELECT table1.column1,
    table2.column2
FROM  table1
    INNER JOIN table2
        ON table1.common_column = table2.common_column
-- WHERE clause with LIKE, AND, OR, NOT operators
WHERE table1.column1 LIKE 'pattern%'
    AND table2.column2 LIKE '_pattern'
    OR table1.column3 > value
      AND NOT table1.column4 = value
      AND table1.column5 IS  NULL
      AND MOD(table1.column6, 2) = 0
-- GROUP BY clause with aggregate function
GROUP BY table1.column1
-- ORDER BY clause
ORDER BY table1.column3 DESC
-- LIMIT and OFFSET for pagination
LIMIT 10 offset 5; 
```

#### Q2:What is the purpose of the `LIKE` operator ins SQL ? 

**Answer**:The `LIKE` operator is used in a `WHERE` clause to search for a specified pattern in a column.

**Wildcards**:

- `%` represents zero, one, or multiple characters
- `_` represents one single character

#### Q3:The `ORDER BY` keyword is used to sort the result set in ascending or descending order. By default it sorts in what  order ?

**Answer**:The `ORDER BY` keyword is used to sort the result set in ascending or descending order. By default, it sorts in ascending order. To sort in descending order, use the `DESC` keyword.

#### Q4:What is the purpose of the `LIMIT` and `OFFSET` clauses in SQL?

**Answer**:The `LIMIT` clause specifies the number of records to return. The `OFFSET` clause skips a specified number of rows before starting to return rows from the query result.

#### Q5:What are SQL aggregate functions and where are they commonly used ? 

**Answer**: Aggregate functions perform a calculation on a set of values and return a single value. They are often used with the `GROUP BY` clause to group the result set by one or more columns.

**Common Aggregate Functions**:

- `COUNT()`: Returns the number of rows that match a specified criterion.

#### Q6:How does the `GROUP BY` statement work in SQL?

**Answer**:The `GROUP BY` statement groups rows that have the same values into summary rows. It is often used with aggregate functions like `COUNT()`, `MAX()`, `MIN()`, `SUM()`, and `AVG()`.

#### Q7:MySQL Functions 

| MySQL Functions | Syntax             | defination                                                  |
| --------------- | ------------------ | ----------------------------------------------------------- |
| MOD             | Mod()              | returns the remainder of a number divided by another number |
| ISNULL          | ISNULL(expression) | returns 1 or 0 depending whether an expression is `NULL`    |

#### Q8: In a tabular format write the defination of all the joins i.e inner join , left join , right join , full outer join ,cross join , natural join , self join and their syntax

**Answer**:The following table explains all the types of joins and their corresponding syntax

| Join            | Definition                                                   | Syntax                                                       |
| --------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| inner join      | *Fetches matching records only*                              | select column_name(s) from table1 inner join table2 on table1.column_name = table2.column_name; |
| left join       | *inner join + additional records from left table*            | select column_name(s) from table1 left join table2 on table1.column_name = table2.column_name; |
| right join      | *inner join + additional records from right table*           | select column_name(s) from table1 right join table2 on table1.column_name = table2.column_name; |
| full outer join | *inner join + left join + right join*                        | select column_name**(s) from table1 full outer join table2 on table1.column_name = table2.column_name; |
| cross join      | Cartesian Product of 2 tables                                | select column_name**(s) from table1 cross join table2;       |
| natural join    | Cross Join + Condition sql will decide the join condition based on common table name(INNER JOIN) | select column_name**(s) from table1 natural JOIN table2;     |
| self join       | The table joins itself (Can be INNER JOIN,LEFT JOIN,RIGHT JOIN ,FULL OUTER JOIN ,CROSS JOIN ,NATURAL JOIN) | syntax can vary                                              |
