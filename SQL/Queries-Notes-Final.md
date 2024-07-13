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
| full outer join | *inner join + left join + right join*                        | select column_name(s) from table1 full outer join table2 on table1.column_name = table2.column_name; |
| cross join      | Cartesian Product of 2 tables                                | select column_name(s) from table1 cross join table2;         |
| natural join    | Cross Join + Condition sql will decide the join condition based on common table name(INNER JOIN) | select column_name(s) from table1 natural JOIN table2;       |
| self join       | The table joins itself (Can be INNER JOIN,LEFT JOIN,RIGHT JOIN ,FULL OUTER JOIN ,CROSS JOIN ,NATURAL JOIN) | syntax can vary                                              |

#### Q9: Write a SQL Query that fetches the names of students whose name starts with A .The *students* table is given below



| id   | name   | age  |
| ---- | ------ | ---- |
| 1    | Alice  | 20   |
| 2    | Bob    | 22   |
| 3    | Amanda | 19   |
| 4    | John   | 21   |
| 5    | Andrew | 23   |

**Answer**:The Query is provided below

```sql
SELECT
  name
FROM
  students
WHERE
  name LIKE 'A%';
```

#### Q10:Write a SQL query to get the third maximum salary using `OFFSET`.The *Employees* table is given below



| id   | name   | salary |
| ---- | ------ | ------ |
| 1    | John   | 50000  |
| 2    | Alice  | 60000  |
| 3    | Bob    | 70000  |
| 4    | Amanda | 80000  |
| 5    | Andrew | 90000  |

**Answer**: The sql query is written below

```sql
SELECT
  salary
FROM
  employees
ORDER BY
  salary DESC
LIMIT
  1
OFFSET
  2;
```

#### Q11(Q3)Write the SQL Query that display the region and the number of employees working in each region



Table name: `employees`

| id   | name   | salary | region |
| ---- | ------ | ------ | ------ |
| 1    | John   | 50000  | North  |
| 2    | Alice  | 60000  | South  |
| 3    | Bob    | 70000  | North  |
| 4    | Amanda | 80000  | East   |

**Answer**:The query is written below

```sql
SELECT
  region,
  COUNT(*) AS employee_count
FROM
  employees
GROUP BY
  region;
```

#### Q12(Q4): Write a SQL query to fetch employee names having a salary greater than or equal to 20000 and less than or equal to 100000 from the `employees` table.



Table name: `employees`

| id   | name   | salary | region |
| ---- | ------ | ------ | ------ |
| 1    | John   | 50000  | North  |
| 2    | Alice  | 60000  | South  |
| 3    | Bob    | 70000  | North  |
| 4    | Amanda | 80000  | East   |

**Answer**: The query is written below

```sql
SELECT
  name
FROM
  employees
WHERE
  salary >= 20000
  AND salary <= 100000;
```

#### Q13(Q5)Given a table `Employee` having columns `empName` and `empId`, what will be the result of the SQL query below?

```sql
sql
Copy code
SELECT
  empName,
  empId
FROM
  Employee
ORDER BY
  2 ASC;
```

**Answer**: The query orders the result set by the `empId` column in ascending order because `ORDER BY 2` refers to the second column in the `SELECT` list, which is `empId`.

#### Q17(Q6): Write an SQL query to delete the column `region` from the `employees` table.



**Example Scenario:**

You have a table named `employees` with the following structure:

Table name: `employees`

| id   | name   | salary | region |
| ---- | ------ | ------ | ------ |
| 1    | John   | 50000  | North  |
| 2    | Alice  | 60000  | South  |
| 3    | Bob    | 70000  | North  |
| 4    | Amanda | 80000  | East   |

**Answer**: The SQL statement is written below

```sql
ALTER TABLE employees
DROP COLUMN region;
```

#### Q18(Q7): Based on the employees table write a sql query to find the 7th highest salary



**Table: employees**

| id   | name    | salary |
| ---- | ------- | ------ |
| 1    | Alice   | 5000   |
| 2    | Bob     | 6000   |
| 3    | Charlie | 7000   |
| 4    | David   | 8000   |
| 5    | Eve     | 9000   |
| 6    | Frank   | 10000  |
| 7    | Grace   | 11000  |

**Answer**: The SQL Query is written below

```sql
SELECT
  salary
FROM
  employees
ORDER BY
  salary DESC
LIMIT
  1
OFFSET
  6;
```

#### Q19(Q8): Given the `employees` table, write a SQL query to add a new column named `department` to the table.



**Table: employees**

| id   | name    | salary |
| ---- | ------- | ------ |
| 1    | Alice   | 5000   |
| 2    | Bob     | 6000   |
| 3    | Charlie | 7000   |
| 4    | David   | 8000   |
| 5    | Eve     | 9000   |
| 6    | Frank   | 10000  |
| 7    | Grace   | 11000  |

**Answer**: The SQL Query is written below:

```sql
ALTER TABLE employees
ADD COLUMN department VARCHAR(50);
```
