# 📅 SQL Date Functions Summary

## 🔹 Date Functions Comparison Table

| **Function**          | **Purpose**                            | **MySQL**                                  | **PostgreSQL**                             | **SQL Server**                             |
|-----------------------|----------------------------------------|--------------------------------------------|--------------------------------------------|--------------------------------------------|
| `DATEDIFF`            | Days between two dates                 | `DATEDIFF(date1, date2)`                   | `date1 - date2`                             | `DATEDIFF(day, date2, date1)`              |
| `DATE_ADD`            | Add interval to date                   | `DATE_ADD(date, INTERVAL x DAY)`           | `date + INTERVAL 'x day'`                  | `DATEADD(day, x, date)`                    |
| `DATE_SUB`            | Subtract interval from date            | `DATE_SUB(date, INTERVAL x DAY)`           | `date - INTERVAL 'x day'`                  | `DATEADD(day, -x, date)`                   |
| `NOW()`               | Current date & time                    | `NOW()`                                    | `NOW()`                                    | `GETDATE()`                                |
| `CURDATE()`           | Current date only                      | `CURDATE()`                                | `CURRENT_DATE`                             | `CAST(GETDATE() AS DATE)`                  |
| `CURTIME()`           | Current time only                      | `CURTIME()`                                | `CURRENT_TIME`                             | `CAST(GETDATE() AS TIME)`                  |
| `EXTRACT()`           | Extract year/month/day etc.            | `EXTRACT(YEAR FROM date)`                  | `EXTRACT(YEAR FROM date)`                  | `DATEPART(YEAR, date)`                     |
| `TO_CHAR()`           | Format date                            | `DATE_FORMAT(date, '%Y-%m-%d')`            | `TO_CHAR(date, 'YYYY-MM-DD')`              | `FORMAT(date, 'yyyy-MM-dd')`              |
| `DAYNAME()`           | Get day of week name                   | `DAYNAME(date)`                            | `TO_CHAR(date, 'Day')`                     | `DATENAME(WEEKDAY, date)`                 |
| `DAYOFWEEK()`         | Get numeric weekday (1=Sun in MySQL)   | `DAYOFWEEK(date)`                          | `EXTRACT(DOW FROM date)` (0=Sun)           | `DATEPART(WEEKDAY, date)`                 |
| `LAST_DAY()`          | Last day of the month                  | `LAST_DAY(date)`                           | `date_trunc('MONTH', date) + INTERVAL '1 MONTH - 1 day'` | `EOMONTH(date)`               |
| `WEEK()`              | Week number of the year                | `WEEK(date)`                               | `EXTRACT(WEEK FROM date)`                  | `DATEPART(WEEK, date)`                    |
| `TIMESTAMPDIFF()`     | Difference by unit                     | `TIMESTAMPDIFF(unit, date1, date2)`        | `EXTRACT(EPOCH FROM date2 - date1)/unit`   | `DATEDIFF(unit, date1, date2)`            |

---

## 🧠 Example Use Cases

| **Use Case**                              | **MySQL Example**                                                 |
|-------------------------------------------|-------------------------------------------------------------------|
| Find record where temp > yesterday        | `w1.recordDate = DATE_ADD(w2.recordDate, INTERVAL 1 DAY)`         |
| Get records in the last 7 days            | `recordDate >= CURDATE() - INTERVAL 7 DAY`                        |
| Get current year                          | `EXTRACT(YEAR FROM NOW())`                                        |
| Format date to 'YYYY-MM-DD'              | `DATE_FORMAT(NOW(), '%Y-%m-%d')`                                  |

---
