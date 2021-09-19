# Lesson 15

*Understanding Data Insertion*

Insert can be used in several ways:

- Inserting a single complete row.
- Inserting a single partial row
- Inserting the results of a query.

*Inserting Complete Rows*

```
INSERT INTO customers
VALUES ('1000000006', 'Toy Land', '123 Any Street', 'New York', 'NY', '11111', 'USA', NULL, NULL);
```

Inserting rule:

- The data to be stored in each table column is specified in the `VALUES` clause, and a value must be provided for every
  column. If a column has no value `NULL` should be used.
- The columns must be populated in the order in which they appear in the table definition.
- This syntax should be avoided.

Safer way

```
INSERT INTO customers(cust_id, cust_name, cust_address, cust_city, cust_state, cust_zip, cust_country, cust_contact,
                      cust_email)
VALUES ('1000000006', 'Toy Land', '123 Any Street', 'New York', 'NY', '11111', 'USA', NULL, NULL);
```

In above syntax each column in `VALUES` corresponds to specific column after table name. The advantage of this is even
the table layout changes , the `INSERT` statement still correct.

*Inserting Partial Rows*

```
INSERT INTO customers(cust_id, cust_name, cust_address, cust_city, cust_state, cust_zip, cust_country)
VALUES ('1000000006', 'Toy Land', '123 Any Street', 'New York', 'NY', '11111', 'USA');
```

You can omit column when insert if :

1. The defined column is allowing `NULL`.
2. A default value is specified.

*Inserting Retrieved Data*

It's made up of an `INSERT` statement and `SELECT` statement.

```
INSERT INTO customers(cust_id, cust_contact,cust_email, cust_name, cust_address, cust_city, cust_state, cust_zip, cust_country)
SELECT cust_id,
       cust_contact,
       cust_email,
       cust_name,
       cust_address,
       cust_city,
       cust_state,
       cust_zip,
       cust_country
FROM custnew;
```

All data from custnew will be inserted into customers. And the column name in `SELECT` does not need to be the same as
the one after table name.

*Copying from One Table to Another*

```
SELECT *
INTO custcopy
FROM customers;
```

This `SELECT` statement create a new table and copies the entire contents of customers into it. To copy only a subset of
columns, explicit column name can be specified instead of `*`
