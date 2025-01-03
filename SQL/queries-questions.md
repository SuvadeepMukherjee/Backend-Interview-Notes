## Questions  on SQL Queries 

#### Q1: Write a generalized SQL Query 

#### **Answer**: A generalized sql query incorporates the following 

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

#### Q4:How to test for NULL Values ? 

**Answer**:We will have to use the `IS NULL` and `IS NOT NULL` operators instead.

`IS NULL` Syntax: 

```sql
SELECT column_names
FROM table_name
WHERE column_name IS NULL;
```

`IS NOT NULL` Syntax: 

```sql
SELECT column_names
FROM table_name
WHERE column_name IS NOT NULL;
```



#### Q5:What is the purpose of the `LIMIT` and `OFFSET` clauses in SQL?

**Answer**:The `LIMIT` clause specifies the number of records to return. The `OFFSET` clause skips a specified number of rows before starting to return rows from the query result.

#### Q6:What are SQL aggregate functions and where are they commonly used ? 

**Answer**: Aggregate functions perform a calculation on a set of values and return a single value. They are often used with the `GROUP BY` clause to group the result set by one or more columns.

**Common Aggregate Functions**:

- `COUNT()`: Returns the number of rows that match a specified criterion.

#### Q7:How does the `GROUP BY` statement work in SQL?

**Answer**:The `GROUP BY` statement groups rows that have the same values into summary rows. It is often used with aggregate functions like `COUNT()`, `MAX()`, `MIN()`, `SUM()`, and `AVG()`.

#### Q8:MySQL Functions 

| MySQL Functions | Syntax             | defination                                                  |
| --------------- | ------------------ | ----------------------------------------------------------- |
| MOD             | Mod(x,y)           | returns the remainder of a number divided by another number |
| ISNULL          | ISNULL(expression) | returns 1 or 0 depending whether an expression is `NULL`    |

#### Q9: In a tabular format write the defination of all the joins i.e inner join , left join , right join , full outer join ,cross join , natural join , self join and their syntax

**Answer**:The following table explains all the types of joins and their corresponding syntax

| Join            | Definition                                                   | Syntax                                                       |
| --------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| inner join      | *Fetches matching records only*                              | select column_name(s) from table1 inner join table2 on table1.column_name = table2.column_name; |
| left join       | *inner join + additional records from left table*            | select column_name(s) from table1 left join table2 on table1.column_name = table2.column_name; |
| right join      | *inner join + additional records from right table*           | select column_name(s) from table1 right join table2 on table1.column_name = table2.column_name; |
| full outer join | *inner join + left join + right join*                        | select column_name(s) from table1 full outer join table2 on table1.column_name = table2.column_name; |
| cross join      | *Cartesian Product of 2 tables*                              | select column_name(s) from table1 cross join table2;         |
| natural join    | *Cross Join + Condition (sql will decide the join condition based on common table name mostly INNER JOIN)* | select column_name(s) from table1 natural JOIN table2;       |
| self join       | *The table joins itself (Can be INNER JOIN,LEFT JOIN,RIGHT JOIN ,FULL OUTER JOIN ,CROSS JOIN ,NATURAL JOIN)* | syntax can vary                                              |

#### Q10: Write a SQL Query that fetches the names of students whose name starts with A .The *students* table is given below

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

#### Q11:Write a SQL query to get the third maximum salary using `OFFSET`.The *Employees* table is given below

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

#### Q12:Write the SQL Query that display the region and the number of employees working in each region

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

#### Q13: Write a SQL query to fetch employee names having a salary greater than or equal to 20000 and less than or equal to 100000 from the `employees` table.

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

#### Q14:Given a table `Employee` having columns `empName` and `empId`, what will be the result of the SQL query below?

```sql
SELECT
  empName,
  empId
FROM
  Employee
ORDER BY
  2 ASC;
```

**Answer**: The query orders the result set by the `empId` column in ascending order because `ORDER BY 2` refers to the second column in the `SELECT` list, which is `empId`.

#### Q15: Write an SQL query to delete the column `region` from the `employees` table.

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

#### Q16: Based on the employees table write a sql query to find the 7th highest salary

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

#### Q17: Given the `employees` table, write a SQL query to add a new column named `department` to the table.

