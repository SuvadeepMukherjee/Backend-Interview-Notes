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

#### Q9:Given the `students` table, write a SQL query to display the records with odd `id` values.

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

#### Q10:Given the `students` table, write a SQL query to fetch alternate records (e.g., records with odd `id` values).

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

#### Q11:Given the `employees` table, write a SQL query to display details of employees who belong to the ECE department.

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

#### Q12:Given the `books` table, write a SQL query to return 100 books starting from the 105th book.

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

#### Q13: Given the `users` table, write a SQL query to select all users whose email and phone_number are both NULL.

**Table: users**

| user_id | username  | email             | phone_number |
| ------- | --------- | ----------------- | ------------ |
| 1       | alice123  | alice@email.com   | NULL         |
| 2       | bob456    | NULL              | 9876543210   |
| 3       | charlie89 | charlie@email.com | NULL         |
| 4       | david23   | NULL              | NULL         |
| 5       | eve55     | eve@email.com     | 1234567890   |
| 6       | frank78   | frank@email.com   | 8765432109   |

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

#### Q14:Given the `employees` table, write a SQL query to fetch the top five maximum salaries.

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

#### Q15:Given the `employees` table, write a SQL query to get the second last `id` without using the `MAX` function.

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

