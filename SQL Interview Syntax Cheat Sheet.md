# SQL Interview Syntax Cheat Sheet

This note is designed for **fresher / early-career Software Engineer interviews**.

The goal is not to memorize dozens of SQL queries.

Instead, remember a few **generalized query templates** and understand what to replace.

---

# 1. Basic `SELECT`

## General Syntax

```sql
SELECT column1, column2
FROM table_name;
```

### Replace

* `column1, column2` → columns you want
* `table_name` → table containing the data

### Example

```sql
SELECT name, salary
FROM Employee;
```

To select all columns:

```sql
SELECT *
FROM Employee;
```

---

# 2. `WHERE` — Filter Rows

## General Syntax

```sql
SELECT columns
FROM table_name
WHERE condition;
```

### Replace

* `columns` → required columns
* `table_name` → table name
* `condition` → filtering condition

### Example

```sql
SELECT *
FROM Employee
WHERE salary > 50000;
```

### Memory

> `WHERE` → Which rows do I want?

---

# 3. `AND` / `OR`

## AND

```sql
SELECT *
FROM table_name
WHERE condition1
AND condition2;
```

### Example

```sql
SELECT *
FROM Employee
WHERE salary > 50000
AND department = 'IT';
```

## OR

```sql
SELECT *
FROM table_name
WHERE condition1
OR condition2;
```

### Example

```sql
SELECT *
FROM Employee
WHERE department = 'IT'
OR department = 'HR';
```

---

# 4. `IN`

```sql
SELECT *
FROM table_name
WHERE column_name IN (value1, value2, value3);
```

### Example

```sql
SELECT *
FROM Employee
WHERE department IN ('IT', 'HR', 'Sales');
```

### Replace

* `column_name` → column to check
* `value1, value2...` → accepted values

---

# 5. `BETWEEN`

## General Syntax

```sql
SELECT *
FROM table_name
WHERE column_name BETWEEN lower_value AND upper_value;
```

### Example

```sql
SELECT *
FROM Employee
WHERE salary BETWEEN 40000 AND 60000;
```

> `BETWEEN` generally includes both boundary values.

---

# 6. `LIKE` — Pattern Matching

## General Syntax

```sql
SELECT *
FROM table_name
WHERE column_name LIKE 'pattern';
```

### Common Patterns

```sql
-- Starts with A
WHERE name LIKE 'A%';

-- Ends with A
WHERE name LIKE '%A';

-- Contains "raj"
WHERE name LIKE '%raj%';

-- Exactly 5 characters
WHERE name LIKE '_____';
```

### Memory

```text
% → Zero or more characters
_ → Exactly one character
```

---

# 7. `NULL`

Do not write:

```sql
WHERE manager_id = NULL;
```

Use:

```sql
WHERE manager_id IS NULL;
```

or:

```sql
WHERE manager_id IS NOT NULL;
```

## General Syntax

```sql
SELECT *
FROM table_name
WHERE column_name IS NULL;
```

---

# 8. `DISTINCT`

Used to remove duplicate values.

## General Syntax

```sql
SELECT DISTINCT column_name
FROM table_name;
```

### Example

```sql
SELECT DISTINCT department
FROM Employee;
```

### Memory

> `DISTINCT` → Give me unique values.

---

# 9. `ORDER BY`

Used to sort the result.

## Ascending

```sql
SELECT columns
FROM table_name
ORDER BY column_name ASC;
```

## Descending

```sql
SELECT columns
FROM table_name
ORDER BY column_name DESC;
```

### Example

```sql
SELECT *
FROM Employee
ORDER BY salary DESC;
```

### Memory

```text
ASC  → Small → Large
DESC → Large → Small
```

---

# 10. `LIMIT`

Used to return only a certain number of rows.

## General Syntax

```sql
SELECT *
FROM table_name
ORDER BY column_name DESC
LIMIT N;
```

### Example

```sql
SELECT *
FROM Employee
ORDER BY salary DESC
LIMIT 5;
```

### Meaning

> Return only the first 5 rows after sorting.

### Replace

* `column_name` → ranking/sorting column
* `N` → number of rows required

### Memory

> `LIMIT` → How many rows should I take?

---

# 11. `OFFSET` — Skip Rows

`OFFSET` is used when you want to **skip a certain number of rows before returning the result**.

It is commonly used together with `LIMIT`.

## General Syntax

```sql
SELECT columns
FROM table_name
ORDER BY column_name
LIMIT N
OFFSET M;
```

### Replace

* `N` → number of rows you want to return
* `M` → number of rows you want to skip

### Example

