## Joins Notes :

#### Q1: In a tabular format write the defination of all the joins i.e INNER JOIN , LEFT JOIN , RIGHT JOIN , FULL OUTER JOIN ,CROSS JOIN , NATURAL JOIN , SELF JOIN

**Answer**:The following table explains all the types of joins 

| Join            | Definition                                                   |
| --------------- | ------------------------------------------------------------ |
| INNER JOIN      | *Fetches matching records only*                              |
| LEFT JOIN       | *INNER JOIN + additional records from left table*            |
| RIGHT JOIN      | *INNER JOIN + additional records from right table*           |
| FULL OUTER JOIN | *INNER JOIN + LEFT JOIN +RIGHT JOIN*                         |
| CROSS JOIN      | *Cartesian Product of 2 Table*                               |
| NATURAL JOIN    | *Cross Join + Condition*<br/>*SQL Will decide the join condition based on common table names (INNER JOIN)* |
| SELF JOIN       | *The Table Joins with itself can be INNER JOIN , LEFT JOIN, RIGHT JOIN ,FULL OUTER JOIN ,CROSS JOIN or NATURAL JOIN* |

#### Q2: Given the Employee and Department tables, write an SQL query to retrieve the employee names along with their respective department names, but only for those employees whose department names are known.

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

Write the SQL query below:

**Answer**: The SQL Query is written below 

```sql
SELECT
  emp_name,
  dept_name
FROM
  Employee
  INNER JOIN Department ON Employee.dept_id = Department.dept_id
```

The result will be the following

| Name    | dept_name |
| ------- | --------- |
| Rahul   | IT        |
| Manoj   | IT        |
| James   | HR        |
| Michael | HR        |

#### Q3:Given the Employee and Department tables, write an SQL query to retrieve the employee names along with their respective department names, including employees whose department names are not known.

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

Write the SQL query below:

**Answer**: The SQL Query is written below: 

```sql
SELECT
  e.emp_name,
  d.dept_name
from
  employee e
  LEFT JOIN department d ON e.dept_id = d.dept_Id
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

#### Q4:Given the Employee and Department tables, write an SQL query to retrieve all department names along with their respective employee names, including departments that do not have any employees.

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

Write the SQL query below:

**Answer**: The SQL Query is written below: 

```sql
SELECT
  e.emp_name,
  d.dept_name
from
  employee e
  RIGHT JOIN department d ON e.dept_id = d.dept_Id
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

#### Employee Table:

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

Manager Table:

| manager_id | manager_name | dept-id |
| ---------- | ------------ | ------- |
| M1         | Prem         | D3      |
| M2         | Shripadh     | D4      |
| M3         | Nick         | D1      |
| M4         | Cory         | D1      |

Projects Table

| project_id | project_name   | team_member_id |
| ---------- | -------------- | -------------- |
| P1         | Data Migration | E1             |
| P1         | Data Migration | E2             |
| P1         | Data Migration | M3             |
| P2         | ETL Tool       | E1             |
| P2         | ETL Tool       | M4             |

Write a sql query to  *fetch details of all employee, their manager , their department and the projects they work on*

**Answer**: The sql query is shown in the follwing code snippet

```sql
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

#### Natural join

Natural Join = Cross join + condition(inner join )

Sql will decide on the join condition based on common table names

```sql
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

Consider the following _Family_ table :

| member_id | name    | age | parent_id |
| --------- | ------- | --- | --------- |
| F1        | David   | 4   | F5        |
| F2        | Carol   | 10  | F5        |
| F3        | Michael | 12  | F5        |
| F4        | Johnson | 36  |           |
| F5        | Morgan  | 40  | F6        |
| F6        | Stewart | 70  |           |
| F7        | Rohan   | 6   | F4        |
| F8        | Asha    | 8   | F4        |

##### Q: Write a query to fetch the child name and their age corresponding to their parent name ?

**Answer**:The query is shown in the following table

```sql
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
