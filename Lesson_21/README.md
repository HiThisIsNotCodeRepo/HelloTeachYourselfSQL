# Lesson 21

*Understanding Cursors*

Result Set is the results retrieved by a SQL query.

A cursor is a database query stored on the DBMS server, not a `SELECT`. It can be scrolled up and down through screens
of data.

*Working with Cursors*

Cursors are created using the `DECLARE` statement, which differs from one DBMS to the next.

```
DELCARE CURSOR CustCursor
IS
SELECT * FROM Customers
WHERE cust_email IS NULL;
```

Using cursors.

```
OPEN CURSOR CustCursor
```

Fetch cursor data.

```
DECLARE TYPE CustCursor IS REF CURSOR
RETURN Customers%ROWTYPE;
DECLARE CustRecord Customers%ROWTYPE
BEGIN
    OPEN CustCursor;
    FETCH CustCursor INTO CustRecord;
    CLOSE CustCursor;
END;
```

In above example, `FETCH` is used to retrieve current row, start at the first row into declared variable `CustRecord`

In below example the retrieved data is looped through from the first row to the last.

```
DECLARE TYPE CustCursor IS REF CURSOR
RETURN Customers%ROWTYPE;
DECLARE CustRecord Customers%ROWTYPE
BEGIN
    OPEN CustCursor
    LOOP
    FETCH CustCursor INTO CustRecord;
    EXIT WHEN CustCursor%NOTFOUND;
        ...
    END LOOP;
    CLOSE CustCursor;
END;
```

Closing Cursors

```
CLOSE CustCursor
```