```sql
SELECT *
FROM Employee
ORDER BY salary DESC
LIMIT 5
OFFSET 10;
```

### Meaning

```text
Skip first 10 rows
        ↓
Return next 5 rows
```

### Memory

```text
OFFSET → Skip
LIMIT  → Take
```

---

## Pagination Using `LIMIT + OFFSET`

Suppose each page contains `10` rows.

```text
Page 1 → OFFSET 0  LIMIT 10
Page 2 → OFFSET 10 LIMIT 10
Page 3 → OFFSET 20 LIMIT 10
Page 4 → OFFSET 30 LIMIT 10
```

### Formula

```text
OFFSET = (pageNumber - 1) × pageSize
```

Example:

```text
pageNumber = 3
pageSize   = 10

OFFSET = (3 - 1) × 10
       = 20
```

Query:

```sql
SELECT *
FROM Employee
ORDER BY emp_id
LIMIT 10
OFFSET 20;
```

This means:

> Skip the first 20 rows and return the next 10 rows.

---

## MySQL Shortcut

MySQL also supports:

```sql
LIMIT offset, number_of_rows;
```

Example:

```sql
SELECT *
FROM Employee
ORDER BY emp_id
LIMIT 20, 10;
```

Meaning:

```text
Skip 20 rows
Take 10 rows
```

For interviews, the clearer form is usually easier to remember:

```sql
LIMIT N OFFSET M;
```

---

# 12. Aggregate Functions

Used to perform calculations over multiple rows.

## General Syntax

```sql
SELECT AGGREGATE_FUNCTION(column_name)
FROM table_name;
```

### Common Aggregate Functions

```sql
COUNT(*)
SUM(column)
AVG(column)
MIN(column)
MAX(column)
```

### Examples

```sql
SELECT COUNT(*)
FROM Employee;
```

```sql
SELECT AVG(salary)
FROM Employee;
```

```sql
SELECT MAX(salary)
FROM Employee;
```

---

# 13. `GROUP BY`

Used to group rows having common values.

## General Syntax

```sql
SELECT group_column, AGGREGATE_FUNCTION(column)
FROM table_name
GROUP BY group_column;
```

### Example

```sql
SELECT department, AVG(salary)
FROM Employee
GROUP BY department;
```

### Replace

* `group_column` → what you want to group by
* `AGGREGATE_FUNCTION` → `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`
* `column` → column on which calculation is performed

### Interview Translation

Question:

> Find the number of employees in each department.

Think:

```text
"each department" → GROUP BY department

"number of employees" → COUNT(*)
```

Query:

```sql
SELECT department, COUNT(*)
FROM Employee
GROUP BY department;
```

---

# 14. `HAVING`

Used to filter groups after `GROUP BY`.

## General Syntax

```sql
SELECT group_column, AGGREGATE_FUNCTION(column)
FROM table_name
GROUP BY group_column
HAVING AGGREGATE_FUNCTION(column) condition;
```

### Example

```sql
SELECT department, AVG(salary)
FROM Employee
GROUP BY department
HAVING AVG(salary) > 50000;
```

### Memory

```text
WHERE  → Filters rows
HAVING → Filters groups
```

---

# 15. Complete `GROUP BY` Pattern

```sql
SELECT group_column,
       AGGREGATE_FUNCTION(column)
FROM table_name
WHERE row_condition
GROUP BY group_column
HAVING aggregate_condition
ORDER BY result_column DESC;
```

### Example

```sql
SELECT department,
       AVG(salary) AS avg_salary
FROM Employee
WHERE status = 'ACTIVE'
GROUP BY department
HAVING AVG(salary) > 50000
ORDER BY avg_salary DESC;
```

---

# 16. `INNER JOIN`

Returns matching rows from both tables.

## General Syntax

```sql
SELECT columns
FROM TableA a
INNER JOIN TableB b
ON a.common_column = b.common_column;
```

### Replace

* `TableA` → first table
* `TableB` → second table
* `common_column` → relationship between tables

### Example

```sql
SELECT e.name,
       d.department_name
FROM Employee e
INNER JOIN Department d
ON e.department_id = d.department_id;
```

### Memory

```text
FROM
JOIN
ON
```

---

# 17. `LEFT JOIN`

Returns:

> All rows from the left table + matching rows from the right table.

## General Syntax

```sql
SELECT columns
FROM TableA a
LEFT JOIN TableB b
ON a.key = b.key;
```

### Example

```sql
SELECT e.name,
       d.department_name
FROM Employee e
LEFT JOIN Department d
ON e.department_id = d.department_id;
```

### Memory

> `LEFT JOIN` → Keep everything from the left table.

---

