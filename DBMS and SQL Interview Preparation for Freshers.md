# DBMS and SQL Interview Preparation for Freshers

## 1. Database and DBMS Fundamentals — High Priority

1. What is a database, and what is a Database Management System (DBMS)?
2. What problems does a DBMS solve compared with storing data in files?
3. How does a relational DBMS differ from a general DBMS?
4. What are tables, rows, columns, and domains in a relational database?
5. What is the difference between a database schema and a database instance?
6. What are data redundancy and data inconsistency?
7. What is data independence, and how do logical and physical data independence differ?
8. What are the external, conceptual, and internal levels of database architecture?
9. What is metadata, and what information does a database catalog store?
10. How does SQL differ from MySQL, PostgreSQL, and SQL Server?

## 2. Keys, Constraints, and Relationships — High Priority

1. What is a super key, and how does it differ from a candidate key?
2. What are primary, alternate, and composite keys?
3. How does a primary key differ from a unique constraint?
4. What is a foreign key, and how does it enforce referential integrity?
5. Can a foreign key contain duplicate values or `NULL`?
6. Can a table have multiple candidate keys or multiple primary keys?
7. How do natural keys differ from surrogate keys?
8. What are `NOT NULL`, `UNIQUE`, `CHECK`, and `DEFAULT` constraints?
9. How do one-to-one, one-to-many, and many-to-many relationships differ?
10. How would you represent a many-to-many relationship between students and courses?
11. What can happen when you delete a parent row that is referenced by child rows?
12. How do `ON DELETE CASCADE`, `ON DELETE SET NULL`, and `ON DELETE RESTRICT` differ?

## 3. SQL Basics and Data Modification — High Priority

1. What are DDL, DML, DCL, and TCL? Which statements are commonly associated with each?
2. How do `CREATE`, `ALTER`, and `DROP` differ?
3. How do `DELETE`, `TRUNCATE`, and `DROP` differ?
4. Which aspects of `TRUNCATE`, such as rollback and identity-counter behavior, depend on the database system?
5. How do you insert one row or multiple rows into a table?
6. How do you update only the rows that match a condition?
7. What happens if an `UPDATE` or `DELETE` statement has no `WHERE` clause?
8. What is the purpose of `DISTINCT`?
9. How do column aliases and table aliases improve a query?
10. How do `CHAR` and `VARCHAR` differ?
11. Why is `DECIMAL` generally more suitable than floating-point types for exact monetary values?
12. How would you add a constraint to a table that already contains data?

## 4. Filtering, Sorting, and NULL Handling — High Priority

1. How does the `WHERE` clause filter rows?
2. How do `AND`, `OR`, and `NOT` interact, and when should you use parentheses?
3. How do `IN`, `BETWEEN`, and `LIKE` work?
4. What do `%` and `_` mean in a `LIKE` pattern?
5. What does `NULL` represent, and how does it differ from zero or an empty string?
6. Why should you use `IS NULL` instead of `= NULL`?
7. How does SQL’s three-valued logic affect filtering conditions involving `NULL`?
8. What is `COALESCE`, and when would you use it?
9. How do you sort results by multiple columns using `ORDER BY`?
10. How would you retrieve the top five highest-paid employees and make the result deterministic when salaries tie?
11. Why is selecting a limited number of rows without `ORDER BY` unreliable when a specific order matters?
12. How would you filter all timestamps within a particular calendar month?

## 5. Aggregate Functions and Grouping — High Priority

1. What do `COUNT`, `SUM`, `AVG`, `MIN`, and `MAX` do?
2. How do `COUNT(*)`, `COUNT(column)`, and `COUNT(DISTINCT column)` differ?
3. How do aggregate functions handle `NULL` values?
4. What is the purpose of `GROUP BY`?
5. How does `WHERE` differ from `HAVING`?
6. Can a query use both `WHERE` and `HAVING`? What does each filter?
7. Why must selected non-aggregated columns generally appear in `GROUP BY`?
8. How would you find departments with more than five employees?
9. How would you calculate total sales for each customer?
10. How would you find duplicate email addresses in a users table?
11. How would you perform conditional aggregation using `CASE`?
12. What is the logical processing order of `FROM`, `WHERE`, `GROUP BY`, `HAVING`, `SELECT`, `DISTINCT`, and `ORDER BY`?

## 6. Joins and Set Operations — High Priority

