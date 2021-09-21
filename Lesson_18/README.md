# Lesson 18

*Understanding Views*

Views are virtual tables. When used, view will dynamically retrieve data.

Retrieve from table:

```
SELECT cust_name, cust_contact
FROM customers,
     orders,
     orderitems
WHERE customers.cust_id = orders.cust_id
  AND orderitems.order_num = orders.order_num
  AND prod_id = 'RGAN01';
```

Retrieve from view:

```
SELECT cust_name, cust_contact
FROM productcustomers
WHERE prod_id = 'RGAN01';
```

*Why Use Views*

- To reuse SQL statements.
- To simplify complex SQL operations.
- To change data formatting and representation. Views can return data formatted and presented differently from their
  underlying tables.

*Performance Issues*

Because views contain no data, any retrieval actually is from execution of query. And if the views are too complex the
performance may degrade.

*View Rules and Restrictions*

- Like tables, views' name must be unique. They must be different from other table or view.
- Views can be nested, that is a views can be built using a query that retrieves data from another view.
- Views cannot be indexed, nor can they have triggers or default values.

*Creating Views*

Using `CREATE VIEW` to create view, to remove a view use `DROP VIEW viewname`. To update a view you must first `DROP`
and then recreate it.

*Using Views to Simplify Complex Joins*

```
CREATE VIEW productcustomers AS
SELECT cust_name, cust_contact, prod_id
FROM customers,
     orders,
     orderitems
WHERE customers.cust_id = orders.cust_id
  AND orderitems.order_num = orders.order_num;
```

*Using Views to Reformat Retrieved Data*

```
CREATE VIEW VendorLocations AS
SELECT RTRIM(vend_name) || ' (' || RTRIM(vend_country) || ')' AS vend_title
FROM vendors;
```

*Using Views to Filter Unwanted Data*

```
CREATE VIEW CustomerEMailList AS
SELECT cust_id, cust_name, cust_email
FROM customers
WHERE cust_email IS NOT NULL;
```

*Using Views with Calculated Fields*

```
CREATE VIEW OrderItemsExpanded AS
SELECT order_num, prod_id, quantity, item_price, quantity * item_price AS expanded_price
FROM orderitems;
```
