# Frequently Asked SQL Interview Questions for Freshers

These notes are designed for:

* Freshers
* 0–2 years experience
* Software Engineer interviews
* Java Backend interviews
* Product-based company interviews

The goal is to give **short, interview-ready answers** instead of textbook explanations.

---

# 1. What is SQL?

### On-Point Answer

SQL stands for **Structured Query Language**.

It is used to communicate with relational databases for operations such as:

* Creating data
* Reading data
* Updating data
* Deleting data

These are commonly called **CRUD operations**.

```text
C → Create
R → Read
U → Update
D → Delete
```

Example:

```sql
SELECT *
FROM Employee;
```

---

# 2. What is the difference between SQL and MySQL?

### On-Point Answer

**SQL** is a language used to interact with relational databases.

**MySQL** is a relational database management system that understands SQL.

```text
SQL
→ Language

MySQL
→ Database Management System
```

Similar DBMS examples:

* PostgreSQL
* Oracle
* SQL Server
* MySQL

---

# 3. What is the difference between Database and DBMS?

### On-Point Answer

A **database** is an organized collection of data.

A **DBMS** is software used to create, store, retrieve, update, and manage that database.

Example:

```text
Database
→ Actual stored data

MySQL
→ DBMS managing that data
```

---

# 4. What are DDL, DML, DQL, DCL, and TCL?

## DDL — Data Definition Language

Used to define database structures.

```sql
CREATE
ALTER
DROP
TRUNCATE
```

---

## DML — Data Manipulation Language

Used to modify data.

```sql
INSERT
UPDATE
DELETE
```

---

## DQL — Data Query Language

Used to retrieve data.

```sql
SELECT
```

---

## DCL — Data Control Language

Used to control permissions.

```sql
GRANT
REVOKE
```

---

## TCL — Transaction Control Language

Used to manage transactions.

```sql
COMMIT
ROLLBACK
SAVEPOINT
```

---

# 5. What is a Primary Key?

### On-Point Answer

A primary key is a column or combination of columns that **uniquely identifies each row in a table**.

Properties:

* Unique
* Cannot be `NULL`

Example:

```text
Employee

emp_id → Primary Key
```

---

# 6. What is a Foreign Key?

### On-Point Answer

A foreign key is a column that references the primary key or unique key of another table.

It is used to establish relationships between tables and maintain referential integrity.

Example:

```text
Employee.department_id
        ↓
Department.department_id
```

---

# 7. Primary Key vs Unique Key

| Primary Key                          | Unique Key                          |
| ------------------------------------ | ----------------------------------- |
| Uniquely identifies each row         | Ensures uniqueness                  |
| Cannot contain `NULL`                | NULL behavior depends on DBMS       |
| One primary key constraint per table | Multiple unique constraints allowed |
| Can contain multiple columns         | Can also contain multiple columns   |

### On-Point Answer

A primary key uniquely identifies every row and cannot contain `NULL`.

A unique key also enforces uniqueness, but a table can have multiple unique constraints.

---

# 8. What is a Candidate Key?

### On-Point Answer

A candidate key is a **minimal set of columns that can uniquely identify a row**.

One candidate key is selected as the primary key.

Example:

```text
Student

StudentID
Email
```

If both are unique:

```text
StudentID → Candidate Key
Email     → Candidate Key
```

One can be chosen as the primary key.

---

# 9. What is a Composite Key?

### On-Point Answer

A composite key is a key formed using **two or more columns together**.

Example:

```text
Enrollment

StudentID
CourseID
```

Together:

```text
(StudentID, CourseID)
```

can uniquely identify one enrollment.

---

# 10. What is NULL in SQL?

### On-Point Answer

`NULL` represents a **missing, unknown, or unavailable value**.

It is different from:

```text
0
''
FALSE
```

Example:

```sql
SELECT *
FROM Employee
WHERE manager_id IS NULL;
```

Do not use:

```sql
manager_id = NULL
```

Use:

```sql
manager_id IS NULL
```

---

# 11. Difference Between NULL, 0, and Empty String

```text
NULL
→ Unknown / missing value

0
→ Actual numeric value

''
→ Empty string
```

They are not the same.

---

# 12. What are Constraints in SQL?

### On-Point Answer

Constraints are rules applied to table columns to maintain data integrity.

Common constraints:

```text
PRIMARY KEY
FOREIGN KEY
UNIQUE
NOT NULL
CHECK
DEFAULT
```

---

# 13. What is Normalization?

### On-Point Answer

