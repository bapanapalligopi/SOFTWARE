Those functions are **not covered in your uploaded notes**. 

If you're expanding your SQL Date & Time chapter, then yes, these are important functions to include.

| Function        | Purpose                          | Example                                                                    |
| --------------- | -------------------------------- | -------------------------------------------------------------------------- |
| `DATE_SUB()`    | Subtract an interval from a date | `DATE_SUB(CURRENT_DATE, INTERVAL 7 DAY)`                                   |
| `DATE_ADD()`    | Add an interval to a date        | `DATE_ADD(CURRENT_DATE, INTERVAL 1 MONTH)`                                 |
| `DATE_FORMAT()` | Format a DATE/DATETIME           | `DATE_FORMAT(order_date,'%d-%m-%Y')`                                       |
| `TIME_FORMAT()` | Format a TIME value              | `TIME_FORMAT(login_time,'%H:%i:%s')` *(typically used with `TIME` values)* |

### 1. DATE_SUB()

Subtracts an interval from a date.

**Syntax**

```sql
DATE_SUB(date, INTERVAL value unit)
```

**Examples**

```sql
SELECT DATE_SUB('2029-05-20', INTERVAL 10 DAY);
```

Output

```
2029-05-10
```

```sql
SELECT *
FROM orders
WHERE order_date >= DATE_SUB(CURRENT_DATE, INTERVAL 30 DAY);
```

---

### 2. DATE_ADD()

Adds an interval to a date.

```sql
SELECT DATE_ADD('2029-05-20', INTERVAL 10 DAY);
```

Output

```
2029-05-30
```

Another example

```sql
SELECT DATE_ADD(CURRENT_DATE, INTERVAL 1 MONTH);
```

---

### 3. DATE_FORMAT()

Formats a DATE or DATETIME into a readable string.

**Syntax**

```sql
DATE_FORMAT(date, 'format')
```

Examples

```sql
SELECT DATE_FORMAT('2029-05-20','%d-%m-%Y');
```

Output

```
20-05-2029
```

```sql
SELECT DATE_FORMAT('2029-05-20','%W');
```

Output

```
Sunday
```

Common format specifiers:

| Format | Meaning        | Example |
| ------ | -------------- | ------- |
| `%Y`   | 4-digit year   | 2029    |
| `%y`   | 2-digit year   | 29      |
| `%m`   | Month (01-12)  | 05      |
| `%d`   | Day (01-31)    | 20      |
| `%M`   | Month name     | May     |
| `%W`   | Weekday name   | Sunday  |
| `%H`   | Hour (24-hour) | 18      |
| `%h`   | Hour (12-hour) | 06      |
| `%i`   | Minutes        | 45      |
| `%s`   | Seconds        | 30      |

---

### 4. TIME_FORMAT()

Formats a `TIME` value.

```sql
SELECT TIME_FORMAT('18:45:30','%h:%i %p');
```

Output

```
06:45 PM
```

If your column is `DATETIME`, extract the time first:

```sql
SELECT TIME_FORMAT(TIME(login_time), '%h:%i:%s %p')
FROM login_history;
```

---

## Other Useful Date & Time Functions (Commonly Asked)

| Function       | Purpose                    |
| -------------- | -------------------------- |
| `NOW()`        | Current date and time      |
| `CURDATE()`    | Current date               |
| `CURTIME()`    | Current time               |
| `DATE()`       | Extract date from DATETIME |
| `TIME()`       | Extract time from DATETIME |
| `DAYNAME()`    | Day name                   |
| `MONTHNAME()`  | Month name                 |
| `LAST_DAY()`   | Last day of the month      |
| `DAYOFMONTH()` | Day number in the month    |
| `DAYOFWEEK()`  | Day number in the week     |
| `DAYOFYEAR()`  | Day number in the year     |
| `WEEK()`       | Week number                |
| `QUARTER()`    | Quarter (1–4)              |

For **SQL interviews and placements**, the most frequently used date/time functions are:

* ✅ `YEAR()`
* ✅ `MONTH()`
* ✅ `DAY()`
* ✅ `HOUR()`
* ✅ `MINUTE()`
* ✅ `SECOND()`
* ✅ `DATE()`
* ✅ `TIME()`
* ✅ `DATE_ADD()`
* ✅ `DATE_SUB()`
* ✅ `DATEDIFF()`
* ✅ `TIMESTAMPDIFF()`
* ✅ `DATE_FORMAT()`
* ✅ `NOW()`
* ✅ `CURDATE()`
* ✅ `CURRENT_TIMESTAMP`
* ✅ `CURRENT_DATE`

These cover the majority of date and time questions asked in coding interviews and SQL practice platforms.
