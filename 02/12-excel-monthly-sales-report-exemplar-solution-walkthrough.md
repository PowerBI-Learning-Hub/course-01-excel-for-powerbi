# 12 — Excel Monthly Sales Report Exemplar Solution Walkthrough

## Core Idea

This exercise demonstrates how analysts use Excel’s:

```text id="6w2m8q"
SUM
AVERAGE
COUNT
COUNTA
MAX
MIN
```

Functions to create:

* Sales summaries
* KPI reports
* Monthly dashboards
* Financial reviews

These are foundational skills for:

* Excel analysts
* Power BI analysts
* PL-300 preparation
* Reporting automation

---

# Business Scenario

Adventure Works needs a completed:

```text id="9m4q1v"
Monthly Sales Report
```

For:

```text id="5x7m2q"
A2 Mountain Bike Frames
```

Prepared for:

```text id="2v8m5q"
Lucas
```

To present during:

```text id="7q1m4v"
Monthly sales review meeting
```

---

# Sample Dataset — April Sales

| Date      | Units Sold | Unit Price | Daily Revenue |
| --------- | ---------- | ---------- | ------------- |
| 01-Apr-23 | 3250       | 200        | 650000        |
| 02-Apr-23 | 2980       | 200        | 596000        |
| 03-Apr-23 | 3560       | 200        | 712000        |
| 04-Apr-23 | 4100       | 200        | 820000        |
| 05-Apr-23 | 3890       | 200        | 778000        |
| 06-Apr-23 | 3440       | 200        | 688000        |
| 07-Apr-23 | 4210       | 200        | 842000        |
| 08-Apr-23 | 3760       | 200        | 752000        |
| 09-Apr-23 | 4025       | 200        | 805000        |
| 10-Apr-23 | 3650       | 200        | 730000        |

---

# Worksheet Output Area

| Cell | Purpose               |
| ---- | --------------------- |
| C35  | Total Revenue         |
| C36  | Total Units Sold      |
| C37  | Lowest Units Sold     |
| D37  | Date of Lowest Sales  |
| C38  | Highest Units Sold    |
| D38  | Date of Highest Sales |
| C39  | Number of Days        |
| C40  | Average Daily Revenue |

---

# Step 1 — Calculate Total Revenue

## Goal

Calculate:

```text id="4r8m1q"
Total April revenue
```

---

# Formula in C35

```excel id="8m2q5v"
=SUM(E4:E33)
```

---

# What This Does

Adds all:

```text id="1x7m4q"
Daily Revenue values
```

---

# Example Result

```text id="3v9m2q"
$23,059,600
```

---

# Important Observation

If using:

* AutoSum
* Insert Function

Excel may incorrectly suggest:

```text id="6m1q8v"
C4:C33
```

Because those cells are closer to:

```text id="7w4m2q"
C35
```

Always manually verify ranges.

---

# Automatic Accounting Format

Excel automatically applied:

```text id="0m7q5v"
Accounting Format
```

Because source revenue cells already used:

```text id="4v2m8q"
Currency formatting
```

---

# Step 2 — Calculate Total Units Sold

## Goal

Calculate:

```text id="5q1m7v"
Total frames sold
```

---

# Formula in C36

```excel id="2x8m4q"
=SUM(C4:C33)
```

---

# Example Result

```text id="8m5q1v"
115,298
```

---

# Important Observation

Many users mistakenly use:

```excel id="6r2m7q"
=COUNT(C4:C33)
```

But:

```text id="3v8m2q"
COUNT only counts rows
```

Correct requirement:

```text id="7m4q1v"
Total quantity sold
```

Requires:

```excel id="5x9m2q"
SUM
```

---

# Step 3 — Find Lowest Sales Day

## Goal

Identify:

```text id="2m7q4v"
Lowest units sold
```

---

# Formula in C37

```excel id="9v1m5q"
=MIN(C4:C33)
```

---

# Example Result

```text id="6m2q8v"
2,560
```

---

# Corresponding Date

Enter manually in:

```text id="5w7m1q"
D37
```

Example:

```text id="1q9m4v"
30-Apr-23
```

---

# Why MIN Is Useful

Used for:

* Weak sales analysis
* Seasonal tracking
* Risk monitoring
* Performance reviews

---

# Step 4 — Find Highest Sales Day

## Goal

Identify:

```text id="8m3q1v"
Highest units sold
```

---

# Formula in C38

```excel id="7v2m5q"
=MAX(C4:C33)
```

---

# Example Result

```text id="5r8m2q"
4,921
```

---

# Corresponding Date

Enter manually in:

```text id="3x7m5q"
D38
```

Example:

```text id="2v9m1q"
16-Apr-23
```

---

# Why MAX Is Useful

Used in:

* Peak performance tracking
* KPI dashboards
* Inventory forecasting
* Sales monitoring

---

# Step 5 — Count Number of Days

## Goal

Calculate:

```text id="8q2m4v"
Number of dates in April
```

---

# Formula Option 1

```excel id="6w7m1q"
=COUNT(B4:B33)
```

