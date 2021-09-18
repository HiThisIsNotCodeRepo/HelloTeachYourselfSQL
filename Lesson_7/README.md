# Lesson 7

*Understanding Calculated Fields*

When data stored within a database's table is not in the format needed by application, we can use calculated field to
reformat the data.

*Concatenating Fields*

```
SELECT vend_name || ' (' || vend_country || ')'
FROM vendors
ORDER BY vend_name;
```

That enquiry will return a single column contain all 4 elements, `vend_name`, `' ('`, `vend_country` and `')'`

If the combined value has excess space due to DBMSs pad column to its width. One way is to apply `RTRIM()` to trims all
space from the right of value.

For reference `LTRIM()` is to trim left side of a string, and `TRIM()` is to trim both right and left.

*Using Aliases*

```
SELECT vend_name || ' (' || vend_country || ')' AS vend_title
FROM vendors
ORDER BY vend_name;
```

Keyword `AS` is to define alias. Although `AS` is optional ,it's highly recommend using it.

*Performing Mathematical Calculations*

```
SELECT prod_id, quantity, item_price, quantity * item_price AS expanded_price
FROM orderitems
WHERE order_num = 20008;
```

`expanded_price` is a calculated field. Other mathematical operators include `+`, `-`, `/`,`()`

If omit `FROM` from `SELECT`, the enquiry will just evaluate expression behind `SELECT`, for example:

- `SELECT 3*2`
- `SELECT Now()`
