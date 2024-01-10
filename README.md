# dp-queries-interview-preparation

1. <b> SQL Query to index Nth highest salary from the table </b>

```
   SELECT * FROM Employee WHERE sal = 
         (
            SELECT MIN(sal) FROM Employee WHERE  sal IN (SELECT DISTINCT TOP N sal FROM Employee ORDER BY sal DESC)
         );
```
   query to get 2nd highest salary
```
   SELECT * FROM employees WHERE employee_id IN 
         (
            SELECT employee_id FROM employees  WHERE salary =
                  (
                     SELECT MAX(salary) FROM employees WHERE salary < (SELECT MAX(salary) FROM employees)
                  )
         );

```
2. <b> Swapping of two integer column values </b>
```
UPDATE SwappingTwoColumnsValueDemo
   SET FirstColumnValue = FirstColumnValue+SecondColumnValue,
       SecondColumnValue = FirstColumnValue-SecondColumnValue,
       FirstColumnValue = FirstColumnValue-SecondColumnValue;
```
3. <b>Syntax for quering from two tables and with foriegn key </b>
```
SELECT  users.email, users.password, data.data_1, data.data_2
FROM users
INNER JOIN data 
ON users.user_id=data.user_id
WHERE users.email='$user_email'

and get all rows without a WHERE condition:
SELECT users.email, users.password, data.data_1, data.data_2
FROM users
INNER JOIN data ON users.user_id=data.user_id
```

4. <b>Self Join</b>

```
SELECT column_name(s)
FROM table1 a, table1 b
WHERE a.common_field = b.common_field;
```
5. <b>SQL Inner Join</b>

```
Table 1 : Orders
Table 2 : Customers

SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
FROM Orders
INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID;
```

6. <b>Left Join</b>
```
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```

7. <b>Left Join</b>
```
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```
8. <b>Outer Join</b>
```
SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2
ON table1.column_name = table2.column_name
WHERE condition;
```
9. <b>Union Join</b>
```
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```
