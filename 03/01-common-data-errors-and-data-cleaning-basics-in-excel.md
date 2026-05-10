# 01 — Common Data Errors in Excel & Data Cleaning Basics

## Core Idea

Raw data is often:

```text id="7m2q5v"
Messy, inconsistent, and unreliable
```

Before analysis, analysts must:

* Detect errors
* Clean data
* Standardize entries
* Remove duplicates
* Fix formatting issues

Bad data leads to:

```text id="4v8m1q"
Incorrect reports and poor business decisions
```

---

# Why Data Cleaning Matters

Poor-quality data can cause:

* Wrong KPIs
* Incorrect totals
* Broken charts
* Invalid Power BI visuals
* Failed lookups
* Misleading trends

---

# Business Scenario

Adventure Works analyst:

```text id="6q1m7v"
Jamie
```

Needs to clean:

* Customer data
* Sales records
* City information
* Revenue entries

Before:

```text id="2m8q4v"
Performing analysis
```

---

# Common Excel Data Errors

| Error Type                 | Impact               |
| -------------------------- | -------------------- |
| Misspellings               | Incorrect grouping   |
| Extra spaces               | Duplicate categories |
| Wrong data type            | Failed calculations  |
| Wrong column entries       | Misclassification    |
| Duplicate rows             | Inflated totals      |
| Bad date formats           | Broken time analysis |
| Inconsistent abbreviations | Reporting errors     |

---

# 1. Misspelled Entries

## Problem Example

### Incorrect Dataset

| Customer | City    | Sales |
| -------- | ------- | ----- |
| John     | Chicago | 1200  |
| Sara     | Chicgo  | 900   |
| Mike     | Chicago | 1500  |

---

# Problem

Excel treats:

```text id="9m4q2v"
Chicago
```

and:

```text id="1x7m5q"
Chicgo
```

As:

```text id="5r2m8q"
Different cities
```

---

# Impact on Analysis

Pivot tables and summaries may:

* Split totals
* Miss records
* Show incorrect KPIs

---

# Best Practice

Use:

* Data validation
* Dropdown lists
* Standard naming rules

---

# 2. Wrong Data Type

## Problem Example

### Incorrect Revenue Entries

| Sales |
| ----- |
| $1200 |
| $950  |
| $800  |

---

# Problem

Excel may treat:

```text id="7v2m4q"
$1200
```

As:

```text id="8m1q5v"
Text instead of numbers
```

---

# Impact

Text values:

* Cannot sum properly
* Break calculations
* Fail in charts and Power BI

---

# Correct Method

## Enter Number First

```text id="4m8q2v"
1200
```

Then apply:

```text id="2q7m5v"
Currency Formatting
```

---

# Correct Dataset

| Sales |
| ----- |
| 1200  |
| 950   |
| 800   |

Formatted as currency.

---

# 3. Extra Spaces

## Problem Example

| City     |
| -------- |
| Chicago  |
| Chicago␠ |

---

# Problem

Excel sees these as:

```text id="5x8m1q"
Two different values
```

---

# Impact

Can break:

* Pivot tables
* Filters
* Lookups
* Power BI relationships

---

# Solution

Use:

```excel id="7m2q5v"
=TRIM(A2)
```

To remove extra spaces.

---

# 4. Data in Wrong Column

## Incorrect Dataset

| City    | Sales   |
| ------- | ------- |
| Chicago | 1200    |
| Miami   | Chicago |

---

# Problem

Text appears in:

```text id="1m8q4v"
Numeric column
```

---

# Impact

Causes:

* Broken calculations
* Import errors
* Data model failures

---

# Best Practice

Always validate:

* Column purpose
* Data types
* Input consistency

---

# 5. Poor Spreadsheet Structure

## Bad Example

| Full Address              |
| ------------------------- |
| 123 North Street Miami FL |

---

# Problem

Hard to analyze by:

* City
* Region
* ZIP code

---

# Better Structure

| House No | Street       | City  | State |
| -------- | ------------ | ----- | ----- |
| 123      | North Street | Miami | FL    |

---

# Why This Matters

Structured columns improve:

* Filtering
* Sorting
* Power BI modeling
* Geographic analysis

---

# 6. Inconsistent Abbreviations

## Bad Example

| Title  |
| ------ |
| Mr     |
| Mister |
| mr     |
| MR     |

---

# Problem

Excel treats them as:

```text id="6v1m7q"
Different categories
```

---

# Impact

Creates:

* Duplicate groups
* Broken summaries
* Dirty dimensions

---

# Best Practice

Standardize entries:

```text id="8q5m2v"
Mr
Mrs
Dr
```

---

# 7. Incorrect Date Formats