Normalization is the process of organizing database tables to:

* Reduce data redundancy
* Avoid update anomalies
* Improve data consistency

Common normal forms:

```text
1NF
2NF
3NF
BCNF
```

---

# 14. Explain 1NF, 2NF, 3NF, and BCNF

## 1NF

Every column should contain atomic values.

```text
❌ Skills = Java, SQL

✅ Separate atomic values
```

---

## 2NF

Must be in 1NF and have no **partial dependency** on part of a composite key.

---

## 3NF

Must be in 2NF and have no **transitive dependency**.

```text
A → B
B → C
```

should not cause unnecessary dependency:

```text
A → C through B
```

---

## BCNF

For every non-trivial functional dependency:

```text
X → Y
```

`X` must be a superkey.

### Memory

```text
1NF
→ Atomic values

2NF
→ No partial dependency

3NF
→ No transitive dependency

BCNF
→ Every determinant must be a superkey
```

---

# 15. What is Functional Dependency?

### On-Point Answer

A functional dependency means one attribute determines another.

```text
X → Y
```

means:

> If I know X, I can determine Y.

Example:

```text
StudentID → StudentName
```

---

# 16. What is a Transaction?

### On-Point Answer

A transaction is a group of database operations treated as a **single logical unit of work**.

Either all operations succeed or the transaction can be rolled back.

Example:

```text
Transfer ₹1000

Account A → -1000
Account B → +1000
```

Both should succeed together.

---

# 17. Explain ACID Properties

```text
A → Atomicity
C → Consistency
I → Isolation
D → Durability
```

## Atomicity

> All operations succeed or none of them do.

---

## Consistency

> A transaction should take the database from one valid state to another valid state.

---

## Isolation

> Concurrent transactions should not improperly interfere with each other.

---

## Durability

> Once committed, data should remain stored even after failures.

### Memory

```text
Atomicity
→ All or nothing

Consistency
→ Valid state

Isolation
→ Transactions don't interfere incorrectly

Durability
→ Committed means permanent
```

---

# 18. What is an Index?

### On-Point Answer

An index is a data structure maintained by the database to improve data retrieval speed.

It works conceptually like an index in a book.

```text
Without Index
→ Search many rows

With Index
→ Locate required records faster
```

---

# 19. Why Not Create Indexes on Every Column?

### On-Point Answer

Indexes improve read performance but introduce overhead.

They require:

* Extra storage
* Additional maintenance
* Slower inserts
* Slower updates
* Slower deletes

### Memory

```text
Index
→ Faster reads

But
→ More write + storage overhead
```

---

# 20. Clustered vs Non-Clustered Index

### On-Point Answer

A clustered index determines how table data is physically or logically ordered/stored according to the DBMS implementation.

A non-clustered index maintains a separate index structure that points to table rows.

### Memory

```text
Clustered
→ Data ordered with index structure

Non-Clustered
→ Separate index points to data
```

Implementation details differ across database systems.

---

# 21. WHERE vs HAVING

### On-Point Answer

`WHERE` filters individual rows before grouping.

`HAVING` filters groups after `GROUP BY`.

```text
WHERE
→ Rows

HAVING
→ Groups
```

Example:

```sql
SELECT department,
       AVG(salary)
FROM Employee
WHERE salary > 30000
GROUP BY department
HAVING AVG(salary) > 50000;
```

---

# 22. What is GROUP BY?

### On-Point Answer

`GROUP BY` groups rows having the same value so aggregate calculations can be performed on each group.

Example:

```sql
SELECT department,
       AVG(salary)
FROM Employee
GROUP BY department;
```

Memory:

> For each X, calculate Y.

---

# 23. Can GROUP BY Be Used Without Aggregate Functions?

### On-Point Answer

Yes.

`GROUP BY` can be used without aggregate functions, although it is commonly used together with functions like:

```text
COUNT
SUM
AVG
MIN
MAX
```

Example:

```sql
SELECT department
FROM Employee
GROUP BY department;
```

---

# 24. What is ORDER BY?

### On-Point Answer

`ORDER BY` sorts query results.

```sql
ORDER BY salary ASC;
```

or:

```sql
ORDER BY salary DESC;
```

Memory:

```text
ASC
→ Small to Large

DESC
→ Large to Small
```

---

# 25. GROUP BY vs ORDER BY

```text
GROUP BY
→ Groups rows

ORDER BY
→ Sorts rows/results
```

Example:

```sql
SELECT department,
       AVG(salary)
FROM Employee
GROUP BY department
ORDER BY AVG(salary) DESC;
```

