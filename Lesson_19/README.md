# Lesson 19

*Understanding Stored Procedures*

Stored procedures are simply collections of one or more SQL statements saved for future use.

*Why to Use Stored Procedures*

- To simplify complex operations.
- To improve DBMS performance.

*Downside of Stored Procedures*

- Impossible to write truly portable stored procedure.
- More complex than writing basic SQL.

*Executing Stored Procedures*

```
EXECUTE AddNewProduct ('JTS01','Stuffed Eiffel Tower',6.49,'Plush stuffed toy with the text La Tour Eiffel in red white and blue');
```

*Creating Stored Procedures*

```
CREATE PROCEDURE MailingListCount(
    ListCount OUT INTEGER
)
IS
    v_rows INTEGER;
BEGIN
SELECT COUNT(*)
INTO v_rows
FROM customers
WHERE NOT cust_email IS NULL;
ListCount := v_rows;
END;
```

To invoke:

```
var ReturnValue NUMBER
EXEC MailingListCount (:ReturnValue);
SELECT ReturnValue;
```
