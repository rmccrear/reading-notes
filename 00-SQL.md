# SQL Reference

## SELECT ORDER BY

Use `ASC` or `DESC` to set the order. Use `LIMIT` and `OFFSET`

`SELECT titles, year FROM movies ORDER BY year LIMIT 10 OFFSET 10`

## INNER JOIN vs LEFT join

reference: [https://sqlbolt.com/lesson/select_queries_with_outer_joins](https://sqlbolt.com/lesson/select_queries_with_outer_joins)

INNER JOIN will return values where both tables have rows found.

LEFT JOIN (LEFT OUTER JOIN) will return values that may contain NULL for the right table.

So, the following will be equivalent even if there are some buildings with no employees:

`SELECT DISTINCT b.name from buildings b INNER JOIN employees e ON b.name= e.building;`

`SELECT DISTINCT b.name from buildings b LEFT JOIN employees e ON b.name= e.building WHERE e.building IS NOT NULL;`

And the following queries will be equivalent, even if there are some buildings with no employees:

`SELECT DISTINCT b.name from buildings b LEFT JOIN employees e ON b.name=e.building 

`SELECT name from buildings;`

## Argregating and GROUP BY

reference: [https://sqlbolt.com/lesson/select_queries_with_aggregates](https://sqlbolt.com/lesson/select_queries_with_aggregates)

COUNT, MIN, MAX, SUM, AVG are aggregate functions. 

`SELECT AVG(years) FROM employees WHERE years>1;`

Use GROUP BY with agregate functions to return an agregate for each distinct value for a column.

`SELECT AVG(years) FROM employees GROUP BY role;`


## Basic syntax

INSERT INTO table (col1, col2) VALUES (val1, val2)

INSERT multiple:

`INSERT INTO employees (role, name, building) VALUES ("Artist", "John B.", NULL), ("Artist", "Jim J.", "2w");`

`UPDATE employees SET role="Engineer", building="e1" WHERE name="John B.";

`DELETE FROM employees WHERE building IS NULL;`

## Database management

CREATE TABLE IF NOT EXISTS tasks (name TEXT DEFAULT "New Task", importance int );

reference for PRIMARY/FOREIGN KEY [https://www.w3schools.com/sql/sql_foreignkey.asp](https://www.w3schools.com/sql/sql_foreignkey.asp)

ALTER tasks ADD time_estimate int DEFAULT 10;

DROP TABLE IF EXISTS tasks;


[screenshots](https://drive.google.com/file/d/1P6Q8JUJvLGCHvISFsgIWXROzeabTk2Z5/view?usp=sharing)