---

# 26. What Does DISTINCT Do?

### On-Point Answer

`DISTINCT` removes duplicate values from query results.

Example:

```sql
SELECT DISTINCT department
FROM Employee;
```

---

# 27. What is LIMIT?

### On-Point Answer

`LIMIT` restricts how many rows are returned.

```sql
SELECT *
FROM Employee
LIMIT 5;
```

Meaning:

> Return only 5 rows.

---

# 28. What is OFFSET?

### On-Point Answer

`OFFSET` skips a specified number of rows before returning results.

```sql
SELECT *
FROM Employee
LIMIT 10
OFFSET 20;
```

Meaning:

```text
Skip 20
Take 10
```

---

# 29. How Do LIMIT and OFFSET Work for Pagination?

Formula:

```text
OFFSET = (pageNumber - 1) × pageSize
```

Example:

```text
Page = 3
Page Size = 10

OFFSET = 20
```

Query:

```sql
SELECT *
FROM Employee
ORDER BY emp_id
LIMIT 10
OFFSET 20;
```

---

# 30. What is LIKE?

### On-Point Answer

`LIKE` is used for pattern matching.

```sql
WHERE name LIKE 'A%';
```

means:

> Starts with A.

Common patterns:

```text
'A%'
→ Starts with A

'%A'
→ Ends with A

'%abc%'
→ Contains abc

'_'
→ Exactly one character
```

---

# 31. What is a JOIN?

### On-Point Answer

A JOIN combines related rows from multiple tables using a common relationship.

General syntax:

```sql
SELECT columns
FROM TableA a
JOIN TableB b
ON a.key = b.key;
```

---

# 32. What are the Different Types of JOINs?

Main joins:

```text
INNER JOIN
LEFT JOIN
RIGHT JOIN
FULL OUTER JOIN
CROSS JOIN
SELF JOIN
```

---

# 33. INNER JOIN vs LEFT JOIN

### INNER JOIN

Returns only matching rows.

### LEFT JOIN

Returns:

```text
All left rows
+
matching right rows
```

Unmatched right-side values become `NULL`.

---

# 34. LEFT JOIN vs RIGHT JOIN

### LEFT JOIN

Keeps all rows from the left table.

### RIGHT JOIN

Keeps all rows from the right table.

---

# 35. What is FULL OUTER JOIN?

### On-Point Answer

`FULL OUTER JOIN` returns:

* Matching rows
* Unmatched left rows
* Unmatched right rows

```text
Everything from both sides
```

---

# 36. What is SELF JOIN?

### On-Point Answer

A self join joins a table with itself using different aliases.

Common example:

> Employee and manager.

```sql
SELECT e.name AS employee,
       m.name AS manager
FROM Employee e
LEFT JOIN Employee m
ON e.manager_id = m.emp_id;
```

---

# 37. What is CROSS JOIN?

### On-Point Answer

A CROSS JOIN returns every possible combination of rows from both tables.

If:

```text
Table A → 3 rows
Table B → 4 rows
```

Result:

```text
3 × 4 = 12 rows
```

---

# 38. What Happens If JOIN Condition is Missing?

### On-Point Answer

Without a proper join condition, the query may produce a Cartesian product where every row from one table combines with every row from another.

This can create a very large result set.

---

# 39. Can We JOIN More Than Two Tables?

### On-Point Answer

Yes.

Example:

```sql
SELECT ...
FROM Employee e
JOIN Department d
    ON e.department_id = d.department_id
JOIN Location l
    ON d.location_id = l.location_id;
```

---

# 40. JOIN vs Subquery

### On-Point Answer

A JOIN is commonly used to combine related data from multiple tables.

A subquery is useful when one query depends on the result of another query.

Example:

```sql
SELECT *
FROM Employee
WHERE salary > (
    SELECT AVG(salary)
    FROM Employee
);
```

---

# 41. Find Employees Earning More Than 50,000

```sql
SELECT *
FROM Employee
WHERE salary > 50000;
```

Pattern:

```text
Filter rows
→ WHERE
```

---

# 42. Find Employees Whose Name Starts With A

```sql
SELECT *
FROM Employee
WHERE name LIKE 'A%';
```

---

# 43. Find Unique Departments

```sql
SELECT DISTINCT department
FROM Employee;
```

---

# 44. Find Highest Salary

```sql
SELECT MAX(salary)
FROM Employee;
```

---

# 45. Find Second Highest Salary

### Query

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
Find highest
    ↓
