# Lesson 17

*Creating Tables*

```
CREATE TABLE Products
(
    prod_id    char(10)      NOT NULL ,
    vend_id    char(10)      NOT NULL ,
    prod_name  char(255)     NOT NULL ,
    prod_price decimal(8,2)  NOT NULL ,
    prod_desc  varchar(1000) NULL
);
```

To prevent accidental overwriting, SQL requires you first manually remove a table and then recreate it.

*Working with NULL Values*

```
CREATE TABLE Orders
(
    order_num  int      NOT NULL ,
    order_date date     NOT NULL ,
    cust_id    char(10) NOT NULL
);
```

In above sql , all three columns are required. This will prevent the insertion of columns with no value.

*Specifying Default Values*

```
CREATE TABLE orderitems
(
    order_num  INTEGER       NOT NULL,
    order_item INTEGER       NOT NULL,
    prod_id    CHAR(10)      NOT NULL,
    quantity   INTEGER       NOT NULL DEFAULT 1,
    item_price DECIMAL(8, 2) NOT NULL
)
```

`DEFAULT 1` instructs DBMS to use quantity of 1 if no quantity is specified. Default values are often used to store
values in date or time stamp columns for example in MYSQL user may specify `DEFAULT CURRENT_DATE()`, Oracle users may
specify `DEFAUTL SYSDATE`, SQL Server users may specify `DEFAULT GETDATE()`

*Updating Tables*

To update table definition, `ALTER TABLE` statement is used.

- All DBMSs allow you to add columns to existing tables.
- Many DBMSs do not allow you to remove or change columns.
- Most DBMSs allow you to rename columns.

```
ALTER TABLE vendors
    ADD vend_phone CHAR(20);
```

*Deleting Tables*

```
DROP TABLE CustCopy;
```

However, when the table involves foreign key, many DBMS will prevent the dropping of tables.

*Renaming Tables*

The renaming is different from implementation. Refer to DBMS documentation for details.
