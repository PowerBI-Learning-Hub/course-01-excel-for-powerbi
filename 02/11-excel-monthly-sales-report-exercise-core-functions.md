# 11 — Excel Monthly Sales Report Exercise (SUM, COUNT, AVERAGE, MAX, MIN)

## Core Idea

This exercise combines the five core Excel functions:

```text id="8m4q2v"
SUM
COUNT
AVERAGE
MAX
MIN
```

To build a:

```text id="4v7m1q"
Monthly Sales Performance Report
```

These functions are heavily used in:

* Financial reporting
* KPI dashboards
* Sales analytics
* Power BI source sheets
* PL-300 reporting workflows

---

# Business Scenario

Adventure Works needs a monthly report for:

```text id="5w2m8q"
A2Mountain Bike Frames
```

Prepared by:

```text id="7m4q1v"
Lucas
```

For:

```text id="9x2m5q"
Monthly sales review meeting
```

---

# Sample Dataset — April Sales Report

| Date   | Units Sold | Unit Price | Daily Revenue |
| ------ | ---------- | ---------- | ------------- |
| 01-Apr | 12         | 1200       | 14400         |
| 02-Apr | 9          | 1200       | 10800         |
| 03-Apr | 15         | 1200       | 18000         |
| 04-Apr | 8          | 1200       | 9600          |
| 05-Apr | 20         | 1200       | 24000         |
| 06-Apr | 11         | 1200       | 13200         |
| 07-Apr | 18         | 1200       | 21600         |
| 08-Apr | 6          | 1200       | 7200          |
| 09-Apr | 14         | 1200       | 16800         |
| 10-Apr | 10         | 1200       | 12000         |

---

# Worksheet Structure

| Column | Purpose       |
| ------ | ------------- |
| B      | Sales Date    |
| C      | Units Sold    |
| D      | Unit Price    |
| E      | Daily Revenue |

---

# Report Output Area

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

Add all:

```text id="6w1m8q"
Daily Revenue values
```

---

# Formula in C35

```excel id="5x4m2q"
=SUM(E4:E33)
```

---

# What This Calculates

```text id="7q2m5v"
Total April sales revenue
```

---

# Analyst Observation

SUM is one of the most-used functions in:

* Financial reporting
* Dashboard totals
* KPI cards
* Power BI staging sheets

---

# Step 2 — Calculate Total Units Sold

## Goal

Count:

```text id="8m1q7v"
Total bikes sold
```

---

# Formula in C36

```excel id="3v8m5q"
=SUM(C4:C33)
```

---

# Important Observation

Even though instructions mention COUNT:

```text id="5r2m8q"
SUM is required for total units sold
```

Because:

* You need total quantity
* Not number of rows

---

# Step 3 — Find Lowest Sales Day

## Goal

Identify:

```text id="2m7q5v"
Lowest units sold
```

---

# Formula in C37

```excel id="9w4m1q"
=MIN(C4:C33)
```

---

# Example Result

```text id="7v2m5q"
6
```

---

# Step 4 — Record Date of Lowest Sales

## Example

| Lowest Sales | Date   |
| ------------ | ------ |
| 6            | 08-Apr |

---

# Enter Date in D37

```text id="1m8q4v"
08-Apr
```

---

# Analyst Observation

MIN helps identify:

* Weak sales periods
* Slow business days
* Seasonal dips
* Performance anomalies

---

# Step 5 — Find Highest Sales Day

## Goal

Identify:

```text id="6q1m7v"
Highest units sold
```

---

# Formula in C38

```excel id="5m8q2v"
=MAX(C4:C33)
```

---

# Example Result

```text id="9v2m4q"
20
```

---

# Step 6 — Record Date of Highest Sales

## Example

| Highest Sales | Date   |
| ------------- | ------ |
| 20            | 05-Apr |

---

# Enter Date in D38

```text id="8x5m2q"
05-Apr
```

---

# Why MAX Is Useful

Used in:

* Peak sales tracking
* KPI monitoring
* Inventory planning
* Forecasting

---

# Step 7 — Count Number of Days

## Goal

Count:

```text id="5w1m8q"
Number of sales dates
```

---

# Formula in C39

```excel id="2v7m4q"
=COUNT(B4:B33)
```

---

# Important Excel Concept

## Excel Stores Dates as Numbers

Even though dates appear as:

