# 03 — Excel Text Cleaning Exercise Using TRIM, LEFT, RIGHT, MID & CONCAT

## Core Idea

This exercise focuses on:

```text id="7m2q5v"
Cleaning and restructuring messy text data
```

Using Excel text functions:

* TRIM
* PROPER
* UPPER
* LEFT
* RIGHT
* MID
* CONCAT

---

# Business Scenario

Adventure Works downloaded reseller data from:

```text id="4v8m1q"
Another system
```

The imported data contains:

* extra spaces
* inconsistent casing
* combined text
* messy formatting

Goal:

```text id="2m8q4v"
Prepare clean standardized data for analysis
```

---

# Skills Practiced

| Skill                 | Purpose                |
| --------------------- | ---------------------- |
| Remove spaces         | Clean imported data    |
| Standardize text case | Consistent reporting   |
| Split text            | Better filtering       |
| Combine text          | Create readable labels |
| Autofill              | Scale formulas quickly |
| Paste Values          | Remove formulas        |
| Delete raw columns    | Keep clean dataset     |

---

# Sample Raw Dataset

| B (Company)      | D (City)      | G      | H                     |
| ---------------- | ------------- | ------ | --------------------- |
| `  bike world  ` | `new york`    | United | States New York uSA   |
| ` cycle house`   | `los angeles` | United | States California uSA |

---

# Expected Clean Dataset

| Company     | City        | Country | State      | Full Name     | Code |
| ----------- | ----------- | ------- | ---------- | ------------- | ---- |
| Bike World  | New York    | States  | New York   | United States | USA  |
| Cycle House | Los Angeles | States  | California | United States | USA  |

---

# Step 1 — Remove Extra Spaces with TRIM

## Problem

Imported text contains:

```text id="5q2m7v"
Leading and trailing spaces
```

---

# Formula

```excel id="8v2m4q"
=TRIM(B2)
```

---

# Result

| Before           | After      |
| ---------------- | ---------- |
| `  bike world  ` | bike world |

---

# Why It Matters

Extra spaces break:

* filters
* lookups
* grouping
* Power BI relationships

---

# Step 2 — Standardize City Names with PROPER

## Problem

City names appear as:

```text id="1x7m5q"
new york
```

---

# Formula

```excel id="6m2q8v"
=PROPER(D2)
```

---

# Result

| Before   | After    |
| -------- | -------- |
| new york | New York |

---

# Why PROPER Is Useful

Creates:

* professional reports
* consistent categories
* cleaner dashboards

---

# Step 3 — Extract Text Using LEFT

## Goal

Extract:

```text id="7q1m5v"
States
```

From:

```text id="9m4q2v"
States New York uSA
```

---

# Formula

```excel id="5r2m8q"
=LEFT(H2,6)
```

---

# Result

| Output |
| ------ |
| States |

---

# LEFT Function Logic

| Argument | Meaning              |
| -------- | -------------------- |
| H2       | Original text        |
| 6        | Characters from left |

---

# Step 4 — Extract State Using RIGHT

## Goal

Extract:

```text id="8m1q5v"
New York
```

---

# Formula

```excel id="4m8q2v"
=RIGHT(H2,8)
```

---

# Result

| Output   |
| -------- |
| New York |

---

# RIGHT Function Logic

Excel counts:

```text id="7v2m4q"
From right to left
```

---

# Step 5 — Combine Text with CONCAT

## Goal

Combine:

* United
* States

Into:

```text id="5x8m1q"
United States
```

---

# Incorrect Formula

```excel id="2q7m5v"
=CONCAT(G2,I2)
```

---

# Incorrect Result

| Output       |
| ------------ |
| UnitedStates |

---

# Correct Formula

```excel id="1m8q4v"
=CONCAT(G2," ",I2)
```

---

# Correct Result

| Output        |
| ------------- |
| United States |

---

# Important CONCAT Rule

Spaces must be added as:

```text id="6v1m7q"
Text arguments inside quotes
```

---

# Step 6 — Extract Middle Text with MID

## Goal

Extract:

```text id="8q5m2v"
uSA
```

From middle of string.

---

# Formula

```excel id="4r7m2q"
=MID(H2,18,3)
```

---

# Result

| Output |
| ------ |
| uSA    |

---

# MID Function Logic

| Argument | Meaning               |
| -------- | --------------------- |
| H2       | Original text         |
| 18       | Start position        |
| 3        | Characters to extract |

---

# Step 7 — Convert to Uppercase with UPPER

## Goal

Convert:

```text id="5m8q1v"
uSA
```

To:

```text id="2m5q8v"
USA
```

---

# Formula

```excel id="9x2m4q"
=UPPER(L2)
```

---

# Result

| Before | After |
| ------ | ----- |
| uSA    | USA   |

---

# Step 8 — Autofill Formulas

## Columns to Copy Down

| Column |
| ------ |
| C      |
| E      |
| I      |
| J      |
| K      |
| L      |
| M      |

---

# Fast Autofill Method

## Workflow

1. Select first formula cell
2. Move to bottom-right corner
3. Cursor becomes black cross
4. Double-click

---

# Why Double-Click Works

Excel detects:

```text id="7m4q1v"
Adjacent data block
```

And copies formula automatically.

---

# Step 9 — Convert Formulas to Values

## Why?

Cleaned dataset should contain:

```text id="3v8m2q"
Final values instead of formulas
```

---

# Workflow

## Select Entire Sheet

Shortcut:

```text id="6w2m8q"
Ctrl + A
```

---

# Copy

Shortcut:

```text id="1q7m5v"
Ctrl + C
```

---

# Paste Values

### Navigation

```text id="8m1q5v"
Home → Paste → Paste Values
```

---

# Why Paste Values Matters

Prevents:

* broken references
* accidental recalculation
* dependency on helper columns

---

# Step 10 — Delete Unnecessary Columns

## Delete Raw Columns

| Columns |
| ------- |
| B       |
| D       |
| G       |
| H       |
| I       |
| L       |

---

# Important Note

Column letters:

```text id="5v2m7q"
Change after deletion
```

Delete carefully.

---

# Final Clean Dataset Example

| Company     | City        | Country | State      | Full Name     | Country Code |
| ----------- | ----------- | ------- | ---------- | ------------- | ------------ |
| Bike World  | New York    | States  | New York   | United States | USA          |
| Cycle House | Los Angeles | States  | California | United States | USA          |

---

# Real Analyst Workflow

## Raw Imported Data

Usually contains:

* inconsistent formatting
* spaces
* mixed casing
* merged text

---

# Cleaning Workflow

1. Create helper columns
2. Apply text functions
3. Autofill formulas
4. Paste as values
5. Remove raw columns
6. Validate results

---

# Common Analyst Mistakes

## Forgetting Paste Values

Leaves:

```text id="9m4q1v"
Formula dependencies
```

---

## Wrong Character Counts

LEFT/RIGHT/MID may:

```text id="2x8m5q"
Extract incorrect text
```

---

## Overwriting Raw Data

Always:

```text id="7q4m1v"
Keep original data until validation complete
```

---

## Ignoring Spaces

Extra spaces can:

* break lookups
* create duplicates
* affect Power BI joins

---

# Productivity Tips

## Work Left to Right

Improves:

```text id="4m7q2v"
Autofill efficiency
```

---

## Save Before Paste Values

Allows rollback if:

```text id="6v1m5q"
Something goes wrong
```

---

## Use Helper Columns

Cleaner and safer than:

```text id="2m8q5v"
Editing original data directly
```

---

# Power BI / PL-300 Relevance

These cleaning steps help create:

* clean dimensions
* reliable relationships
* standardized categories
* consistent reporting

Before importing into:

```text id="4x7m1q"
Power BI
```

---

# Quick Revision

```text id="9m2q5v"
1. TRIM removes extra spaces
2. PROPER standardizes text case
3. LEFT extracts from left
4. RIGHT extracts from right
5. MID extracts from middle
6. CONCAT combines text
7. UPPER converts to uppercase
8. Paste Values removes formulas
9. Helper columns improve cleaning workflows
10. Clean text improves data analysis quality
```

---

# Mini Practice Dataset

| A                | B        | C                   |
| ---------------- | -------- | ------------------- |
| `  bike world  ` | new york | States New York uSA |

---

# Practice Formulas

## Remove Spaces

```excel id="5m2q8v"
=TRIM(A2)
```

---

## Proper Case

```excel id="8v1m4q"
=PROPER(B2)
```

---

## Extract Left Text

```excel id="7m2q5v"
=LEFT(C2,6)
```

---

## Extract Right Text

```excel id="4v8m1q"
=RIGHT(C2,8)
```

---

## Extract Middle Text

```excel id="2m8q4v"
=MID(C2,18,3)
```

---

## Combine Text

```excel id="5q2m7v"
=CONCAT("United"," ","States")
```

---

# Most Important Takeaway

Good text cleaning improves:

* report quality
* filtering
* searches
* Power BI relationships
* dashboard accuracy
* overall data reliability