#### **Table: employees**

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

#### Q18:Given the `students` table, write a SQL query to display the records with odd `id` values.

**Table: students**

| id   | name    | age  |
| ---- | ------- | ---- |
| 1    | Alice   | 20   |
| 2    | Bob     | 21   |
| 3    | Charlie | 22   |
| 4    | David   | 23   |
| 5    | Eve     | 24   |
| 6    | Frank   | 25   |
| 7    | Grace   | 26   |

**Answer**: The SQL Query is written below :

```sql
SELECT
  *
FROM
  students
WHERE
  MOD(id, 2) = 1;
```

#### Q19:Given the `students` table, write a SQL query to fetch alternate records (e.g., records with odd `id` values).

**Table: students**

| id   | name    | age  |
| ---- | ------- | ---- |
| 1    | Alice   | 20   |
| 2    | Bob     | 21   |
| 3    | Charlie | 22   |
| 4    | David   | 23   |
| 5    | Eve     | 24   |
| 6    | Frank   | 25   |
| 7    | Grace   | 26   |

**Answer**: The SQL Query is shown below

```sql
SELECT
  *
FROM
  students
WHERE
  MOD(id, 2) = 1;
```

#### Q20:Given the `employees` table, write a SQL query to display details of employees who belong to the ECE department.

**Table: employees**

| id   | name    | department |
| ---- | ------- | ---------- |
| 1    | Alice   | ECE        |
| 2    | Bob     | CSE        |
| 3    | Charlie | ECE        |
| 4    | David   | Mech       |
| 5    | Eve     | ECE        |
| 6    | Frank   | EEE        |
| 7    | Grace   | CSE        |

**Answer**: The sql query is written below

```sql
SELECT
  *
FROM
  employees
WHERE
  department = 'ECE';
```

#### Q21:Given the `books` table, write a SQL query to return 100 books starting from the 105th book.

**Table: books**

| book_id | title                    | author              | genre           | publish_date |
| ------- | ------------------------ | ------------------- | --------------- | ------------ |
| 101     | "The Great Gatsby"       | F. Scott Fitzgerald | Fiction         | 1925-04-10   |
| 102     | "To Kill a Mockingbird"  | Harper Lee          | Fiction         | 1960-07-11   |
| 103     | "1984"                   | George Orwell       | Science Fiction | 1949-06-08   |
| 104     | "Pride and Prejudice"    | Jane Austen         | Romance         | 1813-01-28   |
| 105     | "The Catcher in the Rye" | J.D. Salinger       | Fiction         | 1951-07-16   |
| ...     | ...                      | ...                 | ...             | ...          |
| 204     | "Crime and Punishment"   | Fyodor Dostoevsky   | Fiction         | 1866-12-22   |

**Answer**: The SQL Query is shown below

```sql
SELECT
  *
FROM
  books
ORDER BY
  book_id
LIMIT
  100
OFFSET
  104;
```

#### Q22: Given the `users` table, write a SQL query to select all users whose email and phone_number are both NULL.

**Table: users**

| user_id | username  | email                                         | phone_number |
| ------- | --------- | --------------------------------------------- | ------------ |
| 1       | alice123  | [alice@email.com](mailto:alice@email.com)     | NULL         |
| 2       | bob456    | NULL                                          | 9876543210   |
| 3       | charlie89 | [charlie@email.com](mailto:charlie@email.com) | NULL         |
| 4       | david23   | NULL                                          | NULL         |
| 5       | eve55     | [eve@email.com](mailto:eve@email.com)         | 1234567890   |
| 6       | frank78   | [frank@email.com](mailto:frank@email.com)     | 8765432109   |

**Answer**: The SQL Query is written below

```sql
SELECT
  *
FROM
  users
WHERE
  email IS NULL
  AND phone_number IS NULL;
```

#### Q23:Given the `employees` table, write a SQL query to fetch the top five maximum salaries.

#### **Table: employees**

| id   | name    | salary |
| ---- | ------- | ------ |
| 1    | Alice   | 5000   |
| 2    | Bob     | 6000   |
| 3    | Charlie | 7000   |
| 4    | David   | 8000   |
| 5    | Eve     | 9000   |
| 6    | Frank   | 10000  |
| 7    | Grace   | 11000  |
| 8    | Hank    | 12000  |
| 9    | Ivy     | 13000  |
| 10   | Jack    | 14000  |

