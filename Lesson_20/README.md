# Lesson 20

*Understanding Transaction Processing*

Transaction is used to maintain database integrity by ensuring batch of SQL operation execute completely or not at all.

- Transaction: A block of SQL statements.
- Rollback: The process of undoing specified SQL statements.
- Commit: Writing unsaved SQL statements to database table.
- Savepoint: A mark in a transaction set to which you can issue a rollback.

*Controlling Transaction*

Break SQL statements into logical chunks and explicitly stating when data should be rolled back.

```
BEGIN TRANSACTION
...
COMMIT TRANSACTION
```

SQL `ROLLBACK` is used to undo SQL statements.

To force an explicit commit, `COMMIT` statement is used.

`SAVEPOINT` enable you to do partial commits or rollback.
