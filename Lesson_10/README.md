# Lesson 10

*Understanding Data Grouping*

Group allows you divide data into logical sets, so you can perform aggregate calculations on each group.

*Creating Groups*

Use `GROUP BY`.

```
SELECT vend_id, COUNT(*) AS num_prods
FROM products
GROUP BY vend_id;
```

1. `GROUP BY` can contain multiple columns and thus enable you to nest group.
2. Every column in `SELECT` statement must be present in the GROUP BY clause except aggregate calculation.
3. `NULL` will be considered as a group.
4. `GROUP BY` must come after `WHERE` and before `ORDER BY`.

*Filtering Groups*

`HAVING` is similar to `WHERE` but it filters group instead of specific row, also `HAVING` supports all `WHERE`
operators.

```
SELECT cust_id, COUNT(*) AS orders
FROM orders
GROUP BY cust_id
HAVING count(*) >= 2;
```

*Grouping and Sorting*

```
SELECT order_num, COUNT(*) AS items
FROM orderitems
GROUP BY order_num
HAVING count(*) >= 3
ORDER BY items, order_num;
```
