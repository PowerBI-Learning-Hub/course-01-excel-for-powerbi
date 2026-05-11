# SUMIF, AVERAGEIF, and COUNTIF Functions in Excel

## Core Idea

* These functions perform calculations based on conditions.
* Useful for:

  * Sales analysis
  * KPI tracking
  * Regional reporting
  * Dashboard metrics
* Commonly used in:

  * Excel reports
  * Power BI source files
  * Business summaries

---

# Sample Dataset — Regional Sales Report

| Order ID | City    | Sales Amount |
| -------- | ------- | -----------: |
| 1001     | Seattle |         4200 |
| 1002     | Chicago |         3800 |
| 1003     | Seattle |         5100 |
| 1004     | Miami   |         6200 |
| 1005     | Seattle |         5800 |
| 1006     | Dallas  |         4500 |

---

# Understanding SUMIF

## Purpose

Adds values only when a condition is met.

---

# SUMIF Syntax

```excel id="5j4x8s"
=SUMIF(range,criteria,sum_range)
```

---

# SUMIF Example

## Business Requirement

Calculate total sales for Seattle only.

## Formula

```excel id="1z6m3v"
=SUMIF(B2:B7,"Seattle",C2:C7)
```

---

# Formula Breakdown

| Argument    | Meaning          |
| ----------- | ---------------- |
| `B2:B7`     | Check city names |
| `"Seattle"` | Condition        |
| `C2:C7`     | Values to total  |

---

# SUMIF Result

| City    | Total Sales |
| ------- | ----------: |
| Seattle |       15100 |

---

# Understanding AVERAGEIF

## Purpose

Calculates average based on a condition.

---

# AVERAGEIF Syntax

```excel id="8c2t4n"
=AVERAGEIF(range,criteria,average_range)
```

---

# AVERAGEIF Example

## Business Requirement

Find average sales for Seattle.

## Formula

```excel id="0q7w2p"
=AVERAGEIF(B2:B7,"Seattle",C2:C7)
```

---

# AVERAGEIF Result

| City    | Average Sales |
| ------- | ------------: |
| Seattle |          5033 |

---

# Understanding COUNTIF

## Purpose

Counts how many times a condition appears.

---

# COUNTIF Syntax

```excel id="7m1d6x"
=COUNTIF(range,criteria)
```

---

# COUNTIF Example

## Business Requirement

Count number of Seattle orders.

## Formula

```excel id="2k9r4f"
=COUNTIF(B2:B7,"Seattle")
```

---

# COUNTIF Result

| City    | Occurrences |
| ------- | ----------: |
| Seattle |           3 |

---

# Practical Workflow

## Step 1 — Organize Dataset

Keep:

* Category column
* Numeric column

separate.

---

## Step 2 — Define Condition

Examples:

* City
* Product
* Department
* Salesperson

---

## Step 3 — Write Formula

Choose:

* SUMIF
* AVERAGEIF
* COUNTIF

based on requirement.

---

## Step 4 — Validate Results

Cross-check:

* Filter manually
* Compare totals

---

# Important Observations

## Text Criteria Need Quotes

Correct:

```excel id="4v6s8t"
"Seattle"
```

Wrong:

```excel id="9x2w5m"
Seattle
```

---

## Functions Are Not Case Sensitive

These work the same:

```excel id="3q5n7r"
"Seattle"
```

```excel id="1b8c2z"
"SEATTLE"
```

---

## COUNTIF Only Counts Matches

Does not total values.

---

# Using Cell References Instead of Typed Text

Better approach for dashboards:

| J1      |
| ------- |
| Seattle |

Formula:

```excel id="6r3v8n"
=SUMIF(B2:B7,J1,C2:C7)
```

Advantages:

* Dynamic reporting
* Easier filtering
* Better for slicers and dashboards

---

# Common Mistakes

## Wrong Range Sizes

Wrong:

```excel id="0m4p7q"
=SUMIF(B2:B7,"Seattle",C2:C10)
```

Ranges should align properly.

---

## Missing Quotes Around Text

Wrong:

```excel id="8k1x5c"
=COUNTIF(B2:B7,Seattle)
```

Correct:

```excel id="9t6v2m"
=COUNTIF(B2:B7,"Seattle")
```

---

## Using Text in Numeric Columns

Sales column must contain numbers.

---

# Productivity Tips

## Use Named Ranges

Makes formulas cleaner.

Example:

```excel id="2w9n4v"
=SUMIF(City,"Seattle",Sales)
```

---

## Combine with Drop-Down Lists

Useful for interactive reports.

---

## Use Excel Tables

Structured references improve readability.

---

# Analyst Use Cases

## Sales Analysis

* Revenue by city
* Average order value
* Order count

## HR

* Employees by department
* Average salaries

## Finance

* Expenses by category
* Budget tracking

## Operations

* Defect counts
* Regional performance

---

# Quick Revision

## SUMIF

```excel id="1p5m8z"
=SUMIF(range,criteria,sum_range)
```

Adds values meeting condition.

---

## AVERAGEIF

```excel id="7d2q6w"
=AVERAGEIF(range,criteria,average_range)
```

Calculates conditional average.

---

## COUNTIF

```excel id="5y8n3v"
=COUNTIF(range,criteria)
```

Counts matching records.

---

# Best Practice

* Keep datasets clean and structured.
* Use cell references instead of hardcoded text.
* Validate ranges before copying formulas.
* Use IF-based functions for dynamic business analysis.
