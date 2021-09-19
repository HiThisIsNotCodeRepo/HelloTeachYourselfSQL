# Lesson 9

*Using Aggregate Functions*

Aggregate functions operate on a set of rows to calculate and return a single value.It is to summarize data, scenario
include:

1. Determine the number of rows.
2. Obtain sum of row.
3. Find the highest, lowest and average values in a table column.
4. `AVG()`,`COUNT()`,`MAX()`,`MIN()`,`SUM()`

*AVG()*

`AVG()` returns the average value of specific column.

```
SELECT AVG(prod_price) AS avg_price
FROM products;
```

`AVG()` applies on individual column only and `NULL` values will be ignored.

*COUNT()*

`COUNT()` returns number of rows.

- `COUNT(*)` will return number of rows in a table ,contain `NULL` value.
- `COUNT(column)` will return number of rows in a specific column, ignore `NULL`

```
SELECT COUNT(*) AS num_cust
FROM customers;

SELECT COUNT(cust_email) AS num_cust
FROM customers;
```

*MAX()*

`MAX()` returns the highest value in column.

```
SELECT MAX(prod_price) AS max_price
FROM products;
```

`MAX()` is usually used to find the highest numeric or date values. `NULL` will be ignored.

*MIN()*

`MIN()` is the opposite of `MAX()`

*SUM()*

`SUM()` returns total of the values in column.

```
SELECT SUM(quantity) AS items_ordered
FROM orderitems
WHERE order_num = 20005;

SELECT SUM(item_price*quantity) AS total_price
FROM orderitems
WHERE order_num = 20005;
```

`NULL` will be ignored.

*Aggregates on Distinct Values*

```
SELECT AVG(DISTINCT prod_price) AS avg_price
FROM products
WHERE vend_id = 'DLL01'
```

- `DISTINCT` can not apply on `COUNT(*)`
- `DISTINCT` must be used with column name and not calculation or expression.

*Combining Aggregate Functions*

```
SELECT COUNT(*)        AS num_items,
       MIN(prod_price) AS price_min,
       MAX(prod_price) AS price_max,
       AVG(prod_price) AS price_avg
FROM products;
```
