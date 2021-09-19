# Lesson 11

*Understanding Subqueries*

Subqueries is query nest in query.

*Filtering by Subquery*

```
SELECT cust_name, cust_contact
FROM customers
WHERE cust_id IN (
    SELECT cust_id
    FROM orders
    WHERE order_num IN (
        SELECT order_num
        FROM orderitems
        WHERE prod_id = 'RGAN01'));
```

The reason we need subquery is that the data we have and data we need is spread across different table.

For the above subquery each query become the filter condition for outer query.

Subquery `SELECT` statements can only retrieve a single column.

Subquery is not the only option we can use join as well.

*Using Subqueries as Calculated Fields*

```
SELECT cust_name, cust_state, (SELECT COUNT(*) FROM orders WHERE orders.cust_id = customers.cust_id) AS orders
FROM customers
ORDER BY cust_name;
```

In above query the subquery is executed once for every customer retrieved. The `WHERE` condition must be in the fully
qualified column name `table_name.column_name` to avoid ambiguity .
