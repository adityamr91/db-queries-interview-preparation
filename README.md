# dp-queries-interview-preparation

1. <b> SQL Query to index Nth highest salary from the table </b>

```
   SELECT * FROM Employee WHERE sal = 
         (
            SELECT MIN(sal) FROM Employee WHERE  sal IN (SELECT DISTINCT TOP N sal FROM Employee ORDER BY sal DESC)
         )
```
Swapping of two integer column values 
```
UPDATE SwappingTwoColumnsValueDemo
   SET FirstColumnValue = FirstColumnValue+SecondColumnValue,
       SecondColumnValue = FirstColumnValue-SecondColumnValue,
       FirstColumnValue = FirstColumnValue-SecondColumnValue;
```

2. <b>Self Join</b>

```
SELECT column_name(s)
FROM table1 a, table1 b
WHERE a.common_field = b.common_field;
```
3. <b>SQL Inner Join</b>

```
Table 1 : Orders
Table 2 : Customers

SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
FROM Orders
INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID;
```

4. <b>Left Join</b>
```
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```

5. <b>Left Join</b>
```
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```
6. <b>Outer Join</b>
```
SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2
ON table1.column_name = table2.column_name
WHERE condition;
```
7. <b>Union Join</b>
```
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```