# 18. `RIGHT JOIN`

Returns:

> All rows from the right table + matching rows from the left table.

## General Syntax

```sql
SELECT columns
FROM TableA a
RIGHT JOIN TableB b
ON a.key = b.key;
```

---

# 19. `FULL OUTER JOIN`

Returns:

* Matching rows
* Unmatched left-side rows
* Unmatched right-side rows

## General Syntax

```sql
SELECT columns
FROM TableA a
FULL OUTER JOIN TableB b
ON a.key = b.key;
```

> MySQL does not directly support `FULL OUTER JOIN`.

---

# 20. Universal JOIN Template

```sql
SELECT columns
FROM TableA a
<JOIN_TYPE> TableB b
ON a.key = b.key;
```

Replace:

```text
<JOIN_TYPE>

INNER JOIN
LEFT JOIN
RIGHT JOIN
FULL OUTER JOIN
```

---

# 21. Find Rows With No Match

Very common interview pattern.

## General Syntax

```sql
SELECT a.*
FROM TableA a
LEFT JOIN TableB b
ON a.key = b.key
WHERE b.key IS NULL;
```

### Example

Find employees not assigned to any department:

```sql
SELECT e.*
FROM Employee e
LEFT JOIN Department d
ON e.department_id = d.department_id
WHERE d.department_id IS NULL;
```

### Memory

```text
LEFT JOIN
+
WHERE right_table.id IS NULL
```

means:

> Find unmatched records.

---

# 22. `SELF JOIN`

Used when a table is related to itself.

Example:

```text
Employee

emp_id
name
manager_id
```

## General Syntax

```sql
SELECT ...
FROM Table t1
JOIN Table t2
ON t1.foreign_key = t2.primary_key;
```

### Example

```sql
SELECT e.name AS employee,
       m.name AS manager
FROM Employee e
LEFT JOIN Employee m
ON e.manager_id = m.emp_id;
```

### Memory

> Same table, different aliases.

---

# 23. Subquery

A query inside another query.

## General Syntax

```sql
SELECT *
FROM table_name
WHERE column_name operator (
    SELECT ...
    FROM ...
);
```

### Example

Find employees earning more than average salary:

```sql
SELECT *
FROM Employee
WHERE salary > (
    SELECT AVG(salary)
    FROM Employee
);
```

### Memory

```text
Calculate something first
        ↓
Use that result in another query
```

---

# 24. Second Highest Salary

```sql
SELECT MAX(salary)
FROM Employee
WHERE salary < (
    SELECT MAX(salary)
    FROM Employee
);
```

### Logic

```text
Find highest salary
      ↓
Ignore highest
      ↓
Find maximum of remaining salaries
```

---

# 25. Window Functions

General structure:

```sql
FUNCTION() OVER (
    PARTITION BY group_column
    ORDER BY order_column
)
```

Common functions:

```sql
ROW_NUMBER()
RANK()
DENSE_RANK()
```

---

# 26. `ROW_NUMBER()`

Assigns a unique sequential number.

```sql
SELECT name,
       salary,
       ROW_NUMBER() OVER (
           ORDER BY salary DESC
       ) AS row_num
FROM Employee;
```

---

# 27. `RANK()`

Ranks rows but leaves gaps after ties.

```text
Salary   Rank

90000     1
80000     2
80000     2
70000     4
```

Syntax:

```sql
RANK() OVER (
    ORDER BY salary DESC
)
```

---

# 28. `DENSE_RANK()`

Ranks rows without gaps after ties.

```text
Salary   Rank

90000     1
80000     2
80000     2
70000     3
```

Syntax:

```sql
DENSE_RANK() OVER (
    ORDER BY salary DESC
)
```

---

# 29. Nth Highest Salary

## General Syntax

```sql
SELECT *
FROM (
    SELECT *,
           DENSE_RANK() OVER (
               ORDER BY salary DESC
           ) AS rnk
    FROM Employee
) t
WHERE rnk = N;
```

### Replace

* `salary` → column to rank
* `N` → required rank

Example:

```sql
WHERE rnk = 3;
```

means:

> Third highest salary.

---

# 30. Ranking Inside Each Group

## General Syntax

```sql
SELECT *,
       DENSE_RANK() OVER (
           PARTITION BY group_column
           ORDER BY value_column DESC
       ) AS rnk
FROM table_name;
```

### Example

```sql
SELECT name,
       department,
       salary,
       DENSE_RANK() OVER (
           PARTITION BY department
           ORDER BY salary DESC
       ) AS rnk
FROM Employee;
```

### Memory

```text
PARTITION BY → Create logical groups
ORDER BY     → Decide ranking order
```

