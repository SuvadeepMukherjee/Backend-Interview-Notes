## SQL Query Questions

### Q1: Write a SQL Query that fetches the names of students whose name satrts with A .The *students* table is given below 

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

