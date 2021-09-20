# Lesson 16

*Updating Data*

`UPDATE` can be used in two ways:

- To update specific rows in a table.
- To update all rows in a table.

```
UPDATE customers
SET cust_email = 'kim@thetoystore.com'
WHERE cust_id = '1000000005';
```

Without `WHERE` , the DBMS would update all the rows in the customers.

The syntax to update multiple columns.

```
UPDATE customers
SET cust_contact = 'Sam Roberts',
    cust_email   = 'sam@toyland.com'
WHERE cust_id = '1000000006';
```

To use `UPDATE` delete a column's value , you can set it to `NULL`.

```
UPDATE customers
SET cust_email = NULL
WHERE cust_id = '1000000005';
```

*Deleting Data*

`DELETE` can be used in two ways:

- To delete specific rows from a table.
- To delete all rows from a table.

```
DELETE
FROM customers
WHERE cust_id = '1000000006';
```

When foreign key are present, the DBMS uses them to enforce referential integrity. This could prevent the deletion of
rows that are needed for a relationship.

Faster way to delete all rows from a table.

```
TRUNCATE TABLE
```

It's much quicker because data changes are not logged.

*Guidelines for Updating and Deleting Data*

- Never execute an `UPDATE` or a `DELETE` without a `WHERE`.
