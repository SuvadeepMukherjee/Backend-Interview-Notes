

## Joins Notes

These are my notes related to joins 

###### Employee Table: 

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



### Inner Join 

**Fetch records that are present in both tables (only records that are getting matched based on the join condition will be fetched )**

```sql
SELECT
  emp_name,
  dept_name
FROM
  Employee
  INNER JOIN Department ON Employee.dept_id = Department.dept_id
```

Employee: D1,D2,D10

Department: D1,D2,D3,D4

Common: D1,D2

The result will be the following 

| Name    | dept_name |
| ------- | --------- |
| Rahul   | IT        |
| Manoj   | IT        |
| James   | HR        |
| Michael | HR        |



