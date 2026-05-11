# 08-Exercise-Date-and-Time-Functions.md

# Exercise: Date & Time Functions in Excel

## Core Objective

Use Excel date functions to:

* Track project deadlines
* Calculate remaining days
* Calculate working days only
* Extract month and year from dates
* Create reusable formulas with Autofill

---

# Sample Dataset

## USA Launch Dates Worksheet

| Campaign ID | Campaign Name    | Start Date | Deadline Date | Days Left | Workdays Left | Launch Month | Launch Year |
| ----------- | ---------------- | ---------- | ------------- | --------- | ------------- | ------------ | ----------- |
| CMP-101     | Bike Sale USA    | 04/01/2023 | 07/11/2023    |           |               |              |             |
| CMP-102     | Summer Promo     | 04/15/2023 | 08/25/2023    |           |               |              |             |
| CMP-103     | Accessories Push | 05/01/2023 | 09/10/2023    |           |               |              |             |
| CMP-104     | Winter Campaign  | 05/10/2023 | 10/20/2023    |           |               |              |             |
| CMP-105     | Holiday Launch   | 06/01/2023 | 11/15/2023    |           |               |              |             |

---

# Federal Holiday Dataset

## Cells J5:J12

| Holiday Dates |
| ------------- |
| 05/29/2023    |
| 07/04/2023    |
| 09/04/2023    |
| 11/23/2023    |
| 12/25/2023    |
| 01/01/2024    |
| 01/15/2024    |
| 02/19/2024    |

---

# Step-by-Step Calculations

---

# 1. Dynamic Current Date

## Cell B1

### Formula

```excel
=TODAY()
```

## Purpose

* Always shows current system date
* Updates automatically every day

---

# 2. Replace Dynamic Date with Static Date

## Cell B1

Replace formula with:

```excel
05/09/23
```

## Why?

* Keeps exercise results consistent
* Easier to compare answers

---

# 3. Calculate Calendar Days Remaining

## Cell E5

### Formula

```excel
=D5-$B$1
```

## Purpose

* Calculates total calendar days left
* Uses subtraction between dates

## Why `$B$1`?

* Keeps current date fixed during Autofill

---

# Example Result

| Deadline Date | Current Date | Result |
| ------------- | ------------ | ------ |
| 07/11/2023    | 05/09/2023   | 63     |

---

# 4. Calculate Working Days Remaining

## Cell F5

### Formula

```excel
=NETWORKDAYS($B$1,D5,$J$5:$J$12)
```

---

# Formula Breakdown

| Part         | Meaning       |
| ------------ | ------------- |
| `$B$1`       | Current date  |
| `D5`         | Deadline date |
| `$J$5:$J$12` | Holiday list  |

---

# What NETWORKDAYS Does

* Excludes Saturdays
* Excludes Sundays
* Excludes listed holidays

---

# Example Result

| Calendar Days | Weekends Removed | Holidays Removed | Workdays |
| ------------- | ---------------- | ---------------- | -------- |
| 63            | Yes              | Yes              | 43       |

---

# 5. Extract Launch Month

## Cell G5

### Formula

```excel
=MONTH(D5)
```

## Example

| Deadline Date | Result |
| ------------- | ------ |
| 07/11/2023    | 7      |

---

# 6. Extract Launch Year

## Cell H5

### Formula

```excel
=YEAR(D5)
```

## Example

| Deadline Date | Result |
| ------------- | ------ |
| 07/11/2023    | 2023   |

---

# 7. Copy Formulas Down

## Autofill Method

### Steps

1. Select E5:H5
2. Hover bottom-right corner
3. Black cross appears
4. Double-click

Excel copies formulas down to row 9 automatically.

---

# Final Output Example

| Campaign         | Days Left | Workdays Left | Month | Year |
| ---------------- | --------- | ------------- | ----- | ---- |
| Bike Sale USA    | 63        | 43            | 7     | 2023 |
| Summer Promo     | 108       | 76            | 8     | 2023 |
| Accessories Push | 124       | 88            | 9     | 2023 |

---

# Important Excel Concepts

## Dates Are Numbers

Excel stores dates as serial numbers.

Example:

| Date       | Serial Number |
| ---------- | ------------- |
| 01/01/1900 | 1             |
| 07/11/2023 | 45118         |

This allows subtraction calculations.

---

# Absolute References

## Example

```excel
$B$1
```

## Why Important?

Without dollar signs:

```excel
=D5-B1
```

Autofill changes reference incorrectly:

```excel
=D6-B2
```

This breaks calculations.

---

# Common Mistakes

## Wrong Date Format

### USA Format

```text
MM/DD/YYYY
```

### European Format

```text
DD/MM/YYYY
```

Incorrect format can generate wrong calculations.

---

## Forgetting Dollar Signs

Wrong:

```excel
=NETWORKDAYS(B1,D5,J5:J12)
```

Correct:

```excel
=NETWORKDAYS($B$1,D5,$J$5:$J$12)
```

---

## Missing Holiday Range

Without holiday argument:

* Public holidays counted as working days
* Incorrect project timeline

---

# Practical Business Uses

## Project Management

* Deadline tracking
* Resource planning
* Timeline monitoring

---

## Marketing Campaigns

* Launch countdowns
* Country rollout schedules
* Regional planning

---

## Operations

* Delivery scheduling
* Production timelines
* Staff planning

---

# Productivity Tips

## Shortcut for Absolute References

Press:

```text
F4
```

After selecting cell reference.

---

## Autofill Shortcut

Double-click fill handle instead of dragging manually.

---

## Fast Date Entry

Press:

```text
Ctrl + ;
```

Insert current date quickly.

---

# PL-300 / Analyst Focus

Understand:

* Date serial numbers
* Dynamic vs static dates
* NETWORKDAYS logic
* Absolute references
* Date extraction functions

These concepts are heavily used in:

* Power BI date tables
* DAX calculations
* KPI reporting
* Project tracking dashboards

---

# Quick Revision

| Function        | Purpose           |
| --------------- | ----------------- |
| `TODAY()`       | Current date      |
| `NETWORKDAYS()` | Working days only |
| `MONTH()`       | Extract month     |
| `YEAR()`        | Extract year      |

---

# Key Takeaway

Excel date functions help analysts:

* Track deadlines
* Calculate working time
* Build dynamic schedules
* Prepare time-based analysis
* Automate project tracking
