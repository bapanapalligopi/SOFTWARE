Based on your uploaded notes, here are concise interview-focused notes that preserve the concepts, examples, and best practices from the source. 

# SQL Date & Time Functions – Quick Notes

## 1. Extracting Date Parts

### Common Functions

| Function   | Returns | Example |
| ---------- | ------- | ------- |
| `YEAR()`   | Year    | 2029    |
| `MONTH()`  | Month   | 8       |
| `DAY()`    | Day     | 19      |
| `HOUR()`   | Hour    | 12      |
| `MINUTE()` | Minute  | 50      |
| `SECOND()` | Second  | 45      |

```sql
SELECT
    YEAR(date_col),
    MONTH(date_col),
    DAY(date_col);
```

For DATETIME:

```sql
SELECT
    HOUR(datetime_col),
    MINUTE(datetime_col),
    SECOND(datetime_col);
```

---

## 2. EXTRACT() Function (SQL Standard)

```sql
SELECT
    EXTRACT(YEAR FROM joining_date),
    EXTRACT(MONTH FROM joining_date),
    EXTRACT(DAY FROM joining_date);
```

**Syntax**

```sql
EXTRACT(part FROM date_column)
```

Works across many databases.

---

# Extracting Date Parts from Table

```sql
SELECT
    emp_id,
    name,
    YEAR(joining_date) AS join_year,
    MONTH(joining_date) AS join_month
FROM employees;
```

### Important

If the date is NULL

```text
YEAR(NULL)  -> NULL
MONTH(NULL) -> NULL
```

Never returns **0**.

---

# Group By Year and Month

```sql
SELECT
    YEAR(joining_date) AS join_year,
    MONTH(joining_date) AS join_month,
    COUNT(*) AS hires
FROM employees
GROUP BY
    YEAR(joining_date),
    MONTH(joining_date);
```

### Execution Order

```
FROM
↓

GROUP BY
↓

COUNT(*)
↓

SELECT
↓

ORDER BY
```

---

# NULL Behavior

Rows having

```text
joining_date = NULL
```

become

```
YEAR(NULL) = NULL
MONTH(NULL) = NULL
```

All NULL dates form one group.

Example

| Year | Month | Count |
| ---- | ----- | ----- |
| NULL | NULL  | 1     |

---

# Performance Rule (Very Important)

❌ Avoid

```sql
WHERE YEAR(joining_date)=2029
AND MONTH(joining_date)=2;
```

Reason

* Functions wrap the indexed column.
* Index may not be used.
* Can cause Full Table Scan.

---

## Preferred

```sql
WHERE joining_date >= '2029-02-01'
AND joining_date < '2029-03-01';
```

Benefits

* Uses index efficiently
* Faster
* Production recommended

---

# BETWEEN

## Inclusive

```
x BETWEEN a AND b
```

is equivalent to

```sql
x >= a
AND x <= b
```

---

## Date Example

```sql
WHERE order_date BETWEEN
'2029-01-01'
AND
'2029-01-31';
```

Suitable for DATE columns.

---

# DATETIME Interview Trap

Suppose

```sql
WHERE login_time BETWEEN
'2029-01-01'
AND
'2029-01-31';
```

Internally SQL treats it as

```text
2029-01-01 00:00:00

to

2029-01-31 00:00:00
```

Therefore these are **excluded**

```
2029-01-31 09:45:00

2029-01-31 18:00:00

2029-01-31 23:59:59
```

---

## Correct Pattern

```sql
WHERE login_time >= '2029-01-01'
AND login_time < '2029-02-01';
```

This is called a

> Half Open Interval

```
[start_date,
 next_period_start)
```

Benefits

* Includes every timestamp
* Handles milliseconds
* Index friendly
* Industry best practice

---

# Why NOT 23:59:59?

Avoid

```sql
<= '2029-01-31 23:59:59'
```

Because

```
23:59:59.500
```

will be excluded.

---

# MIN() and MAX() on Dates

Earliest Login

```sql
MIN(login_time)
```

Latest Login

```sql
MAX(login_time)
```

Example

```sql
SELECT
    user,
    MIN(login_time),
    MAX(login_time)
FROM logins
GROUP BY user;
```

---

# Count + First + Latest Login

```sql
SELECT
    user,
    MIN(login_time),
    MAX(login_time),
    COUNT(*)
FROM logins
GROUP BY user;
```

Useful for

* User analytics
* Audit logs
* Login history

---

# DATEDIFF()

Returns difference in **Days**

```sql
DATEDIFF(end_date,start_date)
```

Example

```sql
SELECT
DATEDIFF('2029-07-19',
         '2029-01-10');
```

Output

```
190
```

### Notes

* Ignores time
* Uses only date part

---

# TIMESTAMPDIFF()

Returns difference in specified unit.

Syntax

```sql
TIMESTAMPDIFF(unit,
start,
end)
```

Example

```sql
TIMESTAMPDIFF(
HOUR,
start_time,
end_time
)
```

Possible Units

* SECOND
* MINUTE
* HOUR
* DAY
* MONTH
* YEAR

Returns **whole units only**.

---

# CURRENT_DATE

Returns today's date.

Example

```sql
CURRENT_DATE
```

---

# CURRENT_TIMESTAMP

Returns current date and time.

```sql
CURRENT_TIMESTAMP
```

