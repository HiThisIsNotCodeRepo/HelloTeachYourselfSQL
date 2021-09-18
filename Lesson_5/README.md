# Lesson 5

*Combining WHERE Clauses*

To join multiple `WHERE` clause using `AND` or `OR`.

```
SELECT prod_id, prod_price, prod_name
FROM Products
WHERE vend_id = 'DLL01'
  AND prod_price <= 4;
```

`AND` requires to meet all condition specified.

```
SELECT prod_name, prod_price
FROM Products
WHERE vend_id = 'DLL01'
   OR vend_id = 'BRS01';
```

`OR` is opposite of `AND` it requires record match either condition.

*Understanding Order of Evaluation*

`AND` has higher precedence than `OR`, `()` has the highest precedence.

```
SELECT prod_name, prod_price
FROM Products
WHERE (vend_id = 'DLL01' OR vend_id = 'BRS01')
  AND prod_price >= 10;
```

*Using the IN Operator*

```
SELECT prod_name, prod_price
FROM Products
WHERE vend_id IN ('DLL01', 'BRS01')
ORDER BY prod_name;
```

Basically `IN` achieves the same goal as `OR`. And `IN` can contain another `SELECT` statement.

*Using the NOT Operator*

To negate condition , can be used before column. `NOT` could be handy when use with `IN` operator.

```
SELECT prod_name
FROM Products
WHERE NOT vend_id = 'DLL01'
ORDER BY prod_name;
```