Ignore highest
    ↓
Find maximum remaining salary
```

---

# 46. Find Nth Highest Salary

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

Replace:

```text
N → Required rank
```

Example:

```sql
WHERE rnk = 3;
```

means third highest salary.

---

# 47. Find Average Salary

```sql
SELECT AVG(salary)
FROM Employee;
```

---

# 48. Find Average Salary Department-Wise

```sql
SELECT department_id,
       AVG(salary)
FROM Employee
GROUP BY department_id;
```

Pattern:

```text
"For each department"
→ GROUP BY
```

---

# 49. Find Departments Having More Than 5 Employees

```sql
SELECT department_id,
       COUNT(*)
FROM Employee
GROUP BY department_id
HAVING COUNT(*) > 5;
```

Pattern:

```text
GROUP BY
+
HAVING
```

---

# 50. Find Departments Whose Average Salary is Greater Than 50,000

```sql
SELECT department_id,
       AVG(salary)
FROM Employee
GROUP BY department_id
HAVING AVG(salary) > 50000;
```

Why `HAVING`?

Because:

```text
AVG(salary)
→ Aggregate result
→ Filter group using HAVING
```

---

# 51. Find Employee Name With Department Name

```sql
SELECT e.name,
       d.department_name
FROM Employee e
INNER JOIN Department d
ON e.department_id = d.department_id;
```

Pattern:

```text
Data from two tables
→ JOIN
```

---

# 52. Find Employees Who Don't Belong to Any Department

```sql
SELECT e.*
FROM Employee e
LEFT JOIN Department d
ON e.department_id = d.department_id
WHERE d.department_id IS NULL;
```

Memory:

```text
LEFT JOIN
+
right.id IS NULL
=
Unmatched records
```

---

# 53. Find Employee and Manager Name

```sql
SELECT e.name AS employee,
       m.name AS manager
FROM Employee e
LEFT JOIN Employee m
ON e.manager_id = m.emp_id;
```

Pattern:

```text
Same table joined with itself
→ SELF JOIN
```

---

# 54. Find Duplicate Emails

```sql
SELECT email,
       COUNT(*)
FROM Users
GROUP BY email
HAVING COUNT(*) > 1;
```

Memory:

```text
Duplicates
=
GROUP BY
+
HAVING COUNT(*) > 1
```

---

# 55. How Do You Identify Duplicate Rows?

Using `ROW_NUMBER()`:

```sql
SELECT *
FROM (
    SELECT *,
           ROW_NUMBER() OVER (
               PARTITION BY email
               ORDER BY id
           ) AS rn
    FROM Users
) t
WHERE rn > 1;
```

Memory:

```text
PARTITION BY duplicate_column
+
ROW_NUMBER
```

---

# 56. ROW_NUMBER vs RANK vs DENSE_RANK

Suppose salaries are:

```text
90000
80000
80000
70000
```

## ROW_NUMBER

```text
90000 → 1
80000 → 2
80000 → 3
70000 → 4
```

Every row gets a unique number.

---

## RANK

```text
90000 → 1
80000 → 2
80000 → 2
70000 → 4
```

Tie creates a gap.

---

## DENSE_RANK

```text
90000 → 1
80000 → 2
80000 → 2
70000 → 3
```

Tie but no gap.

### Memory

```text
ROW_NUMBER
→ Unique sequence

RANK
→ Tie + Gap