## Wrong Example

| Date        |
| ----------- |
| 2024.05.01  |
| May\2024\01 |

---

# Problem

Excel may interpret them as:

```text id="4r7m2q"
Text
```

Instead of:

```text id="5m8q1v"
Real dates
```

---

# Correct Date Format

| Valid Dates |
| ----------- |
| 01/05/2024  |
| 01-05-2024  |

---

# Why Dates Matter

Correct dates enable:

* Time intelligence
* Monthly reporting
* Trend analysis
* Power BI date tables

---

# Important Excel Behavior

Excel stores dates internally as:

```text id="2m5q8v"
Numbers
```

---

# 8. Duplicate Records

## Problem Example

| Invoice | Sales |
| ------- | ----- |
| INV1001 | 1200  |
| INV1001 | 1200  |

---

# Impact

Duplicates cause:

* Inflated totals
* Incorrect KPIs
* Wrong dashboards
* Double counting

---

# Common Causes

| Cause             | Example           |
| ----------------- | ----------------- |
| Manual entry      | User typed twice  |
| Copy-paste errors | Duplicate imports |
| Merge mistakes    | Repeated records  |

---

# Best Practices to Avoid Duplicates

## Sort Data

Example:

```text id="9x2m4q"
Sort by date or invoice number
```

---

## Use Separate Columns

Avoid combining:

* City
* Region
* ZIP code

Into one field.

---

## Use Remove Duplicates Tool

### Navigation

```text id="7m4q1v"
Data → Remove Duplicates
```

---

# Sample Dirty Dataset

| Customer | City     | Sales | Date       |
| -------- | -------- | ----- | ---------- |
| John     | Chicago  | $1200 | 2024.01.01 |
| Sara     | Chicgo   | 900   | Jan\02\24  |
| Mike     | Chicago␠ | 1200  | 01/03/2024 |
| John     | Chicago  | $1200 | 2024.01.01 |

---

# Cleaned Dataset

| Customer | City    | Sales | Date       |
| -------- | ------- | ----- | ---------- |
| John     | Chicago | 1200  | 01/01/2024 |
| Sara     | Chicago | 900   | 01/02/2024 |
| Mike     | Chicago | 1200  | 01/03/2024 |

---

# Useful Excel Cleaning Functions

| Function   | Purpose                  |
| ---------- | ------------------------ |
| `TRIM()`   | Remove spaces            |
| `UPPER()`  | Standardize uppercase    |
| `LOWER()`  | Standardize lowercase    |
| `PROPER()` | Proper capitalization    |
| `CLEAN()`  | Remove hidden characters |

---

# Data Cleaning Workflow

## Recommended Process

1. Check duplicates
2. Fix spelling
3. Remove spaces
4. Standardize dates
5. Verify data types
6. Validate columns
7. Apply formatting
8. Audit totals

---

# Common Analyst Mistakes

## Ignoring Spaces

Invisible spaces can:

```text id="3v8m2q"
Break relationships and lookups
```

---

## Formatting Instead of Cleaning

Formatting:

```text id="6w2m8q"
Does not change actual data type
```

---

## Combining Multiple Data Elements

Avoid:

```text id="1q7m5v"
Full addresses in one column
```

---

## Trusting Imported Data

Always audit:

* Imports
* CSV files
* External sources

---

# Power BI / PL-300 Relevance

Dirty Excel data creates:

* Failed refreshes
* Broken relationships
* Incorrect DAX results
* Duplicate dimension values
* Time intelligence issues

---

# Analyst Best Practices

## Keep Data Atomic

One column:

```text id="8m1q5v"
One type of information
```

---

## Standardize Before Analysis

Never analyze:

```text id="5v2m7q"
Raw messy data directly
```

---

## Validate Input Early

Prevent errors before:

```text id="9m4q1v"
They reach reports
```

---

# Quick Revision

```text id="2x8m5q"
1. Clean data before analysis
2. Misspellings create duplicate categories
3. Extra spaces break grouping
4. Dates must be valid Excel dates
5. Currency symbols should come from formatting
6. Duplicate records inflate results
7. Structured columns improve analysis
8. Standardization is critical for reporting
```

---

# Mini Practice

## Remove Spaces

```excel id="7q4m1v"
=TRIM(A2)
```

---

## Standardize Proper Case

```excel id="4m7q2v"
=PROPER(A2)
```

---

## Convert To Uppercase

```excel id="6v1m5q"
=UPPER(A2)
```

---

# Most Important Takeaway

Reliable data analysis depends on:

* Clean datasets
* Consistent formatting
* Correct data types
* Standardized values
* Duplicate removal
* Structured worksheet design
