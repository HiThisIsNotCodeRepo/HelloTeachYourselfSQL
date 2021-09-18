# Lesson 4

*Using the WHERE Clause*

```
SELECT prod_name,prod_price
FROM Products
WHERE prod_price = 3.49;
```

When using both `ORDER BY` and `WHERE`, make sure `ORDER BY` comes after `WHERE`.

*The WHERE Clause Operators*

`=`,`<>`,`!=`,`<`,`<=`,`!<`,`>`,`>=`,`!>`,`BETWEEN`,`IS NULL`.

List all products that cost less than $10.

```
SELECT prod_name, prod_price
FROM Products
WHERE prod_price < 10;
```

List all products that cost $10 or less.

```
SELECT prod_name, prod_price
FROM Products
WHERE prod_price <= 10;
```

List all products not made by vendor DLL01

```
SELECT vend_id, prod_name
FROM Products
WHERE vend_id <> 'DLL01';
```

If compare a value against string type column, delimiting quotes are required.

Retrieve all products with a price between $5 and $10.

```
SELECT prod_name, prod_price
FROM Products
WHERE prod_price BETWEEN 5 AND 10;
```

`BETWEEN` matches all values in the range including specified start and end value.

Return a list of all products have no price.

```
SELECT prod_name
FROM Products
WHERE prod_price IS NULL;
```

Be cautious when the enquiry is filtered against specific value the `NULL` records won't return.
