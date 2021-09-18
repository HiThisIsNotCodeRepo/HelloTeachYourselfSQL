# Lesson 2

*Retrieving Individual Columns*

```
SELECT prod_name
FROM Products;
```

The return records are unsorted and unfiltered.

SQL statement is case-insensitive. By convention SQL keywords are uppercase and column and table names are lowercase.

*Retrieving Multiple Columns*

```
SELECT prod_id, prod_name, prod_price
FROM Products;
```

*Retrieving All Columns*

```
SELECT *
FROM Products;
```

Be cautious using `*` retrieving unnecessary columns will slow down the performance of retrieval and application.

*Retrieving Distinct Rows*

```
SELECT DISTINCT vend_id
FROM Products;
```

`DISTINCT` apply to all columns, not just the one it precedes. So if multiple columns appear after `DISTINCT` the
combination value of individual column will be distinctive.

*Limiting Results*

To retrieve first 5 rows.

```
SELECT DISTINCT prod_name
FROM Products
limit 5;
```

To get next 5 rows.

```
SELECT DISTINCT prod_name
FROM Products
LIMIT 5 OFFSET 5;
```

`LIMIT` specifies the number of rows to return, `OFFSET` indicate where to start. The first retrieved row is row 0 not
row 1. `LIMIT 1 OFFSET 1` will retrieve the second row not the first row.

*Comment*

Inline

```
SELECT DISTINCT prod_name
FROM Products -- this is inline comment
limit 5 OFFSET 5;
```

Multi lines

```
/*
    This is multi line comments
 */
SELECT DISTINCT prod_name
FROM Products
limit 5 OFFSET 5;
```
