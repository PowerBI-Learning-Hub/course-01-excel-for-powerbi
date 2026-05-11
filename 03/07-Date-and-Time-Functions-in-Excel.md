# Date & Time Functions in Excel

## Core Idea

Excel stores dates and times as **serial numbers** internally.

This allows analysts to:

* Calculate project durations
* Track deadlines
* Analyze monthly/yearly trends
* Build dynamic reports
* Calculate working days
* Monitor employee/service durations

---

# Sample Dataset — Project Tracking

| Project ID | Start Date | End Date   | Working Days | Current Date | Current Time |
| ---------- | ---------- | ---------- | ------------ | ------------ | ------------ |
| PRJ-1001   | 01/05/2026 | 31/05/2026 |              |              |              |
| PRJ-1002   | 10/05/2026 | 15/06/2026 |              |              |              |
| PRJ-1003   | 20/05/2026 | 30/06/2026 |              |              |              |

---

# How Excel Tracks Dates & Time

## Date Serial Numbers

| Date       | Serial Number |
| ---------- | ------------- |
| 01/01/1900 | 1             |
| 02/01/1900 | 2             |
| 11/05/2026 | Large Number  |

Every new day increases serial number by 1.

---

## Time Storage

Excel stores time as fractions.

| Time     | Stored Value |
| -------- | ------------ |
| 12:00 PM | 0.5          |
| 6:00 AM  | 0.25         |

---

# Important Date & Time Functions

| Function        | Purpose                  |
| --------------- | ------------------------ |
| `TODAY()`       | Current date             |
| `NOW()`         | Current date + time      |
| `DAY()`         | Extract day              |
| `MONTH()`       | Extract month            |
| `YEAR()`        | Extract year             |
| `DATE()`        | Build a date             |
| `NETWORKDAYS()` | Count workdays           |
| `DATEDIF()`     | Difference between dates |

---

# TODAY Function

## Purpose

Display dynamic current date.

---

## Formula

```excel id="e3n7xy"
=TODAY()
```

---

## Example Result

```text id="szgrql"
11/05/2026
```

---

## Important

* Updates automatically daily
* No arguments required
* Parentheses still mandatory

Correct:

```excel id="5knim5"
=TODAY()
```

Wrong:

```excel id="w5izdf"
=TODAY
```

---

# NOW Function

## Purpose

Display current date + time.

---

## Formula

```excel id="l96f2s"
=NOW()
```

---

## Example Result

```text id="m92dtm"
11/05/2026 14:30
```

---

## Use Cases

* Timestamp logging
* Refresh monitoring
* Audit tracking

---

# DAY Function

## Goal

Extract day from full date.

---

# Sample Dataset

| Full Date  | Day |
| ---------- | --- |
| 11/05/2026 | 11  |

---

## Formula

```excel id="c46vv5"
=DAY(A2)
```

---

# MONTH Function

## Formula

```excel id="63buv0"
=MONTH(A2)
```

---

## Result

```text id="p1bdwb"
5
```

---

## Use Cases

* Monthly grouping
* Trend analysis
* Pivot reporting

---

# YEAR Function

## Formula

```excel id="chp1fv"
=YEAR(A2)
```

---

## Result

```text id="v89t3y"
2026
```

---

## Use Cases

* Fiscal reporting
* Year-over-year analysis

---

# DATE Function

## Purpose

Combine separate year/month/day values into a valid Excel date.

---

# Sample Dataset

| Year | Month | Day | Final Date |
| ---- | ----- | --- | ---------- |
| 2026 | 5     | 11  |            |

---

## Formula

```excel id="ryzjhm"
=DATE(A2,B2,C2)
```

---

## Result

```text id="6c4s0l"
11/05/2026
```

---

## Practical Use Cases

* Power Query preprocessing
* Building calendar tables
* Dynamic reporting

---

# NETWORKDAYS Function

## Purpose

Calculate working days between dates.

Excludes:

* Saturdays
* Sundays

---

# Sample Dataset

| Start Date | End Date   | Workdays |
| ---------- | ---------- | -------- |
| 01/05/2026 | 31/05/2026 |          |

---

## Formula

```excel id="h6kwmg"
=NETWORKDAYS(A2,B2)
```

---

## Example Result

```text id="c7ud3v"
21
```

---

# Why Useful?

Used for:

* Project planning
* SLA tracking
* Delivery schedules
* Workforce planning

---

# NETWORKDAYS with Holidays

