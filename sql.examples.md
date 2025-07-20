

🔹 1. SELECT – Retrieve data from a table

SELECT name, age FROM employees;

Gets name and age columns from the employees table.

⸻

🔹 2. INSERT – Add new data into a table

INSERT INTO employees (name, age, department)
VALUES ('Alice', 30, 'HR');

Inserts a new employee record.

⸻

🔹 3. UPDATE – Modify existing data

UPDATE employees
SET age = 31
WHERE name = 'Alice';

Updates Alice’s age to 31.

⸻

🔹 4. DELETE – Remove data

DELETE FROM employees
WHERE name = 'Alice';

Deletes the record where name is Alice.

⸻

🔹 5. CREATE – Create new tables or databases

CREATE TABLE employees (
  id INT PRIMARY KEY,
  name VARCHAR(100),
  age INT,
  department VARCHAR(50)
);

Creates a new employees table.

⸻

🔹 6. DROP – Delete tables or databases

DROP TABLE employees;

Deletes the employees table entirely.

⸻

🔹 7. ALTER – Modify table structure

ALTER TABLE employees
ADD COLUMN salary DECIMAL(10, 2);

Adds a new salary column to the table.

⸻

🔹 8. JOIN – Combine data from multiple tables

SELECT e.name, d.name AS department_name
FROM employees e
JOIN departments d ON e.department_id = d.id;

Combines data from employees and departments.

⸻

🔹 9. GROUP BY – Group rows that have the same values

SELECT department, COUNT(*) AS total
FROM employees
GROUP BY department;

Counts how many employees are in each department.

⸻

🔹 10. ORDER BY – Sort result set

SELECT name, age FROM employees
ORDER BY age DESC;

Lists employees by age, from oldest to youngest.


---------------


🧩 Sample Tables

employees

emp_id	name	dept_id
1	Alice	10
2	Bob	20
3	Carol	NULL

departments

dept_id	dept_name
10	HR
20	Engineering
30	Marketing


⸻

🔗 1. INNER JOIN

Returns only matching rows between both tables.

SELECT e.name, d.dept_name
FROM employees e
INNER JOIN departments d ON e.dept_id = d.dept_id;

✅ Result:

name	dept_name
Alice	HR
Bob	Engineering


⸻

🔗 2. LEFT JOIN (LEFT OUTER JOIN)

Returns all rows from the left table, and matched rows from the right. Null if no match.

SELECT e.name, d.dept_name
FROM employees e
LEFT JOIN departments d ON e.dept_id = d.dept_id;

✅ Result:

name	dept_name
Alice	HR
Bob	Engineering
Carol	NULL


⸻

🔗 3. RIGHT JOIN (RIGHT OUTER JOIN)

Returns all rows from the right table, and matched rows from the left.

SELECT e.name, d.dept_name
FROM employees e
RIGHT JOIN departments d ON e.dept_id = d.dept_id;

✅ Result:

name	dept_name
Alice	HR
Bob	Engineering
NULL	Marketing


⸻

🔗 4. FULL OUTER JOIN

Returns all rows from both tables. Nulls if no match.

Not supported in all DBs directly (e.g., MySQL), but can be simulated.

SELECT e.name, d.dept_name
FROM employees e
FULL OUTER JOIN departments d ON e.dept_id = d.dept_id;

✅ Result:

name	dept_name
Alice	HR
Bob	Engineering
Carol	NULL
NULL	Marketing


⸻

🔗 5. CROSS JOIN

Returns the Cartesian product of both tables (all combinations).

SELECT e.name, d.dept_name
FROM employees e
CROSS JOIN departments d;

✅ Result (3 employees × 3 departments = 9 rows):

name	dept_name
Alice	HR
Alice	Engineering
Alice	Marketing
Bob	HR
Bob	Engineering
Bob	Marketing
Carol	HR
Carol	Engineering
Carol	Marketing






