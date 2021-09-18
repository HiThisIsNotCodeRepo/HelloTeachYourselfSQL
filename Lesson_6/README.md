# Lesson 6

*Using the LIKE Operator*

Wildcard searching can only be used with text fields.

*The Percent Sign(%) Wildcard*

`%` match any number(from 0 to any) of any character.

```
SELECT prod_id, prod_name
FROM Products
WHERE prod_name LIKE 'Fish%';
```

Find all products started with the word Fish . Also do take note the search is case-sensitive.

Use `%` on both sides.

```
SELECT prod_id, prod_name
FROM Products
WHERE prod_name LIKE '%bean bag%';
```

Use `%` in middle.

```
SELECT prod_id, prod_name
FROM Products
WHERE prod_name LIKE 'F%y';
```

Some DBMSs pad field contents with spaces. In this case the text in column may end with space, to use wildcard searching
properly recommend using the function to trim the space when do enquiry or append `%` at search pattern.

`%` will not match `NULL`.

*The Underscore(_) Wildcard*

`_` only match a single character.

```
SELECT prod_id, prod_name
FROM Products
WHERE prod_name LIKE '__ inch teddy bear%';
```

*Tips for Using Wildcards*

Because wildcard search typically take far longer to process don't overuse it. If really needs to ,try not use them at
the beginning of the search pattern, because they are the slowest to process.
