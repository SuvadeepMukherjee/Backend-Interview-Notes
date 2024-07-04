## Joins Notes Part 2: 

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

