# 02 — Excel Text Functions for Data Cleaning & Standardization

## Core Idea

Text data in Excel is often:

* inconsistent
* messy
* incorrectly formatted

This creates problems in:

* filters
* searches
* PivotTables
* Power BI
* formulas
* reporting

Excel text functions help:

```text id="7m2q5v"
Clean, split, standardize, and combine text data
```

---

# Why Text Cleaning Matters

Dirty text data can cause:

* duplicate categories
* failed lookups
* broken relationships
* incorrect grouping
* inaccurate analysis

---

# Business Scenario

Adventure Works analyst:

```text id="4v8m1q"
Jamie
```

Needs to:

* remove extra spaces
* standardize names
* split customer names
* combine text fields

Before:

```text id="2m8q4v"
Data analysis and reporting
```

---

# Core Text Functions Covered

| Function | Purpose                        |
| -------- | ------------------------------ |
| LEFT     | Extract characters from left   |
| RIGHT    | Extract characters from right  |
| MID      | Extract characters from middle |
| TRIM     | Remove extra spaces            |
| UPPER    | Convert to uppercase           |
| LOWER    | Convert to lowercase           |
| PROPER   | Capitalize each word           |
| CONCAT   | Combine text                   |

---

# Sample Dataset — Raw Customer Data

| Customer Name        |
| -------------------- |
| Doctor Martin Garcia |
| doctor martin garcia |
| DOCTOR MARTIN GARCIA |
| Doctor               |
| Martin               |
| Garcia               |

---

# 1. LEFT Function

## Purpose

Extract characters from:

```text id="5q2m7v"
Left side of text
```

---

# Syntax

```excel id="8v2m4q"
=LEFT(cell,number_of_characters)
```

---

# Example Dataset

| B2                   |
| -------------------- |
| Doctor Martin Garcia |

---

# Formula

```excel id="1x7m5q"
=LEFT(B2,6)
```

---

# Result

| Output |
| ------ |
| Doctor |

---

# Use Cases

* Extract titles
* Country codes
* Product prefixes
* Employee IDs

---

# 2. RIGHT Function

## Purpose

Extract characters from:

```text id="6m2q8v"
Right side of text
```

---

# Syntax

```excel id="7q1m5v"
=RIGHT(cell,number_of_characters)
```

---

# Formula

```excel id="9m4q2v"
=RIGHT(B2,6)
```

---

# Result

| Output |
| ------ |
| Garcia |

---

# Common Use Cases

* Last names
* File extensions
* Last digits of IDs

---

# 3. MID Function

## Purpose

Extract text from:

```text id="5r2m8q"
Middle of a string
```

---

# Syntax

```excel id="8m1q5v"
=MID(cell,start_position,number_of_characters)
```

---

# Formula

```excel id="4m8q2v"
=MID(B2,8,6)
```

---

# Result

| Output |
| ------ |
| Martin |

---

# MID Function Logic

| Argument | Meaning               |
| -------- | --------------------- |
| B2       | Original text         |
| 8        | Start position        |
| 6        | Characters to extract |

---

# Common Analyst Uses

* Extract SKU sections
* Parse codes
* Split imported text
* Separate IDs

---

# LEFT + MID + RIGHT Workflow

## Raw Data

| Full Name            |
| -------------------- |
| Doctor Martin Garcia |

---

# Clean Structured Output

| Title  | First Name | Last Name |
| ------ | ---------- | --------- |
| Doctor | Martin     | Garcia    |

---

# Why This Matters

Structured columns improve:

* filtering
* sorting
* reporting
* Power BI modeling

---

# Alternative Method

## Text to Columns

### Navigation

```text id="7v2m4q"
Data → Text to Columns
```

Useful for:

```text id="5x8m1q"
Large datasets
```

---

# 4. TRIM Function

## Purpose

Remove:

* leading spaces
* trailing spaces
* extra spaces between words

---

# Syntax

```excel id="2q7m5v"
=TRIM(cell)
```

---

# Dirty Dataset

| B2                   |
| -------------------- |
| Doctor Martin Garcia |

---

# Formula

```excel id="1m8q4v"
=TRIM(B2)
```

---

# Result

| Clean Output         |
| -------------------- |
| Doctor Martin Garcia |

---

# Why TRIM Is Important

Extra spaces break:

* lookups
* filters
* grouping
* Power BI relationships

---

# Real Analyst Workflow

## Cleaning Entire Column

### Step 1

Insert helper column.

---

### Step 2

Apply formula:

```excel id="6v1m7q"
=TRIM(A2)
```

---

### Step 3

Autofill down.

---

### Step 4

Copy results.

---

### Step 5

Paste Special → Values.

---

### Step 6

Delete original dirty column.

---

# 5. UPPER Function

## Purpose

Convert all letters to:

```text id="8q5m2v"
UPPERCASE
```

---

# Syntax

```excel id="4r7m2q"
=UPPER(cell)
```

---

# Example

```excel id="5m8q1v"
=UPPER(B2)
```

---

# Result

| Output               |
| -------------------- |
| DOCTOR MARTIN GARCIA |

---

# Common Use Cases

* Product codes
* SKU standardization
* Database consistency

---

# 6. LOWER Function

## Purpose

Convert all letters to:

```text id="2m5q8v"
lowercase
```

---

# Syntax

```excel id="9x2m4q"
=LOWER(cell)
```

---

# Example

