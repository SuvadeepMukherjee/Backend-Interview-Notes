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

#### Q16:Given the `employees` table, write a SQL query to find out the data of employees whose age is between 25 and 35 inclusive.

**Table: employees**

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

#### Table for Q17,Q18,Q19,20

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

#### Q17:Write a SQL query to retrieve all employees FirstName along with their department names using an INNER JOIN. Order the results by `LastName` in ascending order.

**Answer**: The SQL Query is provided below 

```sql
SELECT firstname,
    departmentname
FROM  employees
    INNER JOIN departments
        ON employees.departmentid = departments.departmentid
ORDER BY lastname ASC 
```



#### Q18:Write a SQL query to retrieve all employees FirstName and their department names, including those employees who do not belong to any department, using a LEFT JOIN. Order the results by `LastName` in ascending order.

**Answer**:The SQL Query is written below 

```sql
SELECT firstname,
    departmentname
FROM  employees
    LEFT JOIN departments
       ON employees.departmentid = departments.departmentid
ORDER BY lastname ASC 
```



#### Q19:Write a SQL query to retrieve all departments and their employee FirstName, including those departments that do not have any employees, using a RIGHT JOIN. Order the results by `DepartmentName` in ascending order.

**Answer**: The SQL Query is written below 

```sql
SELECT firstname,
    departmentname
FROM  employees
    RIGHT JOIN departments
        ON employees.departmentid = departments.departmentid
ORDER BY departmentname ASC 
```



#### Q20:Write a SQL query to retrieve all employees and their department names, including employees without departments and departments without employees, using a FULL OUTER JOIN. Order the results by `LastName` in ascending order.

**Answer**:  The SQL Query is written below 

```sql
SELECT firstname,
    departmentname
FROM  employees
    full OUTER JOIN join Departments
          ON employees.departmentid = Departments.departmentid
ORDER BY lastname ASC 
```

#### Q21:Create an index on the `age` column on the `Students` table shown below 

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

#### Q1: In a tabular format write the defination of all the joins i.e inner join , left join , right join , full outer join ,cross join , natural join , self join and their syntax



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

#### Q2: Given the Employee and Department tables, write an SQL query to retrieve the employee names along with their respective department names, but only for those employees whose department names are known.



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

```
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

#### Q3:Given the employee and department tables, write an sql query to retrieve the employee names along with their respective department names, including employees whose department names are not known.



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

```
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

#### Q4:Given the employee and department tables, write a sql query to retrieve all department names along with their respective employee names, including departments that do not have any employees.



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

```
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

#### Q5:Consider the following tables:



#### employee Table:



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

manager Table:

| manager_id | manager_name | dept-id |
| ---------- | ------------ | ------- |
| M1         | Prem         | D3      |
| M2         | Shripadh     | D4      |
| M3         | Nick         | D1      |
| M4         | Cory         | D1      |

projects Table

| project_id | project_name   | team_member_id |
| ---------- | -------------- | -------------- |
| P1         | Data Migration | E1             |
| P1         | Data Migration | E2             |
| P1         | Data Migration | M3             |
| P2         | ETL Tool       | E1             |
| P2         | ETL Tool       | M4             |

Write a sql query to *fetch details of all employee, their manager , their department and the projects they work on*

**Answer**: The sql query is shown in the follwing code snippet

```
SELECT
  e.emp_name,
  d.dept_name,
  m.manager_name,
  p.project_name
FROM
  employee e
  LEFT JOIN department d ON e.dept_id = d.dept_id
  INNER JOIN manager m ON m.manager_id = e.manager_id
  LEFT JOIN projects P ON p.team_member_id = e.emp_id;
```



The output will be the follwing :

| emp_name | dept_name | manager_name | project_name   |
| -------- | --------- | ------------ | -------------- |
| Rahul    | IT        | Prem         | ETL Tool       |
| Rahul    | IT        | Prem         | Data Migration |
| Manoj    | IT        | Prem         | Data Migration |
| James    | HR        | Shripadh     | NULL           |
| Michael  | HR        | Shripadh     | NULL           |
| Ali      | NULL      | Nick         | NULL           |
| Robin    | NULL      | Nick         | NULL           |

#### Q6: Given the Employee and Department tables, write an SQL query to retrieve the employee names and their respective departments ,If an employee does not have an department ouput NULL , similarly if a department does not have employees output null



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

```
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

#### Q7:



Joins Notes Part 2:

Consider the following tables:

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

#### Full Outer Join



Full Outer Join = Inner Join + Left Join + Right Join

Example query :

|      |      |
| ---- | ---- |
|      |      |
|      |      |
|      |      |
|      |      |
|      |      |
|      |      |
|      |      |
|      |      |

#### Cross Join :



**Defination**: A **Cross Join** in SQL is a type of join that returns the Cartesian product of two tables. This means it combines each row from the first table with every row from the second table, resulting in a result set that contains all possible combinations of rows from both tables. Cross joins do not require any condition to join the tables.

##### Q: Write a query to fetch the Employee table and their corresponding department name .Also make sure to display the company name and the company location corresponding to each employee



**Answer**: We write the follwing query

```
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

#### Natural join



Natural Join = Cross join + condition(inner join )

Sql will decide on the join condition based on common table names

```
SELECT e.emp_name,d.dept_name
FROM employee e
NATURAL JOIN department d ;
```



In the above sql query the join condition will be dept_id

| emp_name | dept_name |
| -------- | --------- |
| Rahul    | IT        |
| Manoj    | IT        |
| James    | HR        |
| Michael  | HR        |

#### Self Join



In self join we join a table with itself , we can do inner join .left join ,right join ,full outer join , cross join or natural join

Consider the following *Family* table :

| member_id | name    | age  | parent_id |
| --------- | ------- | ---- | --------- |
| F1        | David   | 4    | F5        |
| F2        | Carol   | 10   | F5        |
| F3        | Michael | 12   | F5        |
| F4        | Johnson | 36   |           |
| F5        | Morgan  | 40   | F6        |
| F6        | Stewart | 70   |           |
| F7        | Rohan   | 6    | F4        |
| F8        | Asha    | 8    | F4        |

##### Q: Write a query to fetch the child name and their age corresponding to their parent name ?



**Answer**:The query is shown in the following table

```
SELECT
  child.name as child_name,
  child.age as child_age,
  parent.name as parent_name,
  parent.age as parent_age
FROM
  family as child
  join family as parent on child.parent_id = parent.member_id;
```



The output would be the follwing

| child_name | child_age | parent_name | parent_age |
| ---------- | --------- | ----------- | ---------- |
| David      | 4         | Morgan      | 40         |
| Carol      | 10        | Morgan      | 40         |
| Michael    | 12        | Morgan      | 40         |
| Morgan     | 40        | Stewart     | 70         |
| Rohan      | 6         | Johnson     | 36         |
| Asha       | 8         | Johnson     | 36         |
