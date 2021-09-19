# Lesson 12

*Understanding Joins*

Relational tables are designed so that information is split into multiple tables, and they are related to each other
through common values.

*Understanding Scale*

Able to handle an increasing load without failing. A well-designed database or application is said to scale well.

*Why Use Joins*

To retrieve data from different table with a single `SELECT` statement.

*Creating a Join*

```
SELECT vend_name, prod_name, prod_price
FROM vendors,
     products
WHERE vendors.vend_id = products.vend_id;
```

The `WHERE` is to instruct the DBMS how to join the tables, without it the number of rows retrieved will be the number
of rows in the first table multiplied by the number of rows in the second tables, known as **Cartesian Product**(
Or **Cross Joins**).

*Inner Joins*

```
SELECT vend_name, prod_name, prod_price
FROM vendors
         INNER JOIN products ON vendors.vend_id = products.vend_id;
```

Same as `WHERE vendors.vend_id = products.vend_id `

*Joining Multiple Tables*

```
SELECT prod_name, vend_name, prod_price, quantity
FROM orderitems,
     products,
     vendors
WHERE products.vend_id = vendors.vend_id
  AND orderitems.prod_id = products.prod_id
  and order_num = 20007;

```