**Answer**: The SQL Querry is written below

```sql
SELECT
  salary
FROM
  employees
ORDER BY
  salary DESC
LIMIT
  5;
```

#### Q24:Given the `employees` table, write a SQL query to get the second last `id` without using the `MAX` function.

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
| 8    | Hank    | 12000  |
| 9    | Ivy     | 13000  |
| 10   | Jack    | 14000  |

**Answer**: The SQL Query is written below

```sql
SELECT
  id
FROM
  employees
ORDER BY
  id DESC
LIMIT
  1
OFFSET
  1;
```

#### Q25:Given the `employees` table, write a SQL query to find out the data of employees whose age is between 25 and 35 inclusive.

#### **Table: employees**

| id   | name    | age  |
| ---- | ------- | ---- |
| 1    | Alice   | 28   |
| 2    | Bob     | 30   |
| 3    | Charlie | 32   |
| 4    | David   | 35   |
| 5    | Eve     | 22   |
| 6    | Frank   | 27   |
| 7    | Grace   | 31   |
| 8    | Hank    | 36   |
| 9    | Ivy     | 25   |
| 10   | Jack    | 29   |

**Answer**: The SQL Query is written below

```sql
SELECT
  *
FROM
  employees
WHERE
  age >= 25
  AND age <= 35;
```

#### Q26: Given the Employee and Department tables, write an SQL query to retrieve the employee names along with their respective department names, but only for those employees whose department names are known.

employee Table:

| emp_id | emp_name | salary | dept_id | manager_id |
| ------ | -------- | ------ | ------- | ---------- |
| E1     | Rahul    | 15000  | D1      | M1         |
| E2     | Manoj    | 15000  | D1      | M1         |
| E3     | James    | 55000  | D2      | M2         |
| E4     | Michael  | 25000  | D2      | M2         |
| E5     | Ali      | 20000  | D10     | M3         |
| E6     | Robin    | 35000  | D10     | M3         |

department Table:

| dept_id | dept_name |
| ------- | --------- |
| D1      | IT        |
| D2      | HR        |
| D3      | Finance   |
| D4      | Admin     |

Write the SQL query below:

**Answer**: The SQL Query is written below

```sql
select
  emp_name,
  dept_name
from
  employee
  inner join department on employee.dept_id = department.dept_id
```

The result will be the following

| Name    | dept_name |
| ------- | --------- |
| Rahul   | IT        |
| Manoj   | IT        |
| James   | HR        |
| Michael | HR        |

#### Q27:Given the employee and department tables, write an sql query to retrieve the employee names along with their respective department names, including employees whose department names are not known.

employee Table:

| emp_id | emp_name | salary | dept_id | manager_id |
| ------ | -------- | ------ | ------- | ---------- |
| E1     | Rahul    | 15000  | D1      | M1         |
| E2     | Manoj    | 15000  | D1      | M1         |
| E3     | James    | 55000  | D2      | M2         |
| E4     | Michael  | 25000  | D2      | M2         |
| E5     | Ali      | 20000  | D10     | M3         |
| E6     | Robin    | 35000  | D10     | M3         |

department Table:

| dept_id | dept_name |
| ------- | --------- |
| D1      | IT        |
| D2      | HR        |
| D3      | Finance   |
| D4      | Admin     |

Write the SQL query below:

**Answer**: The sql Query is written below:

```sql
select
  e.emp_name,
  d.dept_name
from
  employee e
  left join department d on e.dept_id = d.dept_Id
```

The output will be the following :

| emp_name | dept_name |
| -------- | --------- |
| Rahul    | IT        |
| Manoj    | IT        |
| James    | HR        |
| Michael  | HR        |
| Ali      | NULL      |
| Robin    | NULL      |

#### Q28:Given the employee and department tables, write a sql query to retrieve all department names along with their respective employee names, including departments that do not have any employees.

employee Table:

| emp_id | emp_name | salary | dept_id | manager_id |
| ------ | -------- | ------ | ------- | ---------- |
| E1     | Rahul    | 15000  | D1      | M1         |
| E2     | Manoj    | 15000  | D1      | M1         |
| E3     | James    | 55000  | D2      | M2         |
| E4     | Michael  | 25000  | D2      | M2         |
| E5     | Ali      | 20000  | D10     | M3         |
| E6     | Robin    | 35000  | D10     | M3         |

department Table:

| dept_id | dept_name |
| ------- | --------- |
| D1      | IT        |
| D2      | HR        |
| D3      | Finance   |
| D4      | Admin     |

Write the SQL query below:

The sql Query is written below:

```sql
select
  e.emp_name,
  d.dept_name
from
  employee e
  right join department d on e.dept_id = d.dept_Id
```

The output will be the following

| emp_name | dept_name |
| -------- | --------- |
| Rahul    | IT        |
| Manoj    | IT        |
| James    | HR        |
| Michael  | HR        |
| NULL     | Finance   |
| NULL     | Admin     |

#### Q29: Given the Employee and Department tables, write an SQL query to retrieve the employee names and their respective departments ,If an employee does not have an department ouput NULL , similarly if a department does not have employees output null

Employee Table:

| emp_id | emp_name | salary | dept_id | manager_id |
| ------ | -------- | ------ | ------- | ---------- |
| E1     | Rahul    | 15000  | D1      | M1         |
| E2     | Manoj    | 15000  | D1      | M1         |
| E3     | James    | 55000  | D2      | M2         |
| E4     | Michael  | 25000  | D2      | M2         |
| E5     | Ali      | 20000  | D10     | M3         |
| E6     | Robin    | 35000  | D10     | M3         |

Department Table:

| dept_id | dept_name |
| ------- | --------- |
| D1      | IT        |
| D2      | HR        |
| D3      | Finance   |
| D4      | Admin     |

Write the SQL Query

**Answer**: The SQL Query is written below

```sql
SELECT
  e.emp_name,
  d.dept_name
FROM
  employee e
  FULL OUTER JOIN department d ON d.dept_id = e.dept_id;
```

The output will be the follwing:

| emp_name | dept_name |
| -------- | --------- |
| Rahul    | IT        |
| Manoj    | IT        |
| James    | HR        |
| Michael  | HR        |
| Ali      | NULL      |
| Robin    | NULL      |
| NULL     | Finance   |
| NULL     | Admin     |

#### Q30:Given the Employee , Department and Company tables write a query that retrieves the emp_name along with their respective dept_name but only for those employees whose department names are known also make sure to display the company_name and location 

Employee Table:

| emp_id | emp_name | salary | dept_id | manager_id |
| ------ | -------- | ------ | ------- | ---------- |
| E1     | Rahul    | 15000  | D1      | M1         |
| E2     | Manoj    | 15000  | D1      | M1         |
| E3     | James    | 55000  | D2      | M2         |
| E4     | Michael  | 25000  | D2      | M2         |
| E5     | Ali      | 20000  | D10     | M3         |
| E6     | Robin    | 35000  | D10     | M3         |

Department Table:

| dept_id | dept_name |
| ------- | --------- |
| D1      | IT        |
| D2      | HR        |
| D3      | Finance   |
| D4      | Admin     |

Company table:

| Company_id | company_name      | Location     |
| ---------- | ----------------- | ------------ |
| C001       | techTFQ Solutions | Kuala lumpur |

**Answer**:We write the follwing query

```sql
SELECT
  e.emp_name,
  d.dept_name,
  c.company_name,
  c.location
FROM
  empoyee e
  INNER JOIN department d ON e.dept_id = d.dept_id
  CROSS JOIN company c;
```

The output will be the following :

| emp_name | dept_name | comapny_name      | Location     |
| -------- | --------- | ----------------- | ------------ |
| Rahul    | IT        | techTFQ Solutions | kuala lampur |
| Manoj    | IT        | techTFQ Solutions | kuala lampur |
| James    | HR        | techTFQ Solutions | kuala lampur |
| Michael  | HR        | techTFQ Solutions | kuala lampur |

#### Q31: Given the Employee and Department tables, write an SQL query to retrieve the employee names along with their respective department names, but only for those employees whose department names are known.You cannot use `INNER JOIN`

employee Table:

| emp_id | emp_name | salary | dept_id | manager_id |
| ------ | -------- | ------ | ------- | ---------- |
| E1     | Rahul    | 15000  | D1      | M1         |
| E2     | Manoj    | 15000  | D1      | M1         |
| E3     | James    | 55000  | D2      | M2         |
| E4     | Michael  | 25000  | D2      | M2         |
| E5     | Ali      | 20000  | D10     | M3         |
| E6     | Robin    | 35000  | D10     | M3         |

department Table:

| dept_id | dept_name |
| ------- | --------- |
| D1      | IT        |
| D2      | HR        |
| D3      | Finance   |
| D4      | Admin     |

Write the SQL query below:

**Answer**: The SQL Query is written below

```sql
select
  emp_name,
  dept_name
from
  employee
  NATURAL join department 
```

The result will be the following

| Name    | dept_name |
| ------- | --------- |
| Rahul   | IT        |
| Manoj   | IT        |
| James   | HR        |
| Michael | HR        |

#### Table for Q32,Q33,Q34,35

**Employees**

| EmployeeID | FirstName | LastName | DepartmentID |
| ---------- | --------- | -------- | ------------ |
| 1          | John      | Doe      | 10           |
| 2          | Jane      | Smith    | 20           |
| 3          | Bob       | Johnson  | 10           |
| 4          | Alice     | Davis    | 30           |

**Departments**

| DepartmentID | DepartmentName |
| ------------ | -------------- |
| 10           | Sales          |
| 20           | Marketing      |
| 30           | HR             |
| 40           | IT             |

#### Q33:Write a SQL query to retrieve all employees FirstName along with their department names using an INNER JOIN. Order the results by `LastName` in ascending order.

**Answer**: The SQL Query is provided below

```sql
SELECT firstname,
    departmentname
FROM  employees
    INNER JOIN departments
        ON employees.departmentid = departments.departmentid
ORDER BY lastname ASC 
```

The result will be the following 

| FirstName | Department |
| --------- | ---------- |
| Alice     | HR         |
| John      | Sales      |
| Bob       | Sales      |
| Jane      | Marketing  |



#### Q34:Write a SQL query to retrieve all employees FirstName and their department names, including those employees who do not belong to any department, using a LEFT JOIN. Order the results by `LastName` in ascending order.

**Answer**:The SQL Query is written below

```sql
SELECT firstname,
    departmentname
FROM  employees
    LEFT JOIN departments
       ON employees.departmentid = departments.departmentid
ORDER BY lastname ASC 
```

The result will be the following 

| FirstName | Department |
| --------- | ---------- |
| Alice     | HR         |
| John      | Sales      |
| Bob       | Sales      |
| Jane      | Marketing  |



#### Q35:Write a SQL query to retrieve all departments and their employee FirstName, including those departments that do not have any employees, using a RIGHT JOIN. Order the results by `DepartmentName` in ascending order.

**Answer**: The SQL Query is written below

```sql
SELECT firstname,
    departmentname
FROM  employees
    RIGHT JOIN departments
        ON employees.departmentid = departments.departmentid
ORDER BY departmentname ASC 
```

The result will be the following: 

| FirstName | Department |
| --------- | ---------- |
| Alice     | HR         |
| NULL      | IT         |
| Jane      | Marketing  |
| John      | Sales      |
| Bob       | Sales      |

#### Q36:Write a SQL query to retrieve all employees and their department names, including employees without departments and departments without employees, using a FULL OUTER JOIN. Order the results by `LastName` in ascending order.

**Answer**: The SQL Query is written below

```sql
SELECT firstname,
    departmentname
FROM  employees
    full OUTER JOIN join Departments
          ON employees.departmentid = Departments.departmentid
ORDER BY lastname ASC 
```

#### Q37:Create an index on the `age` column on the `Students` table shown below

**students**

| id   | name    | age  | city        |
| ---- | ------- | ---- | ----------- |
| 1    | Alice   | 25   | New York    |
| 2    | Bob     | 28   | Los Angeles |
| 3    | Charlie | 22   | Chicago     |
| 4    | David   | 30   | Houston     |
| 5    | Eve     | 27   | Miami       |

**Answer**: The SQL Query is shown below

```sql
CREATE INDEX idx_age ON students (age); 
```