DENSE_RANK
→ Tie + No Gap
```

---

# 57. Find Top 3 Salaries in Each Department

```sql
SELECT *
FROM (
    SELECT *,
           DENSE_RANK() OVER (
               PARTITION BY department_id
               ORDER BY salary DESC
           ) AS rnk
    FROM Employee
) t
WHERE rnk <= 3;
```

Pattern:

```text
Top N in each group
=
PARTITION BY
+
DENSE_RANK
```

---

# 58. Find Employees Earning More Than Average Salary

```sql
SELECT *
FROM Employee
WHERE salary > (
    SELECT AVG(salary)
    FROM Employee
);
```

Pattern:

```text
Compare row
with calculated value
→ Subquery
```

---

# 59. Find Employees Earning More Than Their Department Average

```sql
SELECT e.*
FROM Employee e
WHERE e.salary > (
    SELECT AVG(e2.salary)
    FROM Employee e2
    WHERE e2.department_id = e.department_id
);
```

This is a **correlated subquery**.

---

# 60. What is a Correlated Subquery?

### On-Point Answer

A correlated subquery depends on a value from the outer query and may execute logically once for each outer row.

Example:

```sql
SELECT e.*
FROM Employee e
WHERE e.salary > (
    SELECT AVG(e2.salary)
    FROM Employee e2
    WHERE e2.department_id = e.department_id
);
```

---

# 61. What is EXISTS?

### On-Point Answer

`EXISTS` checks whether a subquery returns at least one row.

Example:

```sql
SELECT *
FROM Customer c
WHERE EXISTS (
    SELECT 1
    FROM Orders o
    WHERE o.customer_id = c.customer_id
);
```

Meaning:

> Find customers having at least one order.

---

# 62. What is NOT EXISTS?

### On-Point Answer

`NOT EXISTS` checks whether no matching row exists.

```sql
SELECT *
FROM Customer c
WHERE NOT EXISTS (
    SELECT 1
    FROM Orders o
    WHERE o.customer_id = c.customer_id
);
```

Meaning:

> Find customers who never placed an order.

---

# 63. DELETE vs TRUNCATE vs DROP

## DELETE

Removes rows.

```sql
DELETE FROM Employee
WHERE emp_id = 10;
```

---

## TRUNCATE

Removes all rows from a table.

```sql
TRUNCATE TABLE Employee;
```

---

## DROP

Removes the table itself.

```sql
DROP TABLE Employee;
```

### Memory

```text
DELETE
→ Remove rows

TRUNCATE
→ Empty table

DROP
→ Remove table
```

Transactional behavior and identity-reset behavior may vary by DBMS.

---

# 64. UNION vs UNION ALL

## UNION

Combines query results and removes duplicates.

```sql
SELECT name
FROM Employees

UNION

SELECT name
FROM Managers;
```

---

## UNION ALL

Combines query results and keeps duplicates.

```sql
SELECT name
FROM Employees

UNION ALL

SELECT name
FROM Managers;
```

### Memory

```text
UNION
→ Unique

UNION ALL
→ All
```

---

# 65. What is a CTE?

### On-Point Answer

CTE stands for **Common Table Expression**.

It creates a temporary named result that can be used inside the query.

```sql
WITH HighSalary AS (
    SELECT *
    FROM Employee
    WHERE salary > 50000
)

SELECT *
FROM HighSalary;
```

Memory:

```text
Create temporary result
→ Give it a name
→ Query it
```

---

# 66. What is CASE WHEN?

### On-Point Answer

`CASE WHEN` provides conditional logic inside SQL, similar to `if-else`.

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

---

# 67. What are Aggregate Functions?

### On-Point Answer

Aggregate functions perform calculations over multiple rows.

Common functions:

```text
COUNT()
SUM()
AVG()
MIN()
MAX()
```

Example:

```sql
SELECT AVG(salary)
FROM Employee;
```

---

# 68. COUNT(*) vs COUNT(column)

### On-Point Answer

```sql
COUNT(*)
```

counts rows.

```sql
COUNT(column)
```

counts non-NULL values in that column.

Example:

```sql
SELECT COUNT(manager_id)
FROM Employee;
```

Rows where `manager_id` is `NULL` are not counted.

---

# 69. What is COMMIT?

### On-Point Answer

`COMMIT` permanently saves transaction changes.

```sql
COMMIT;
```

---

# 70. What is ROLLBACK?

### On-Point Answer

`ROLLBACK` undoes uncommitted transaction changes.

```sql
ROLLBACK;
```

Memory:

```text
COMMIT
→ Save

ROLLBACK
→ Undo
```

---

# 71. What is SAVEPOINT?

### On-Point Answer

A savepoint creates a checkpoint inside a transaction so you can roll back to that point instead of cancelling the entire transaction.

Example:

```sql
SAVEPOINT sp1;
```

Then:

```sql
ROLLBACK TO sp1;
```

---

# 72. Transaction Example

```sql
START TRANSACTION;

UPDATE Account
SET balance = balance - 1000
WHERE id = 1;

UPDATE Account
SET balance = balance + 1000
WHERE id = 2;

COMMIT;
```

If something fails:

```sql
ROLLBACK;
```

---

# Top 20 Questions to Prioritize

If preparation time is limited, focus on these first:

```text
1. WHERE vs HAVING

2. GROUP BY

3. Aggregate Functions

4. INNER JOIN

5. LEFT JOIN

6. Types of JOINs

7. Primary Key vs Foreign Key

8. Primary Key vs Unique Key

9. Normalization

10. ACID Properties

11. Indexes

12. DELETE vs TRUNCATE vs DROP