---

# Today's Logins

Recommended

```sql
WHERE login_time >= CURRENT_DATE
AND login_time <
DATE_ADD(CURRENT_DATE,
INTERVAL 1 DAY);
```

---

# Delivery Time Example

```sql
TIMESTAMPDIFF(
MINUTE,
order_placed_at,
delivered_at
)
```

Can classify deliveries using CASE

* Pending
* Bad Data
* On Time
* Slow

---

# Monthly Orders

```sql
SELECT
YEAR(order_placed_at),
MONTH(order_placed_at),
COUNT(*)
FROM deliveries
GROUP BY
YEAR(order_placed_at),
MONTH(order_placed_at);
```

---

# Interview Tips

### ✔ DATE

```
Stores only date
```

Example

```
2029-08-19
```

---

### ✔ DATETIME

```
Stores date + time
```

Example

```
2029-08-19 12:50:45
```

---

### ✔ DATE Functions

```
YEAR()

MONTH()

DAY()

HOUR()

MINUTE()

SECOND()
```

---

### ✔ Aggregates for Dates

```
MIN()

MAX()

COUNT()
```

---

### ✔ Difference Functions

```
DATEDIFF()

TIMESTAMPDIFF()
```

---

### ✔ Best Practices

* Never use `YEAR()` or `MONTH()` in `WHERE` on indexed columns.
* Use date ranges (`>=` and `<`) instead.
* Avoid `BETWEEN` with `DATETIME` columns.
* Prefer **half-open intervals** (`>= start AND < next_period_start`).
* `MIN()` returns the earliest date.
* `MAX()` returns the latest date.
* `DATEDIFF()` ignores time.
* `TIMESTAMPDIFF()` considers both date and time.
* `CURRENT_DATE` returns only the date.
* `CURRENT_TIMESTAMP` returns both date and time.
Yes. Based **only on your uploaded notes**, a few functions and keywords are present but weren't explicitly listed in the summary. 

| Function / Keyword  | Purpose                      | Present in Notes           |
| ------------------- | ---------------------------- | -------------------------- |
| `YEAR()`            | Extract year                 | ✅                          |
| `MONTH()`           | Extract month                | ✅                          |
| `DAY()`             | Extract day                  | ✅                          |
| `HOUR()`            | Extract hour                 | ✅                          |
| `MINUTE()`          | Extract minute               | ✅                          |
| `SECOND()`          | Extract second               | ✅                          |
| `EXTRACT()`         | SQL standard date extraction | ✅                          |
| `DATEDIFF()`        | Difference in days           | ✅                          |
| `TIMESTAMPDIFF()`   | Difference in specified unit | ✅                          |
| `CURRENT_DATE`      | Current system date          | ✅                          |
| `CURRENT_TIMESTAMP` | Current system date & time   | ✅                          |
| `DATE()`            | Create/convert to DATE       | **❌ Missed**               |
| `TIMESTAMP()`       | Create/convert to DATETIME   | **❌ Missed**               |
| `DATE_ADD()`        | Add interval to a date       | **❌ Missed**               |
| `BETWEEN`           | Inclusive range operator     | ✅ (operator, not function) |
| `COUNT()`           | Aggregate count              | ✅                          |
| `MIN()`             | Earliest date/time           | ✅                          |
| `MAX()`             | Latest date/time             | ✅                          |
| `CASE`              | Conditional expressions      | **❌ Missed**               |

### 1. `DATE()`

Used to create or convert a value to a DATE.

```sql
SELECT DATE('2029-08-19');
```

Output:

```
2029-08-19
```

Used in the notes for sample variables. 

---

### 2. `TIMESTAMP()`

Creates a DATETIME/TIMESTAMP value.

```sql
SELECT TIMESTAMP('2029-05-18 12:50:45');
```

Used for sample DATETIME values. 

---

### 3. `DATE_ADD()`

Adds an interval to a date.

```sql
DATE_ADD(CURRENT_DATE, INTERVAL 1 DAY)
```

Used to find records until the start of the next day. 

---

### 4. `CASE`

Conditional logic inside SQL queries.

```sql
CASE
    WHEN delivered_at IS NULL THEN 'Pending'
    WHEN delivered_at < order_placed_at THEN 'Bad Data'
    WHEN TIMESTAMPDIFF(SECOND, order_placed_at, delivered_at) <= 60 * 30
         THEN 'On Time'
    ELSE 'Slow'
END
```

Used for delivery status classification. 

---

## Complete Function List From Your Notes

### Date Extraction

* `YEAR()`
* `MONTH()`
* `DAY()`
* `HOUR()`
* `MINUTE()`
* `SECOND()`
* `EXTRACT()`

### Date Creation

* `DATE()`
* `TIMESTAMP()`

### Date Difference

* `DATEDIFF()`
* `TIMESTAMPDIFF()`

### Current Date & Time

* `CURRENT_DATE`
* `CURRENT_TIMESTAMP`

### Date Arithmetic

* `DATE_ADD()`

### Aggregate Functions

* `COUNT()`
* `MIN()`
* `MAX()`

### Conditional Logic

* `CASE`

### Operators / Clauses

* `BETWEEN`
* `GROUP BY`
* `ORDER BY`
* `WHERE`

These are all the functions, keywords, and operators explicitly covered in your uploaded notes. 
