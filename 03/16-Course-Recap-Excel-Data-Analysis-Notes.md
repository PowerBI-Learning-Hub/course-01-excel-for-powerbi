# 16-Course-Recap-Excel-Data-Analysis-Notes.md

# Excel Data Analysis — Final Course Recap

## Overview

This course covered:

- Excel basics
- Data entry and formatting
- Formulas and functions
- Text cleaning
- Date calculations
- Logical functions
- Preparing data for analysis

---

# Week 1 — Excel Fundamentals

# Sample Dataset

| Employee | Department | Salary | City |
|---|---|---|---|
| Ali | Sales | 4500 | Miami |
| Sara | HR | 5200 | Seattle |
| John | IT | 6100 | Chicago |

---

# Key Concepts

## Excel Interface

Important areas:

- Ribbon
- Formula Bar
- Worksheet
- Name Box
- Tabs

---

# Data Formatting

## Common Formatting

| Format | Example |
|---|---|
| Currency | $4,500 |
| Percentage | 10% |
| Date | 05/12/2026 |

---

# Sorting & Filtering

## Example

### Sort Salary Highest to Lowest

```text
6100
5200
4500
```

### Filter Only Sales Department

| Employee | Department |
|---|---|
| Ali | Sales |

---

# Week 2 — Formulas & Functions

# Formula Basics

## Sample Dataset

| Product | Qty | Price |
|---|---|---|
| Bike | 5 | 500 |
| Helmet | 10 | 80 |

---

# Multiplication Formula

```excel
=B2*C2
```

Result:

```text
2500
```

---

# Core Functions

| Function | Formula |
|---|---|
| SUM | =SUM(C2:C5) |
| AVERAGE | =AVERAGE(C2:C5) |
| COUNT | =COUNT(C2:C5) |
| MAX | =MAX(C2:C5) |
| MIN | =MIN(C2:C5) |

---

# Relative vs Absolute Reference

## Relative

```excel
=A2*B2
```

Changes when copied.

---

## Absolute

```excel
=$A$2*B2
```

Reference stays fixed.

---

# Percentage Formula

```excel
=Profit/Sales
```

Example:

```excel
=200/1000
```

Result:

```text
20%
```

---

# Week 3 — Preparing Data for Analysis

# Common Data Problems

## Sample Dirty Dataset

| Customer Name |
|---|
|  john smith |
| SARA KHAN |
| michaelBrown |

---

# TRIM Function

```excel
=TRIM(A2)
```

Removes extra spaces.

---

# PROPER Function

```excel
=PROPER(A2)
```

Result:

```text
John Smith
```

---

# UPPER / LOWER

```excel
=UPPER(A2)
=LOWER(A2)
```

---

# LEFT / RIGHT / MID

## Sample Data

| Full Code |
|---|
| USA-1001 |

### LEFT

```excel
=LEFT(A2,3)
```

Result:

```text
USA
```

---

### RIGHT

```excel
=RIGHT(A2,4)
```

Result:

```text
1001
```

---

### MID

```excel
=MID(A2,5,2)
```

Result:

```text
10
```

---

# CONCAT Function

## Dataset

| First Name | Last Name |
|---|---|
| John | Smith |

### Formula

```excel
=CONCAT(A2," ",B2)
```

Result:

```text
John Smith
```

---

# Date Functions

# Sample Dataset

| Start Date | End Date |
|---|---|
| 05/01/2026 | 05/31/2026 |

---

# TODAY Function

```excel
=TODAY()
```

Returns current date.

---

# NOW Function

```excel
=NOW()
```

Returns current date and time.

---

# NETWORKDAYS

```excel
=NETWORKDAYS(A2,B2)
```

Returns working days excluding weekends.

---

# YEAR / MONTH / DAY

```excel
=YEAR(A2)
=MONTH(A2)
=DAY(A2)
```

---

# Logical Functions

# IF Function

## Sample Dataset

| Sales |
|---|
| 12000 |
| 8000 |

### Formula

```excel
=IF(A2>10000,"Bonus","No Bonus")
```

---

# IFS Function

```excel
=IFS(A2>=90,"A",A2>=80,"B",TRUE,"C")
```

---

# AND Function

```excel
=AND(A2>50,B2>50)
```

All conditions must be TRUE.

---

# OR Function

```excel
=OR(A2>50,B2>50)
```

Only one condition must be TRUE.

---

# SUMIF / COUNTIF / AVERAGEIF

# Sample Dataset

| City | Sales |
|---|---|
| Seattle | 5000 |
| Miami | 7000 |
| Seattle | 3000 |

---

# SUMIF

```excel
=SUMIF(A2:A4,"Seattle",B2:B4)
```

Result:

```text
8000
```

---

# COUNTIF

```excel
=COUNTIF(A2:A4,"Seattle")
```

Result:

```text
2
```

---

# AVERAGEIF

```excel
=AVERAGEIF(A2:A4,"Seattle",B2:B4)
```

Result:

```text
4000
```

---

# Common Analyst Workflow

```text
Import Data
    ↓
Clean Data
    ↓
Standardize Text
    ↓
Create Calculations
    ↓
Apply Logical Functions
    ↓
Generate Reports
```

---

# Productivity Tips

- Use Autofill for faster formulas
- Freeze Panes for large datasets
- Use filters before analysis
- Keep data types consistent
- Use absolute references in lookup tables

---

# PL-300 Focus

Important concepts:

- Data cleaning
- Data transformation
- Conditional calculations
- Date intelligence basics
- Data consistency
- Report preparation

---

# Quick Revision

| Topic | Main Learning |
|---|---|
| Formatting | Improve readability |
| Functions | Automate calculations |
| Text Functions | Clean messy data |
| Date Functions | Timeline analysis |
| IF Functions | Conditional logic |
| SUMIF | Conditional totals |

---

# Final Takeaway

You can now:

- Build Excel reports
- Clean datasets
- Create formulas
- Use logical calculations
- Prepare data for analysis
- Build strong Excel foundations for Power BI
