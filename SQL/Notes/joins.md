

## Joins Notes: 

The following table gives a simple defination of Inner,left and Right Join 



| Join       | Definition                                         |
| ---------- | -------------------------------------------------- |
| Inner Join | *Fectches matching records only*                   |
| Left Join  | *Inner Join + additional records from left table*  |
| Right Join | *Inner Join + additional records from right table* |

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

#### Inner Join 

```sql
SELECT
  emp_name,
  dept_name
FROM
  Employee
  INNER JOIN Department ON Employee.dept_id = Department.dept_id
```

Employee: D1,D2,D10 , Department: D1,D2,D3,D4 Common: D1,D2

The result will be the following 

| Name    | dept_name |
| ------- | --------- |
| Rahul   | IT        |
| Manoj   | IT        |
| James   | HR        |
| Michael | HR        |

#### Left Join

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

#### Right Join : 

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

#### Q: Fetch details of all employee, their manager , their department and the projects they work on 

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

 