13. UNION vs UNION ALL

14. Subqueries

15. Second Highest Salary

16. Nth Highest Salary

17. Find Duplicates

18. ROW_NUMBER vs RANK vs DENSE_RANK

19. Top N Per Department

20. Employees Earning More Than Average Salary
```

---

# Must-Know Query Patterns

## Pattern 1 — Filter Rows

```sql
SELECT *
FROM table_name
WHERE condition;
```

---

## Pattern 2 — Group and Calculate

```sql
SELECT group_column,
       AGGREGATE(column)
FROM table_name
GROUP BY group_column;
```

---

## Pattern 3 — Filter Groups

```sql
SELECT group_column,
       AGGREGATE(column)
FROM table_name
GROUP BY group_column
HAVING aggregate_condition;
```

---

## Pattern 4 — JOIN

```sql
SELECT columns
FROM TableA a
JOIN TableB b
ON a.key = b.key;
```

---

## Pattern 5 — Find Unmatched Rows

```sql
SELECT a.*
FROM TableA a
LEFT JOIN TableB b
ON a.key = b.key
WHERE b.key IS NULL;
```

---

## Pattern 6 — Subquery

```sql
SELECT *
FROM table_name
WHERE column operator (
    SELECT ...
);
```

---

## Pattern 7 — Find Duplicates

```sql
SELECT column,
       COUNT(*)
FROM table_name
GROUP BY column
HAVING COUNT(*) > 1;
```

---

## Pattern 8 — Nth Highest

```sql
SELECT *
FROM (
    SELECT *,
           DENSE_RANK() OVER (
               ORDER BY column DESC
           ) AS rnk
    FROM table_name
) t
WHERE rnk = N;
```

---

## Pattern 9 — Top N Per Group

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

---

# Interview Question → SQL Pattern Mapping

| Interview Wording           | Think                            |
| --------------------------- | -------------------------------- |
| Find / Show / Get           | `SELECT`                         |
| Filter records              | `WHERE`                          |
| For each department         | `GROUP BY`                       |
| Filter grouped results      | `HAVING`                         |
| Count rows                  | `COUNT()`                        |
| Average                     | `AVG()`                          |
| Total                       | `SUM()`                          |
| Highest                     | `MAX()`                          |
| Lowest                      | `MIN()`                          |
| Sort                        | `ORDER BY`                       |
| Top N                       | `LIMIT`                          |
| Skip N                      | `OFFSET`                         |
| Combine tables              | `JOIN`                           |
| No matching record          | `LEFT JOIN + IS NULL`            |
| Compare against aggregate   | Subquery                         |
| Duplicate values            | `GROUP BY + HAVING COUNT(*) > 1` |
| Nth highest                 | `DENSE_RANK()`                   |
| Top N per group             | `PARTITION BY + DENSE_RANK()`    |
| Conditional result          | `CASE WHEN`                      |
| Matching row exists         | `EXISTS`                         |
| Matching row does not exist | `NOT EXISTS`                     |

---

# Final Memory Map

```text
Need rows?
→ WHERE

Need groups?
→ GROUP BY

Need to filter groups?
→ HAVING

Need calculations?
→ COUNT / SUM / AVG / MIN / MAX

Need sorting?
→ ORDER BY

Need only N rows?
→ LIMIT

Need to skip rows?
→ OFFSET

Need multiple tables?
→ JOIN

Need unmatched rows?
→ LEFT JOIN + IS NULL

Need duplicates?
→ GROUP BY + HAVING COUNT(*) > 1

Need result based on another query?
→ Subquery

Need ranking?
→ ROW_NUMBER / RANK / DENSE_RANK

Need ranking within each group?
→ PARTITION BY

Need Nth highest?
→ DENSE_RANK

Need conditional logic?
→ CASE WHEN

Need temporary named result?
→ CTE

Need check for matching rows?
→ EXISTS / NOT EXISTS
```

---

# Final SQL Interview Strategy

For every SQL interview problem, ask yourself:

```text
1. What data do I need?
→ SELECT

2. Which table contains it?
→ FROM

3. Do I need another table?
→ JOIN

4. Which rows should remain?
→ WHERE

5. Do I need groups?
→ GROUP BY

6. Do I need to filter those groups?
→ HAVING

7. Do I need sorting?
→ ORDER BY

8. Do I need only a few rows?
→ LIMIT

9. Do I need to skip rows?
→ OFFSET
```

> Do not memorize complete SQL answers blindly.
> Learn to identify the pattern from the wording of the interview question.