```excel id="7m4q1v"
=LOWER(B2)
```

---

# Result

| Output               |
| -------------------- |
| doctor martin garcia |

---

# Common Uses

* Emails
* URLs
* Standardized exports

---

# 7. PROPER Function

## Purpose

Capitalize:

```text id="3v8m2q"
First letter of each word
```

---

# Syntax

```excel id="6w2m8q"
=PROPER(cell)
```

---

# Example

```excel id="1q7m5v"
=PROPER(B2)
```

---

# Result

| Output               |
| -------------------- |
| Doctor Martin Garcia |

---

# Why PROPER Is Useful

Makes reports:

* cleaner
* professional
* standardized

---

# Case Cleaning Example

| Dirty Data    | Function | Result        |
| ------------- | -------- | ------------- |
| doctor martin | PROPER   | Doctor Martin |
| MARTIN        | LOWER    | martin        |
| martin        | UPPER    | MARTIN        |

---

# 8. CONCAT Function

## Purpose

Combine multiple cells into:

```text id="8m1q5v"
Single text value
```

---

# Syntax

```excel id="5v2m7q"
=CONCAT(cell1,cell2,cell3)
```

---

# Sample Dataset

| A2     | B2     | C2     |
| ------ | ------ | ------ |
| Doctor | Martin | Garcia |

---

# Formula Without Spaces

```excel id="9m4q1v"
=CONCAT(A2,B2,C2)
```

---

# Result

| Output             |
| ------------------ |
| DoctorMartinGarcia |

---

# Formula With Spaces

```excel id="2x8m5q"
=CONCAT(A2," ",B2," ",C2)
```

---

# Result

| Output               |
| -------------------- |
| Doctor Martin Garcia |

---

# Important CONCAT Rule

Spaces must be added as:

```text id="7q4m1v"
Text arguments inside quotes
```

---

# CONCAT Use Cases

* Full names
* Addresses
* Email IDs
* Custom labels
* Product descriptions

---

# CONCAT Data Type Warning

After CONCAT:

```text id="4m7q2v"
Result becomes TEXT
```

Even if numbers are combined.

---

# Sample Customer Cleaning Workflow

## Raw Dataset

| Full Name            |
| -------------------- |
| doctor martin garcia |

---

# Step 1 — Remove Spaces

```excel id="6v1m5q"
=TRIM(A2)
```

Result:

```text id="2m8q5v"
doctor martin garcia
```

---

# Step 2 — Standardize Case

```excel id="4x7m1q"
=PROPER(B2)
```

Result:

```text id="9m2q5v"
Doctor Martin Garcia
```

---

# Step 3 — Split Name

| Formula        | Result |
| -------------- | ------ |
| `=LEFT(C2,6)`  | Doctor |
| `=MID(C2,8,6)` | Martin |
| `=RIGHT(C2,6)` | Garcia |

---

# Regional Settings Important

Formula separators vary by region.

---

# Example

## US Region

```excel id="5m2q8v"
=LEFT(B2,6)
```

---

## European Regions

```excel id="8v1m4q"
=LEFT(B2;6)
```

---

# Other Regional Differences

| Setting        | Example                  |
| -------------- | ------------------------ |
| Date Format    | MM/DD/YYYY vs DD/MM/YYYY |
| Function Names | SUM vs SOMME             |
| Separators     | Comma vs Semicolon       |

---

# Common Analyst Mistakes

## Forgetting Spaces in CONCAT

Creates:

```text id="7m2q5v"
Merged unreadable text
```

---

## Wrong Character Count

LEFT/RIGHT/MID may:

```text id="4v8m1q"
Cut incorrect text
```

---

## Ignoring TRIM

Extra spaces break:

* VLOOKUP
* XLOOKUP
* relationships
* Power BI models

---

## Using Manual Cleaning

Functions are:

```text id="2m8q4v"
Faster and scalable
```

---

# Productivity Tips

## Use Helper Columns

Never overwrite:

```text id="5q2m7v"
Original raw data
```

---

## Use Autofill

Apply cleaning formulas quickly.

---

## Paste Special → Values

After cleaning:

```text id="8v2m4q"
Convert formulas into static values
```

---

# Power BI / PL-300 Relevance

These functions help prepare:

* dimension tables
* customer names
* product codes
* lookup fields
* relationships

Before importing into:

```text id="1x7m5q"
Power BI
```

---

# Quick Revision

```text id="6m2q8v"
1. LEFT extracts from left
2. RIGHT extracts from right
3. MID extracts from middle
4. TRIM removes extra spaces
5. UPPER converts to uppercase
6. LOWER converts to lowercase
7. PROPER capitalizes words
8. CONCAT combines text
9. Clean text improves analysis quality
10. Structured text improves reporting
```

---

# Mini Practice Dataset

| A      | B      | C      |
| ------ | ------ | ------ |
| Doctor | Martin | Garcia |

---

# Practice Formulas

## Full Name

```excel id="7q1m5v"
=CONCAT(A2," ",B2," ",C2)
```

---

## Uppercase

```excel id="9m4q2v"
=UPPER(D2)
```

---

## Proper Case

```excel id="5r2m8q"
=PROPER(D2)
```

---

## Remove Spaces

```excel id="8m1q5v"
=TRIM(D2)
```

---

# Most Important Takeaway

Good analysis depends on:

* clean text
* standardized formatting
* structured columns
* consistent naming
* properly formatted datasets
