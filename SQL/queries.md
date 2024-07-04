## SQL Query Questions

#### Q1: Write a SQL Query that fetches the names of students whose name starts with A .The *students* table is given below 

| id   | name   | age  |
| ---- | ------ | ---- |
| 1    | Alice  | 20   |
| 2    | Bob    | 22   |
| 3    | Amanda | 19   |
| 4    | John   | 21   |
| 5    | Andrew | 23   |

**Answer**: The Query is provided below 

```sql
SELECT
  name
FROM
  students
WHERE
  name LIKE 'A%';
```

#### Q2: write a  SQL query to get the third maximum salary using `OFFSET`.The *Employees* table is given below 

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

#### Q3: display the number of employees working in each region

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
  region,
  COUNT(*) AS employee_count
FROM
  employees
GROUP BY
  region;
```

#### Q4: Write a SQL query to fetch employee names having a salary greater than or equal to 20000 and less than or equal to 100000 from the `employees` table.

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

#### Q5: Given a table Employee having columns empName and empId, what will be the result of the SQL query below? 

```sql
SELECT
  empName
FROM
  Employee
ORDER by
  2 ASC
```

**Answer**: orders the result set by the second column in the select list, which in this case is `empName`.

#### Q6: Write an SQL query to delete the column `region` from the `employees` table.

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

#### Q7: Based on the employees table write a sql query to find the 7th highest salary 

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

#### Q8: Given the `employees` table, write a SQL query to add a new column named `department` to the table.

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

