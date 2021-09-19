# Lesson 14

*Understanding Combined Querires*

SQL enables you to perform multiple `SELECT` statements and return the result as a single query and these combined
queries known as unions or compound queries.

*Creating Combined Queries*

```
SELECT cust_name, cust_contact, cust_email
FROM customers
WHERE cust_state IN ('IL', 'IN', 'MI')
UNION
SELECT cust_name, cust_contact, cust_email
FROM customers
WHERE cust_name = 'Fun4All';
```

`UNION` instructs the DBMS to execute both `SELECT` statements and combine the output into a single query result set.
Using `WHERE` can achieve same result:

```
SELECT cust_name, cust_contact, cust_email
FROM customers
WHERE cust_state IN ('IL', 'IN', 'MI')
OR cust_name = 'Fun4All';
```

`UNION` rules:

- `UNION` must be composed of two or more `SELECT` statements.
- Each query in `UNION` must contain the same columns, expression, or aggregate functions.

*Including or Eliminating Duplicate Rows*

By default `UNION` will automatically remove any duplicate rows from query result set.

```
SELECT cust_name, cust_contact, cust_email
FROM customers
WHERE cust_state IN ('IL', 'IN', 'MI')
UNION ALL
SELECT cust_name, cust_contact, cust_email
FROM customers
WHERE cust_name = 'Fun4All';
```

Using `UNION ALL` will not eliminate duplication.

*Sorting Combined Query Results*

When using `UNION` only final `SELECT` statement's `ORDER BY` will count.

```
SELECT cust_name, cust_contact, cust_email
FROM customers
WHERE cust_state IN ('IL', 'IN', 'MI')
UNION
SELECT cust_name, cust_contact, cust_email
FROM customers
WHERE cust_name = 'Fun4All'
ORDER BY cust_name, cust_contact;
```
