# Lesson 22

*Understanding Constraints*

Performing client-side checks is a time-consuming process.Having the DBMS do the checks for you is far more efficient.

*Primary Keys*

To ensure value in a column are unique and never change. And primary key values can never be reused.

*Foreign Keys*

A foreign key is a column in a table whose values must be listed in a primary key in another table. It's important part
of ensuring referential integrity.

*Unique Constraints*

To ensure all data in a column is unique. Compare with primary key , unique constraint can be multiple or NULL or
updated or reused but it can not be defined as foreign keys.

*Check Constraints*

It's used to ensure data in a column meets a set of criteria.

*Understanding Indexes*

Indexes are used to sort data logically to improve the speed of searching and sorting operations.

Primary key data is always sorted.

Once you set index on one column the DBMS keeps a sorted list of that content for its own use. So when do search it will
not start from row one but use index to locate content faster. However, index will degrade the performance of data
insertion, modification and deletion. Because when these operations are executed, the DBMS has to update the index
dynamically. Also index data can take up lots of storage. Not all data is suitable for indexing. Data that is
sufficiently unique can benefit more from indexes. Indexes are used for data filtering and data sorting.

*Understanding Triggers*

Triggers are special stored procedures that are executed automatically when specific database activity occurs. It can be
associated with `INSERT`,`UPDATE` and `DELETE`

Within triggers, your code has access to the following:

- All new data in `INSERT` operations
- All new data and old data in `UPDATE` operations
- DELETE data in `DELETE` operations.

Depending on the DBMS being used, triggers can be executed before or after a specified operation is performed.

*Database Security*

Some operations that are often secured:

- Access to database administration features ( creating tables, altering or dropping existing table).
- Access to specific database or tables.
- The type of access (read-only,access to specific columns)
- Access to tables via views or stored procedures.
- Restricting the ability to manage user accounts.

Use `GRANT` and `REVOKE` to manage security.