```text id="7m2q5v"
01-Apr
```

Excel internally stores them as:

```text id="4r8m1q"
Numeric values
```

So:

```excel id="0m5q7v"
COUNT
```

Can count dates successfully.

---

# Step 8 — Calculate Average Daily Revenue

## Goal

Calculate:

```text id="6x2m5q"
Average revenue per day
```

---

# Formula in C40

```excel id="3m8q1v"
=AVERAGE(E4:E33)
```

---

# Important Formatting Observation

Excel automatically applies:

```text id="7q4m2v"
Accounting Format
```

Because source revenue cells already use:

```text id="8v1m5q"
Currency formatting
```

---

# Function Summary Table

| Function | Formula            | Purpose               |
| -------- | ------------------ | --------------------- |
| SUM      | `=SUM(E4:E33)`     | Total Revenue         |
| SUM      | `=SUM(C4:C33)`     | Total Units Sold      |
| MIN      | `=MIN(C4:C33)`     | Lowest Units Sold     |
| MAX      | `=MAX(C4:C33)`     | Highest Units Sold    |
| COUNT    | `=COUNT(B4:B33)`   | Count Days            |
| AVERAGE  | `=AVERAGE(E4:E33)` | Average Daily Revenue |

---

# Important Excel Behaviors

## COUNT Counts Dates

Because Excel treats dates as:

```text id="4m7q2v"
Numbers
```

---

## MIN/MAX Ignore Text

They focus only on:

```text id="9q1m5v"
Numeric values
```

---

## AVERAGE Ignores Blank Cells

Useful for:

* Incomplete months
* Partial datasets
* Rolling reports

---

# Common Mistakes

## Using COUNT Instead of SUM

Wrong:

```excel id="6w2m8q"
=COUNT(C4:C33)
```

Correct:

```excel id="5m7q1v"
=SUM(C4:C33)
```

---

## Accepting Wrong AutoSum Range

Always verify:

```text id="3v8m4q"
Highlighted selection
```

---

## Forgetting Dates Are Numeric

COUNT works on dates because:

```text id="2m5q7v"
Dates are stored as numbers
```

---

## Using MAX on Revenue Instead of Units

Check:

```text id="1x8m5q"
Correct target column
```

---

# Analyst Best Practices

## Validate Auto-Selected Ranges

Excel guesses:

```text id="5v2m7q"
Not always correctly
```

---

## Keep Data Clean

Functions work best with:

* Consistent columns
* Proper formats
* No mixed data types

---

## Use Summary Sections

Keep KPI formulas grouped:

```text id="9m4q1v"
Bottom or top of worksheet
```

For:

* Dashboards
* Executive reviews
* Quick analysis

---

# Productivity Tips

## Learn Core Functions Deeply

Master:

```text id="4r7m2q"
SUM
AVERAGE
COUNT
MAX
MIN
```

These power most Excel reports.

---

## Use AutoFill for Repeated Reports

Build one formula:

```text id="6m2q8v"
Copy across/down quickly
```

---

# PL-300 / Data Analyst Focus

## Important Concepts

Understand:

* Function syntax
* AutoSum behavior
* Date handling
* Aggregation functions
* Dynamic recalculation
* KPI calculations

---

# Real-World Applications

Used in:

* Monthly reports
* Sales dashboards
* Financial summaries
* Executive KPI sheets
* Inventory reports
* Power BI source files

---

# Quick Revision

```text id="5x8m1q"
1. SUM totals numeric values
2. MIN finds lowest value
3. MAX finds highest value
4. COUNT counts numeric/date cells
5. AVERAGE calculates mean
6. Excel stores dates as numbers
7. Always verify suggested ranges
8. Functions update dynamically
```

---

# Mini Practice

## Practice 1 — Revenue Total

Create:

```excel id="7m2q4v"
=SUM(E4:E33)
```

---

## Practice 2 — Highest Sales Day

Create:

```excel id="9q5m1v"
=MAX(C4:C33)
```

---

## Practice 3 — Average Revenue

Create:

```excel id="4v8m2q"
=AVERAGE(E4:E33)
```

---

# Most Important Takeaway

Reliable Excel sales reporting depends on:

* Correct function selection
* Proper range selection
* Understanding date handling
* Accurate KPI calculations
* Clean worksheet structure
* Careful formula auditing