---

# Formula Option 2

```excel id="1m8q5v"
=COUNTA(B4:B33)
```

---

# Why Both Work

Because Excel stores dates as:

```text id="4r7m2q"
Numeric values
```

Even though dates display as:

```text id="7m1q8v"
01-Apr-23
```

Internally:

```text id="5x2m4q"
Dates are numbers
```

---

# Example Result

```text id="9v4m1q"
30
```

---

# COUNT vs COUNTA

| Function | Counts             |
| -------- | ------------------ |
| COUNT    | Numeric cells only |
| COUNTA   | Any non-empty cell |

---

# Analyst Observation

COUNT works because:

```text id="8m5q2v"
Dates are numeric
```

COUNTA works because:

```text id="3v1m7q"
Dates are non-empty cells
```

---

# Step 6 — Calculate Average Daily Revenue

## Goal

Calculate:

```text id="2m8q5v"
Average revenue per day
```

---

# Formula in C40

```excel id="7q4m1v"
=AVERAGE(E4:E33)
```

---

# Example Result

```text id="5w2m8q"
$768,653
```

---

# Important Observation

If using:

* Insert Function
* AutoSum

Excel may select:

```text id="4v7m2q"
Wrong range
```

Always manually confirm:

```text id="6m1q5v"
E4:E33
```

---

# Automatic Formatting

AVERAGE result automatically used:

```text id="9q2m4v"
Accounting Format
```

Because source values already used:

```text id="8m5q1v"
Currency formatting
```

---

# Function Summary Table

| Function | Formula            | Purpose               |
| -------- | ------------------ | --------------------- |
| SUM      | `=SUM(E4:E33)`     | Total Revenue         |
| SUM      | `=SUM(C4:C33)`     | Total Units Sold      |
| MIN      | `=MIN(C4:C33)`     | Lowest Sales          |
| MAX      | `=MAX(C4:C33)`     | Highest Sales         |
| COUNT    | `=COUNT(B4:B33)`   | Count Days            |
| COUNTA   | `=COUNTA(B4:B33)`  | Alternative Day Count |
| AVERAGE  | `=AVERAGE(E4:E33)` | Average Revenue       |

---

# Important Excel Behaviors

## Dates Are Numeric

Excel internally stores dates as:

```text id="7x2m5q"
Serial numbers
```

---

## AutoSum Guesses Nearby Ranges

Useful:

```text id="3m8q1v"
But not always accurate
```

---

## Formatting Propagates Automatically

Excel often copies formatting from:

```text id="1v7m4q"
Source data
```

---

# Common Mistakes

## Using COUNT Instead of SUM

Wrong:

```excel id="8m2q5v"
=COUNT(C4:C33)
```

Correct:

```excel id="5r7m1q"
=SUM(C4:C33)
```

---

## Accepting Incorrect AutoSum Range

Always inspect:

```text id="4x9m2q"
Highlighted cells
```

---

## Confusing COUNT and COUNTA

Remember:

```text id="2m5q8v"
COUNT = numbers only
COUNTA = any content
```

---

## Using Wrong Target Column

Verify formulas use:

```text id="6v1m7q"
Correct dataset column
```

---

# Productivity Tips

## Learn Core Functions Deeply

Master:

```text id="9q4m2v"
SUM
AVERAGE
COUNT
COUNTA
MAX
MIN
```

These functions power most Excel reports.

---

## Use Summary KPI Sections

Group formulas together:

```text id="8m1q5v"
Bottom or top of worksheet
```

For:

* Dashboards
* Executive reporting
* Fast analysis

---

## Validate Auto-Generated Suggestions

Excel suggestions are:

```text id="3v7m2q"
Helpful but imperfect
```

---

# PL-300 / Data Analyst Focus

## Important Skills

Understand:

* Aggregation functions
* Dynamic calculations
* Date handling
* AutoSum behavior
* KPI reporting
* Formula auditing

---

# Real-World Applications

Used in:

* Sales dashboards
* Financial reporting
* KPI scorecards
* Executive summaries
* Forecast tracking
* Power BI staging sheets

---

# Quick Revision

```text id="6w2m8q"
1. SUM totals values
2. MIN finds smallest value
3. MAX finds largest value
4. COUNT counts numeric/date cells
5. COUNTA counts all non-empty cells
6. AVERAGE calculates mean
7. Excel stores dates as numbers
8. Always verify AutoSum ranges
```

---

# Mini Practice

## Practice 1 — Revenue Total

Create:

```excel id="5x7m1q"
=SUM(E4:E33)
```

---

## Practice 2 — Highest Sales Day

Create:

```excel id="9m4q2v"
=MAX(C4:C33)
```

---

## Practice 3 — Average Revenue

Create:

```excel id="3v8m5q"
=AVERAGE(E4:E33)
```

---

# Most Important Takeaway

Reliable Excel sales reports depend on:

* Correct function selection
* Proper range validation
* Understanding Excel date behavior
* Accurate KPI calculations
* Careful formula auditing
* Clean worksheet structure
