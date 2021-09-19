# Lesson 13

*Using Table Aliases*

```
SELECT cust_name, cust_contact
FROM customers AS C,
     orders AS O,
     orderitems AS OI
WHERE C.cust_id = O.cust_id
  AND OI.order_num = O.order_num
  AND prod_id = 'RGAN01'
```

Two primary reasons to use alias table names:

1. To shorten the SQL syntax.
2. To enable multiple uses of the same table within a single `SELECT` statement.

*Using Different Join Types*

1. Self join.
2. Natural join.
3. Outer join.

*Self join*

```
SELECt c1.cust_id, c1.cust_name, c1.cust_contact
FROM customers AS c1,
     customers AS c2
WHERE c1.cust_name = c2.cust_name
  AND c2.cust_contact = 'Jim Jones';
```

*Natural Joins*

```SELECT C.*, O.order_num, O.order_date, OI.prod_id, OI.quantity, OI.item_price
FROM customers AS C,
     orders AS O,
     orderitems AS OI
WHERE C.cust_id = O.cust_id
  AND OI.order_num = O.order_num
  AND prod_id = 'RGAN01';
```

In natural join each column is unique.

*Outer Joins*

Inner join: retrieves a list of all customers and their order:

```
SELECT customers.cust_id, orders.order_num
FROM customers
         INNER JOIN orders on customers.cust_id = orders.cust_id;
```

Outer join: retrieves a list of all customers including those who have placed no orders.

```
SELECT customers.cust_id, orders.order_num
FROM customers
         LEFT OUTER JOIN orders on customers.cust_id = orders.cust_id
```

Outer joins also include rows with no related rows.

- `RIGTH` include all rows of right table.
- `LEFT` include all rows of left table.

Full outer join that retrieves all rows from both tables and relates those that can be related.

*Using Joins with Aggregate Functions*

Inner join.

```
SELECT customers.cust_id, COUNT(orders.order_num) AS num_ord
FROM customers
         INNER JOIN orders ON customers.cust_id = orders.cust_id
GROUP BY customers.cust_id;
```

Outer join.

```
SELECT customers.cust_id, COUNT(orders.order_num) AS num_ord
FROM customers
         LEFT OUTER JOIN orders ON customers.cust_id = orders.cust_id
GROUP BY customers.cust_id;
```