---

# 31. Top N Per Group

Question:

> Find the top 3 highest-paid employees in each department.

## General Syntax

```sql
SELECT *
FROM (
    SELECT *,
           DENSE_RANK() OVER (
               PARTITION BY group_column
               ORDER BY value_column DESC
           ) AS rnk
    FROM table_name
) t
WHERE rnk <= N;
```

### Example

```sql
SELECT *
FROM (
    SELECT *,
           DENSE_RANK() OVER (
               PARTITION BY department
               ORDER BY salary DESC
           ) AS rnk
    FROM Employee
) t
WHERE rnk <= 3;
```

---

# 32. Find Duplicate Values

## General Syntax

```sql
SELECT column_name,
       COUNT(*)
FROM table_name
GROUP BY column_name
HAVING COUNT(*) > 1;
```

### Example

```sql
SELECT email,
       COUNT(*)
FROM Users
GROUP BY email
HAVING COUNT(*) > 1;
```

### Memory

```text
Duplicates
=
GROUP BY
+
COUNT(*) > 1
```

---

# 33. `CASE WHEN`

SQL equivalent of `if-else`.

## General Syntax

```sql
SELECT column_name,
       CASE
           WHEN condition1 THEN result1
           WHEN condition2 THEN result2
           ELSE result3
       END AS alias
FROM table_name;
```

### Example

```sql
SELECT name,
       salary,
       CASE
           WHEN salary >= 80000 THEN 'High'
           WHEN salary >= 50000 THEN 'Medium'
           ELSE 'Low'
       END AS salary_category
FROM Employee;
```

### Memory

```text
CASE
WHEN
THEN
ELSE
END
```

---

# 34. `UNION`

Combines results from multiple queries.

```sql
SELECT column
FROM TableA

UNION

SELECT column
FROM TableB;
```

`UNION` removes duplicate rows.

---

# 35. `UNION ALL`

```sql
SELECT column
FROM TableA

UNION ALL

SELECT column
FROM TableB;
```

Keeps duplicate rows.

### Memory

```text
UNION     → Removes duplicates
UNION ALL → Keeps duplicates
```

---

# 36. `EXISTS`

Checks whether at least one matching record exists.

## General Syntax

```sql
SELECT *
FROM TableA a
WHERE EXISTS (
    SELECT 1
    FROM TableB b
    WHERE b.key = a.key
);
```

### Example

```sql
SELECT *
FROM Customer c
WHERE EXISTS (
    SELECT 1
    FROM Orders o
    WHERE o.customer_id = c.customer_id
);
```

### Memory

> Does at least one matching row exist?

---

# 37. `NOT EXISTS`

Used to find records without corresponding matches.

```sql
SELECT *
FROM TableA a
WHERE NOT EXISTS (
    SELECT 1
    FROM TableB b
    WHERE b.key = a.key
);
```

### Example

```sql
SELECT *
FROM Customer c
WHERE NOT EXISTS (
    SELECT 1
    FROM Orders o
    WHERE o.customer_id = c.customer_id
);
```

---

# 38. Common Table Expression — `CTE`

Used to create a temporary named result.

## General Syntax

```sql
WITH cte_name AS (
    SELECT ...
    FROM ...
)

SELECT *
FROM cte_name;
```

### Example

```sql
WITH HighSalaryEmployees AS (
    SELECT *
    FROM Employee
    WHERE salary > 50000
)

SELECT *
FROM HighSalaryEmployees;
```

### Memory

> Create temporary result → Give it a name → Use it.

---

# 39. `INSERT`

## General Syntax

```sql
INSERT INTO table_name (
    column1,
    column2
)
VALUES (
    value1,
    value2
);
```

### Example

```sql
INSERT INTO Employee (
    name,
    salary
)
VALUES (
    'Ravi',
    50000
);
```

---

# 40. `UPDATE`

## General Syntax

```sql
UPDATE table_name
SET column_name = new_value
WHERE condition;
```

### Example

```sql
UPDATE Employee
SET salary = 60000
WHERE emp_id = 1;
```

Be careful:

```sql
UPDATE Employee
SET salary = 60000;
```

updates **every row**.

---

# 41. `DELETE`

## General Syntax

```sql
DELETE FROM table_name
WHERE condition;
```

### Example

```sql
DELETE FROM Employee
WHERE emp_id = 10;
```

Without `WHERE`:

```sql
DELETE FROM Employee;
```

all rows are deleted.

---

# Master SQL Query Skeleton

This is the most important syntax to remember:

```sql
SELECT columns / aggregate_functions

FROM table_name

JOIN another_table
    ON join_condition

WHERE row_condition

GROUP BY grouping_columns

HAVING aggregate_condition

ORDER BY sorting_column ASC/DESC

LIMIT N
OFFSET M;
```

You do **not** need every clause every time.

Remove whatever is not required.

---

# Complete Example

```sql
SELECT d.department_name,
       AVG(e.salary) AS avg_salary

FROM Employee e

INNER JOIN Department d
ON e.department_id = d.department_id

WHERE e.status = 'ACTIVE'

GROUP BY d.department_name

HAVING AVG(e.salary) > 50000

ORDER BY avg_salary DESC

LIMIT 5
OFFSET 10;
```

Meaning:

```text
Join Employee and Department
        ↓
Consider only ACTIVE employees
        ↓
Group by department
        ↓
Calculate average salary
        ↓
Keep groups with AVG salary > 50000
        ↓
Sort highest average salary first
        ↓
Skip first 10 results
        ↓
Take next 5 results
```

---

# How to Convert Interview Questions Into SQL

| Interview Wording            | Think                            |
| ---------------------------- | -------------------------------- |
| Find / Show / Get            | `SELECT`                         |
| From employees/users/orders  | `FROM`                           |
| Where salary > X             | `WHERE`                          |
| For each department          | `GROUP BY`                       |
| Number of employees          | `COUNT()`                        |
| Average salary               | `AVG()`                          |
| Total sales                  | `SUM()`                          |
| Highest                      | `MAX()`                          |
| Lowest                       | `MIN()`                          |
| Groups having some condition | `HAVING`                         |
| Highest to lowest            | `ORDER BY DESC`                  |
| Lowest to highest            | `ORDER BY ASC`                   |
| Top 5                        | `LIMIT 5`                        |
| Skip first 10                | `OFFSET 10`                      |
| Next 10 records              | `LIMIT 10 OFFSET X`              |
| Pagination                   | `LIMIT + OFFSET`                 |
| Data from two tables         | `JOIN`                           |
| Only matching records        | `INNER JOIN`                     |
| Keep all left-side records   | `LEFT JOIN`                      |
| Records having no match      | `LEFT JOIN + IS NULL`            |
| More than average            | Subquery                         |
| Duplicate values             | `GROUP BY + HAVING COUNT(*) > 1` |
| Nth highest                  | `DENSE_RANK()`                   |
| Top N per department         | `PARTITION BY + DENSE_RANK()`    |
| If / Else                    | `CASE WHEN`                      |
| Matching record exists       | `EXISTS`                         |
| No matching record exists    | `NOT EXISTS`                     |

---

# Must-Know SQL Interview Patterns

```text
1. SELECT + WHERE

2. GROUP BY + Aggregate Function

3. GROUP BY + HAVING

4. JOIN + ON

5. LEFT JOIN + IS NULL

6. Subquery

7. GROUP BY + HAVING COUNT(*) > 1

8. DENSE_RANK() + PARTITION BY

9. LIMIT + OFFSET
```

---

# Final Memory Map

```text
Need rows?
→ WHERE

Need groups?
→ GROUP BY

Need to filter groups?
→ HAVING

Need sorting?
→ ORDER BY

Need only N rows?
→ LIMIT

Need to skip rows?
→ OFFSET

Need pagination?
→ LIMIT + OFFSET

Need another table?
→ JOIN

Need unmatched rows?
→ LEFT JOIN + IS NULL

Need calculation?
→ COUNT / SUM / AVG / MIN / MAX

Need duplicates?
→ GROUP BY + HAVING COUNT(*) > 1

Need ranking?
→ ROW_NUMBER / RANK / DENSE_RANK

Need ranking inside each group?
→ PARTITION BY

Need Nth highest?
→ DENSE_RANK

Need reusable complex query?
→ CTE

Need conditional output?
→ CASE WHEN
```

---

# One-Line Interview Cheat Code

```sql
SELECT what_you_need
FROM where_it_exists
JOIN another_table
    ON how_tables_are_related
WHERE which_rows_you_need
GROUP BY how_you_group_them
HAVING which_groups_you_need
ORDER BY how_you_sort_them
LIMIT how_many_you_need
OFFSET how_many_you_skip;
```

## Final Memory Sentence

```text
SELECT → What?
FROM → Where?
JOIN → With which table?
ON → How are they related?
WHERE → Which rows?
GROUP BY → Group by what?
HAVING → Which groups?
ORDER BY → In what order?
LIMIT → Take how many?
OFFSET → Skip how many?
```

> Do not memorize SQL queries blindly.
> Learn to translate the wording of the interview question into SQL clauses.