# Sample Holiday Table

| Holidays   |
| ---------- |
| 25/12/2026 |
| 01/01/2027 |

---

## Formula

```excel id="n1hkh2"
=NETWORKDAYS(A2,B2,H2:H3)
```

---

## Result

Working days exclude:

* Weekends
* Holiday dates

---

# NETWORKDAYS.INTL

## Purpose

Custom weekend settings.

---

## Formula

```excel id="fq7hjh"
=NETWORKDAYS.INTL(A2,B2,1)
```

---

## Useful For

Countries with different weekends:

* Friday/Saturday
* Sunday only
* Custom schedules

---

# DATEDIF Function

## Purpose

Calculate duration between dates.

---

# Sample Dataset

| Joining Date | Current Date | Years Worked |
| ------------ | ------------ | ------------ |
| 01/05/2018   | 11/05/2026   |              |

---

## Formula

```excel id="c0nh6f"
=DATEDIF(A2,B2,"y")
```

---

## Result

```text id="c3xjca"
8
```

---

# Common DATEDIF Units

| Unit  | Meaning |
| ----- | ------- |
| `"d"` | Days    |
| `"m"` | Months  |
| `"y"` | Years   |

---

# Practical Workflow

# Employee Experience Tracking

### Raw Data

| Employee | Join Date |

### Calculated Fields

* Years worked
* Months worked
* Remaining contract duration

---

# Delivery Planning

### Calculate

* Working days
* Shipping duration
* Delivery delays

---

# Sales Reporting

### Extract

* Month
* Year
* Quarter

For:

* Pivot tables
* Dashboards
* Time intelligence

---

# Important Observations

# Dates Must Be Real Excel Dates

Correct:

```text id="6j8ojx"
08/30/23
```

Incorrect:

```text id="n2bzdb"
08.30.23
```

Incorrect formats may become text.

---

# TODAY & NOW Are Dynamic

These update automatically:

```excel id="97c4w8"
=TODAY()
=NOW()
```

---

# DATEDIF Is a Legacy Function

Important:

* Not shown in autocomplete
* Must type manually

---

# Common Mistakes

# Forgetting Parentheses

Wrong:

```excel id="c4x2k9"
=TODAY
```

Correct:

```excel id="vfqxyw"
=TODAY()
```

---

# Using Text Instead of Dates

Problem:

* Calculations fail
* Sorting breaks
* Pivot grouping fails

---

# Incorrect Regional Settings

US:

```text id="v94yq3"
MM/DD/YYYY
```

Europe:

```text id="n41dbe"
DD/MM/YYYY
```

Wrong locale can create incorrect dates.

---

# Productivity Tips

## Insert Current Date

```text id="vkp2uy"
Ctrl + ;
```

---

## Insert Current Time

```text id="gx0cgq"
Ctrl + Shift + ;
```

---

## AutoFill Date Series

Drag fill handle:

```text id="t4j2fi"
01/05/2026
02/05/2026
03/05/2026
```

---

# Analyst Use Cases

| Scenario                | Function        |
| ----------------------- | --------------- |
| Daily dashboard refresh | `TODAY()`       |
| Timestamping            | `NOW()`         |
| Monthly analysis        | `MONTH()`       |
| Year grouping           | `YEAR()`        |
| Workday planning        | `NETWORKDAYS()` |
| Employee tenure         | `DATEDIF()`     |

---

# PL-300 / Power BI Focus

Date functions are critical for:

* Date tables
* DAX Time Intelligence
* Rolling periods
* Year-over-year analysis
* Dynamic KPIs

---

# Quick Revision

| Task                | Formula               |
| ------------------- | --------------------- |
| Current Date        | `=TODAY()`            |
| Current Date + Time | `=NOW()`              |
| Extract Day         | `=DAY(A2)`            |
| Extract Month       | `=MONTH(A2)`          |
| Extract Year        | `=YEAR(A2)`           |
| Create Date         | `=DATE(Y,M,D)`        |
| Working Days        | `=NETWORKDAYS(A2,B2)` |
| Years Between Dates | `=DATEDIF(A2,B2,"y")` |

---

# Key Takeaway

Excel date functions help analysts:

* Track deadlines
* Build dynamic reports
* Analyze trends
* Calculate durations
* Plan projects efficiently

Understanding Excel date logic is foundational for:

* Excel Analytics
* Power BI
* SQL Reporting
* DAX Time Intelligence
