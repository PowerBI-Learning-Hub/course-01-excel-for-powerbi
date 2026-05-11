# 09-Exemplar-Date-and-Time-Functions.md

# Exemplar: Calculating Working Days Remaining

## Core Objective

Use Excel date functions to:

* Calculate remaining calendar days
* Calculate working days only
* Exclude weekends and holidays
* Extract month and year from dates
* Build reusable formulas with Autofill

---

# Sample Dataset

## USA Launch Dates Worksheet

| Campaign         | Start Date | Deadline Date | Days Left | Workdays Left | Month | Year |
| ---------------- | ---------- | ------------- | --------- | ------------- | ----- | ---- |
| Bike Launch      | 04/01/2023 | 07/02/2023    |           |               |       |      |
| Summer Promo     | 04/15/2023 | 08/10/2023    |           |               |       |      |
| Winter Campaign  | 05/01/2023 | 09/15/2023    |           |               |       |      |
| Accessories Push | 05/10/2023 | 10/01/2023    |           |               |       |      |
| Holiday Sales    | 06/01/2023 | 11/20/2023    |           |               |       |      |

---

# Federal Holiday Table

## Cells J5:J26

| Holiday Dates |
| ------------- |
| 05/29/2023    |
| 07/04/2023    |
| 09/04/2023    |
| 11/23/2023    |
| 12/25/2023    |

---

# Step 1 — Dynamic Current Date

## Cell B1

### Formula

```excel id="7e2lwl"
=TODAY()
```

---

# Purpose

* Displays current system date
* Updates automatically every 24 hours

---

# Important Observation

TODAY function:

* Requires parentheses
* No arguments inside brackets

Correct:

```excel id="h5myd0"
=TODAY()
```

Wrong:

```excel id="bt0i95"
=TODAY
```

---

# Step 2 — Convert to Static Date

Replace formula in B1 with:

```text id="n3x5qy"
05/09/23
```

---

# Why Static Date Was Used

Exercise uses fixed date so everyone gets same results.

Real projects normally keep:

```excel id="z0oqcx"
=TODAY()
```

---

# Step 3 — Calculate Calendar Days Remaining

## Cell E5

### Formula

```excel id="ktq0ub"
=D5-$B$1
```

---

# Formula Logic

| Part   | Meaning       |
| ------ | ------------- |
| `D5`   | Deadline date |
| `$B$1` | Current date  |

---

# Why Dollar Signs Matter

Without dollar signs:

```excel id="3n8r2g"
=D5-B1
```

Autofill changes reference incorrectly.

Correct:

```excel id="dgqqms"
=D5-$B$1
```

---

# Example Result

| Current Date | Deadline Date | Result |
| ------------ | ------------- | ------ |
| 05/09/23     | 07/02/23      | 54     |

---

# Step 4 — Calculate Working Days Only

## Cell F5

### Formula

```excel id="fe2szy"
=NETWORKDAYS($B$1,D5,$J$5:$J$26)
```

---

# Formula Breakdown

| Formula Part | Purpose       |
| ------------ | ------------- |
| `$B$1`       | Start date    |
| `D5`         | Deadline      |
| `$J$5:$J$26` | Holiday range |

---

# What NETWORKDAYS Excludes

* Saturdays
* Sundays
* Federal holidays

---

# Example Result

| Calendar Days | Weekends Removed | Holidays Removed | Workdays |
| ------------- | ---------------- | ---------------- | -------- |
| 54            | Yes              | Yes              | 37       |

---

# Important Analyst Observation

Excel ignores holiday dates already in the past.

Safe to include entire holiday range:

```excel id="t8kkwb"
$J$5:$J$26
```

---

# Step 5 — Extract Month

## Cell G5

### Formula

```excel id="x8ezvt"
=MONTH(D5)
```

---

# Example

| Deadline Date | Result |
| ------------- | ------ |
| 07/02/2023    | 7      |

---

# Step 6 — Extract Year

## Cell H5

### Formula

```excel id="qj9l9t"
=YEAR(D5)
```

---

# Example

| Deadline Date | Result |
| ------------- | ------ |
| 07/02/2023    | 2023   |

---

# Step 7 — Copy Formulas Down

## Fast Autofill Method

### Steps

1. Select E5:H5
2. Move cursor to bottom-right corner
3. Black cross appears
4. Double-click

Excel copies formulas automatically to row 9.

---

# Final Output Example

| Campaign        | Days Left | Workdays Left | Month | Year |
| --------------- | --------- | ------------- | ----- | ---- |
| Bike Launch     | 54        | 37            | 7     | 2023 |
| Summer Promo    | 93        | 65            | 8     | 2023 |
| Winter Campaign | 129       | 91            | 9     | 2023 |

---

# Important Excel Concepts

# Dates Are Serial Numbers

Excel stores dates as numbers internally.

Example:

| Date       | Serial Number |
| ---------- | ------------- |
| 01/01/1900 | 1             |
| 07/02/2023 | 45109         |

This allows:

```excel id="90n5gi"
=D5-B1
```

---

# Relative vs Absolute References

## Relative Reference

```excel id="7mq98m"
B1
```

Changes during Autofill.

---

## Absolute Reference

```excel id="7jlwm5"
$B$1
```

Remains fixed.

---

# Common Mistakes

## Forgetting Absolute References

Wrong:

```excel id="9ecw6d"
=NETWORKDAYS(B1,D5,J5:J26)
```

Correct:

```excel id="yn10ki"
=NETWORKDAYS($B$1,D5,$J$5:$J$26)
```

---

## Wrong Date Format

### USA Format

```text id="yl1tt3"
MM/DD/YYYY
```

### European Format

```text id="ay2v0q"
DD/MM/YYYY
```

Wrong regional settings can produce incorrect results.

---

## Missing Holiday Range

Without holidays:

* Workdays count becomes inaccurate
* Project timelines become unreliable

---

# Productivity Tips

## Fast Absolute References

Press:

```text id="n0of7v"
F4
```

After selecting cell reference.

---

## Autofill Shortcut

Double-click fill handle instead of dragging manually.

---

## Insert Current Date Shortcut

```text id="lq6i0y"
Ctrl + ;
```

---

# Practical Business Uses

## Project Management

* Timeline tracking
* Deadline planning
* Resource scheduling

---

## Marketing Teams

* Campaign launch countdown
* Regional rollout tracking
* Milestone planning

---

## Operations

* Delivery schedules
* Manufacturing timelines
* Staff planning

---

# PL-300 / Analyst Focus

Understand:

* Date serial numbers
* TODAY function
* NETWORKDAYS logic
* Holiday exclusions
* Relative vs absolute references

These concepts are used heavily in:

* Power BI date tables
* KPI tracking
* SLA calculations
* Project dashboards
* Time intelligence calculations

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

Date functions help analysts:

* Track deadlines dynamically
* Calculate working timelines
* Build automated schedules
* Improve project planning
* Prepare accurate business reports
