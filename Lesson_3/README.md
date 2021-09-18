# Lesson 3

*Sorting Data*

```
SELECT prod_name
FROM Products
ORDER BY prod_name;
```

The sorted column can be unselected in `SELECT`.

*Sorting by Multiple Columns*

```
SELECT prod_id, prod_price, prod_name
FROM Products
ORDER BY prod_price, prod_name;
```

The results will be sorted by `prod_price` first and if adjacent rows have the same `prod_price` then they will be
sorted by `prod_name`.

*Sorting by Column Position*

```
SELECT prod_id, prod_price, prod_name
FROM Products
ORDER BY 2, 3;
```

`ORDER BY 2, 3` means sort by `prod_price` and then by `prod_name`. This technique will not allow you to sort by the
column not show in `SELECT`.

*Specifying Sort Direction*

One column `DESC` sorting.

```
SELECT prod_id, prod_price, prod_name
FROM Products
ORDER BY prod_price DESC;
```

Multiple column and mix `DESC` and `ASC` sorting.

```
SELECT prod_id, prod_price, prod_name
FROM Products
ORDER BY prod_price DESC, prod_name;
```