1. What is a join, and why is it needed?
2. How do `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, and `FULL OUTER JOIN` differ?
3. What is a `CROSS JOIN`, and how many rows can it produce?
4. What is a self-join, and when would you use one?
5. How would you display employees alongside their managers using a self-join?
6. How would you find customers who have never placed an order?
7. What is the difference between placing a condition in `ON` and placing it in `WHERE` for a `LEFT JOIN`?
8. Why can joining two tables produce more rows than either input?
9. How can you avoid double-counting values when aggregating across one-to-many joins?
10. How does `UNION` differ from `UNION ALL`?
11. What requirements must queries satisfy to be combined using a set operator?
12. How do `INTERSECT` and `EXCEPT` differ from joins?

## 7. Subqueries and Common Table Expressions — High Priority

1. What is a subquery, and where can it appear in a SQL statement?
2. What is the difference between a scalar subquery and a subquery that returns multiple rows?
3. How does a correlated subquery differ from a non-correlated subquery?
4. How do `IN` and `EXISTS` differ?
5. Why can `NOT IN` produce unexpected results when its subquery returns `NULL`?
6. How would you find employees who earn more than the company’s average salary?
7. How would you find employees who earn more than their own department’s average salary?
8. How would you find products that have never been ordered using `NOT EXISTS`?
9. What is a Common Table Expression (CTE), and how is it written using `WITH`?
10. How does a CTE differ from a subquery or a temporary table?
11. When might you choose a join over a subquery, and why should you avoid assuming one is always faster?

## 8. Practical SQL Query Problems — High Priority

1. How would you find the second-highest distinct salary without using a window function?
2. How would you retrieve all employees who share the highest salary?
3. How would you find the highest-paid employees in each department, including ties?
4. How would you identify duplicate records based on a combination of columns?
5. How would you delete duplicate records while keeping the row with the smallest ID?
6. How would you find departments that have no employees?
7. How would you find customers who placed at least three orders in the last 30 days?
8. How would you calculate monthly revenue from completed orders?
9. How would you retrieve the latest order for each customer when multiple orders can share the same timestamp?
10. How would you find employees who earn more than their managers?
11. How would you count employees in every department, including departments with zero employees?
12. How would you increase salaries by 10% for employees in a selected department?
13. How would you find students who are enrolled in both of two specified courses?
14. How would you find customers who have purchased every product in a specified category?

## 9. Functional Dependencies and Normalization — High Priority

1. What is a functional dependency?
2. What are full, partial, and transitive dependencies?
3. What are insertion, update, and deletion anomalies?
4. What is normalization, and why is it useful?
5. What are the requirements of First Normal Form (1NF)?
6. How does Second Normal Form (2NF) differ from 1NF?
7. How does Third Normal Form (3NF) differ from 2NF?
8. What is Boyce–Codd Normal Form (BCNF), and how does it differ from 3NF?
9. Given a small relation and its functional dependencies, how would you identify candidate keys?
10. How would you normalize a table containing students, courses, and instructor details?
11. What are lossless decomposition and dependency preservation?
12. What is denormalization, and what trade-offs does it introduce?

## 10. Transactions and ACID Properties — High Priority

1. What is a database transaction?
2. What are atomicity, consistency, isolation, and durability?
3. How do `COMMIT`, `ROLLBACK`, and `SAVEPOINT` differ?
4. What is autocommit, and how does it affect transaction boundaries?
5. How would you organize a money transfer between two accounts as a transaction?
6. What should happen if one statement in a multi-step transaction fails?
7. Why does database consistency still depend on correctly defined constraints and application logic?
8. What can go wrong if two users try to book the same seat at the same time?
9. Why is checking availability and then inserting a booking without transaction protection unsafe?
10. Why can long-running transactions cause problems?

## 11. Concurrency Control and Isolation — High Priority

1. Why does a DBMS need concurrency control?
2. What are dirty reads, non-repeatable reads, and phantom reads?
3. What is a lost update?
4. What are the standard transaction isolation levels?
5. How does stronger isolation affect concurrency and performance?
6. What is serializability, and how does a serializable schedule differ from a serial schedule?
7. What are shared and exclusive locks?
8. How does optimistic concurrency control differ from pessimistic concurrency control?
9. What is a database deadlock, and how can it occur?
10. How can an application reduce deadlocks and respond when a transaction is chosen as a deadlock victim?
11. What is Multi-Version Concurrency Control (MVCC), at a basic level?
12. How could you safely update a product’s stock count when several users purchase it simultaneously?

## 12. Indexing and Query Performance — High Priority

1. What is an index, and how can it speed up a query?
2. Why can indexes slow down `INSERT`, `UPDATE`, and `DELETE` operations?
3. What is the basic difference between B-tree and hash indexes?
4. How do clustered and non-clustered indexes differ in database systems that support that distinction?
5. What is a composite index, and why does column order matter?
6. How might an index on `(department_id, salary)` support different filtering conditions?
7. What is index selectivity, and why does it matter?
8. What is a covering index?
9. Why might a query optimizer choose a table scan even when an index exists?
10. How can applying a function to an indexed column affect index usage?
11. How can leading-wildcard searches such as `LIKE '%text'` affect conventional B-tree index usage?
12. What is an execution plan, and what would you inspect using `EXPLAIN`?
13. Why can `SELECT *` be inefficient?
14. How would you investigate a query that becomes slow as a table grows?

## 13. Window Functions — Medium Priority

1. What is a window function, and how does it differ from an aggregate used with `GROUP BY`?
2. What are the roles of `OVER`, `PARTITION BY`, and `ORDER BY` in a window function?
3. How do `ROW_NUMBER`, `RANK`, and `DENSE_RANK` differ?
4. How would you retrieve the top three distinct salaries in each department, including ties?
5. How would you select exactly three employees per department using a deterministic ordering?
6. How would you calculate a running total of sales?
7. How would you use `LAG` to compare each month’s revenue with the previous month’s revenue?
8. How do `LAG` and `LEAD` differ?
9. What is a window frame, and how can it affect a running calculation?
10. Why do you commonly need a CTE or subquery to filter rows by a window-function result?

## 14. Views, Procedures, Functions, and Triggers — Medium Priority

1. What is a view, and why would you create one?
2. How does a regular view differ from a materialized view?
3. Does a regular view normally store its query results?
4. Can you insert or update data through a view? What can restrict this?
5. What is a stored procedure?
6. How does a stored procedure differ from a database function in the DBMS you use?
7. What is a trigger, and when does it execute?
8. How does a trigger differ from a stored procedure?
9. What problems can arise when important business logic is hidden inside triggers?
10. When would you use a view to simplify access to data or restrict the columns users can see?

## 15. Database Design and Application Integration — Medium Priority

1. What is an Entity–Relationship diagram, and what are entities, attributes, and relationships?
2. How would you design tables for a student–course enrollment system?
3. How would you design a doctor appointment system so that the database helps prevent duplicate bookings for the same slot?
4. How would you decide which constraints belong in the database rather than only in application code?
5. What is SQL injection, and how do parameterized queries help prevent it?
6. How does a prepared statement differ from building SQL through string concatenation?
7. What is connection pooling, and why is opening a new connection for every request expensive?
8. What problems can occur if an application does not close database resources properly?
9. What is the N+1 query problem?
10. How does offset-based pagination differ from keyset pagination?

## 16. Recovery and Distributed Database Basics — Low Priority, Optional Advanced

1. What is write-ahead logging, and how does it support recovery?
2. What is a checkpoint, and how can it reduce crash-recovery work?
3. How does a backup differ from replication?
4. How does replication differ from sharding?
5. How does horizontal partitioning differ from vertical partitioning?
6. How do relational databases differ from document and key-value databases?
7. What does the CAP theorem describe during a network partition?
8. What is eventual consistency?
9. What is two-phase locking, and how does it differ from two-phase commit?
10. What are recursive CTEs, and where might they be useful?

## Must-Prepare Checklist

- [ ] Database vs DBMS vs RDBMS.
- [ ] Schemas, instances, and data independence.
- [ ] Primary, candidate, super, composite, and foreign keys.
- [ ] Constraints and referential integrity.
- [ ] One-to-one, one-to-many, and many-to-many relationships.
- [ ] DDL, DML, DCL, and TCL statements.
- [ ] `DELETE` vs `TRUNCATE` vs `DROP`.
- [ ] `SELECT`, `INSERT`, `UPDATE`, and `DELETE`.
- [ ] Filtering with `WHERE`, `IN`, `BETWEEN`, and `LIKE`.
- [ ] `NULL`, `IS NULL`, and `COALESCE`.
- [ ] Sorting and deterministic top-N queries.
- [ ] Aggregate functions and their treatment of `NULL`.
- [ ] `GROUP BY` vs `HAVING`.
- [ ] Logical SQL query-processing order.
- [ ] Inner, outer, cross, and self-joins.
- [ ] Join multiplicity and accidental double-counting.
- [ ] `UNION` vs `UNION ALL`.
- [ ] Subqueries and correlated subqueries.
- [ ] `IN`, `EXISTS`, and the `NOT IN`–`NULL` pitfall.
- [ ] Common Table Expressions.
- [ ] Second-highest salary and highest salary per department.
- [ ] Duplicate detection and safe duplicate deletion.
- [ ] Queries for missing relationships and zero counts.
- [ ] Functional dependencies and normalization through BCNF.
- [ ] Transactions and ACID properties.
- [ ] `COMMIT`, `ROLLBACK`, and `SAVEPOINT`.
- [ ] Isolation levels and concurrency anomalies.
- [ ] Locks, deadlocks, and basic MVCC.
- [ ] Indexes, composite indexes, and indexing trade-offs.
- [ ] Basic execution-plan analysis.
- [ ] `ROW_NUMBER`, `RANK`, and `DENSE_RANK`.
- [ ] Running totals and `LAG`.
- [ ] Views, procedures, functions, and triggers.
- [ ] Basic relational schema design.
- [ ] Parameterized queries and SQL injection prevention.
- [ ] Connection pooling and the N+1 query problem.
