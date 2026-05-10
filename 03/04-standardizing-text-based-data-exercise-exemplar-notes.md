# 04 — Standardizing Text-Based Data in Excel (Exercise Walkthrough)

## Core Idea

This exercise focuses on:

```text id="7m2q5v"
Cleaning and restructuring messy text data using Excel text functions
```

Main tasks:

* Remove unnecessary spaces
* Standardize text case
* Extract text sections
* Combine text values
* Convert formulas into clean values

---

# Business Scenario

Adventure Works reseller data:

```text id="4v8m1q"
Downloaded from another system
```

Problems found:

* extra spaces
* uppercase city names
* merged text strings
* inconsistent formatting

Goal:

```text id="2m8q4v"
Prepare clean standardized data for analysis and reporting
```

---

# Functions Used

| Function | Purpose                    |
| -------- | -------------------------- |
| TRIM     | Remove extra spaces        |
| PROPER   | Standardize capitalization |
| LEFT     | Extract left-side text     |
| RIGHT    | Extract right-side text    |
| MID      | Extract middle text        |
| CONCAT   | Combine text               |
| UPPER    | Convert to uppercase       |

---

# Sample Raw Dataset

| B (Company)                           | D (City) | G      | H                 |
| ------------------------------------- | -------- | ------ | ----------------- |
| `  the bicycle accessories company  ` | ALHAMBRA | United | StatesNew YorkuSA |

---

# Expected Clean Dataset

| Company                         | City     | Country | State    | Combined Name | Code |
| ------------------------------- | -------- | ------- | -------- | ------------- | ---- |
| The Bicycle Accessories Company | Alhambra | States  | New York | United States | USA  |

---

# Step 1 — Remove Extra Spaces with TRIM

## Problem

Company names contain:

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

| Before                                | After                           |
| ------------------------------------- | ------------------------------- |
| `  the bicycle accessories company  ` | The Bicycle Accessories Company |

---

# Why TRIM Matters

Extra spaces can:

* break lookups
* create duplicate categories
* affect Power BI relationships

---

# Step 2 — Standardize City Names with PROPER

## Problem

Cities entered as:

```text id="1x7m5q"
ALHAMBRA
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
| ALHAMBRA | Alhambra |

---

# Why PROPER Is Useful

Creates:

* cleaner reports
* professional formatting
* consistent filtering

---

# Step 3 — Extract Text Using LEFT

## Goal

Extract:

```text id="7q1m5v"
States
```

From:

```text id="9m4q2v"
StatesNewYorkuSA
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
| H2       | Source text          |
| 6        | Characters from left |

---

# Step 4 — Extract Text Using RIGHT

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
Characters from right side
```

---

# Step 5 — Combine Text Using CONCAT

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

# Step 6 — Extract Middle Text Using MID

## Goal

Extract:

```text id="8q5m2v"
uSA
```

---

# Formula

```excel id="4r7m2q"
=MID(H2,8,3)
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
| H2       | Source text           |
| 8        | Starting position     |
| 3        | Characters to extract |

---

# Step 7 — Convert Text to Uppercase

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

## Columns Filled Down

| Columns |
| ------- |
| C       |
| E       |
| I       |
| J       |
| K       |
| L       |
| M       |

---

# Fast Autofill Workflow

1. Select formula cell
2. Move cursor to bottom-right corner
3. Cursor changes to black cross
4. Double-click

---

# Why Double-Click Works

Excel uses:

```text id="7m4q1v"
Adjacent data block as reference
```

---

# Step 9 — Convert Formulas to Values

## Why This Step Matters

Prevents:

* dependency on formulas
* accidental recalculation
* broken references

---

# Workflow

## Select Entire Worksheet

Shortcut:

```text id="3v8m2q"
Ctrl + A
```

---

# Copy

Shortcut:

```text id="6w2m8q"
Ctrl + C
```

---

# Paste Values

### Navigation

```text id="1q7m5v"
Home → Paste → Paste Values
```

---

# Result

Worksheet now contains:

```text id="8m1q5v"
Static clean values instead of formulas
```

---

# Step 10 — Delete Old Dirty Columns

## Remove Columns

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
Shift after deletion
```

Delete carefully.

---

# Final Clean Dataset

| Company                         | City     | Country | State    | Full Name     | Code |
| ------------------------------- | -------- | ------- | -------- | ------------- | ---- |
| The Bicycle Accessories Company | Alhambra | States  | New York | United States | USA  |

---

# Real Analyst Workflow

## Typical Imported Data Problems

| Problem             | Example           |
| ------------------- | ----------------- |
| Extra spaces        | `company`         |
| Wrong case          | NEW YORK          |
| Combined text       | StatesNewYorkuSA  |
| Inconsistent naming | usa / USA / U.S.A |

---

# Recommended Cleaning Process

1. Keep raw data untouched
2. Create helper columns
3. Apply cleaning formulas
4. Autofill formulas
5. Validate results
6. Paste as values
7. Remove raw columns

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

## Deleting Raw Data Too Early

Always:

```text id="7q4m1v"
Validate cleaned data first
```

---

## Ignoring Spaces

Extra spaces can:

* break joins
* affect lookups
* create duplicates

---

# Productivity Tips

## Work Left to Right

Improves:

```text id="4m7q2v"
Autofill efficiency
```

---

## Save Before Paste Values

Allows:

```text id="6v1m5q"
Recovery if needed
```

---

## Use Helper Columns

Safer than:

```text id="2m8q5v"
Editing original imported data directly
```

---

# Power BI / PL-300 Relevance

These text-cleaning workflows help create:

* clean dimension tables
* reliable relationships
* standardized customer names
* consistent geographic data

Before importing into:

```text id="4x7m1q"
Power BI
```

---

# Quick Revision

```text id="9m2q5v"
1. TRIM removes spaces
2. PROPER standardizes text case
3. LEFT extracts left-side text
4. RIGHT extracts right-side text
5. MID extracts middle text
6. CONCAT combines text values
7. UPPER converts text to uppercase
8. Autofill speeds up cleaning
9. Paste Values removes formulas
10. Clean text improves reporting accuracy
```

---

# Mini Practice Dataset

| A                                     | B        | C                |
| ------------------------------------- | -------- | ---------------- |
| `  the bicycle accessories company  ` | ALHAMBRA | StatesNewYorkuSA |

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
=MID(C2,8,3)
```

---

## Combine Text

```excel id="5q2m7v"
=CONCAT("United"," ","States")
```

---

## Convert to Uppercase

```excel id="8v2m4q"
=UPPER("uSA")
```

---

# Most Important Takeaway

Clean and standardized text data:

* improves analysis quality
* reduces duplicate categories
* improves filtering and sorting
* creates reliable Power BI models
* supports accurate reporting
