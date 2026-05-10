# Excel Formulas & Functions Quick Recap

## Core Topics Covered

This week focused on:

* Excel formulas
* Function syntax
* Calculation control
* Percentage calculations
* AutoSum functions
* Autofill workflows

---

# 1. Excel Formulas

## What Is a Formula?

A formula is:

```excel id="4m8q2v"
A calculation performed in Excel
```

Examples:

```excel id="7q1m5v"
=A1+B1
=A1-B1
=A1*B1
=A1/B1
```

---

# Formula Rules

## Every Formula Starts With

```excel id="8v2m4q"
=
```

---

# Common Operators

| Operator | Purpose        |
| -------- | -------------- |
| `+`      | Addition       |
| `-`      | Subtraction    |
| `*`      | Multiplication |
| `/`      | Division       |

---

# Static vs Dynamic Formulas

## Static Formula

Fixed numbers:

```excel id="1x7m5q"
=100+50
```

Always returns same result.

---

## Dynamic Formula

Uses cell references:

```excel id="6m2q8v"
=A1+B1
```

Updates automatically when values change.

---

# Formula Bar

## Purpose

Shows:

```text id="3v8m1q"
Actual formula inside selected cell
```

Worksheet displays:

```text id="5q2m7v"
Calculated result
```

---

# Formula Chains

A formula can reference:

```text id="9m4q2v"
Another formula cell
```

Changes flow through entire calculation chain automatically.

---

# Cross-Sheet References

## Syntax

```excel id="2r7m5q"
=Sheet2!A1
```

Used to reference:

* Other worksheets
* External workbooks

---

# 2. Order of Precedence

## Excel Calculation Priority

Excel calculates:

1. Multiplication & Division
2. Addition & Subtraction

---

# Example

## Without Parentheses

```excel id="8m1q5v"
=2+3*4
```

Result:

```text id="7v2m4q"
14
```

Because:

```text id="5x8m1q"
3*4 happens first
```

---

# Using Parentheses

## Correct Controlled Formula

```excel id="6q4m2v"
=(2+3)*4
```

Result:

```text id="1m8q5v"
20
```

---

# Key Rule

Use parentheses to:

```text id="9r2m7q"
Control calculation sequence
```

---

# 3. Relative vs Absolute References

## Relative Reference

Changes during copy:

```excel id="4v7m1q"
=A1+B1
```

---

# Absolute Reference

Stays fixed:

```excel id="2m8q4v"
=$A$1
```

---

# Shortcut

## F4 Key

Adds dollar signs automatically.

---

# When To Use Absolute References

Useful for:

* Tax rates
* Exchange rates
* Discount percentages
* Fixed lookup values

---

# 4. Percentage Calculations

## Percentage of a Number

```excel id="7m2q5v"
=A1*10%
```

---

# Percentage Difference

```excel id="1v8m4q"
=(New-Old)/Old
```

---

# Increase by Percentage

Increase by 10%:

```excel id="8q5m1v"
=A1*110%
```

---

# Profit Margin Formula

```excel id="5m7q2v"
=(Revenue-Cost)/Revenue
```

---

# 5. Excel Functions

## What Is a Function?

A:

```text id="9x2m4q"
Predefined Excel formula
```

---

# Function Syntax

```excel id="4m1q8v"
=FUNCTION(arguments)
```

---

# Example

```excel id="7v5m2q"
=SUM(B2:B10)
```

---

# Function Components

| Component | Meaning         |
| --------- | --------------- |
| `=`       | Starts formula  |
| `SUM`     | Function name   |
| `()`      | Holds arguments |
| `B2:B10`  | Range argument  |

---

# 6. Insert Function Tool

## Navigation

```text id="2q8m5v"
Formulas → Insert Function
```

---

# Benefits

```text id="6m4q1v"
✔ Helps build formulas
✔ Shows required arguments
✔ Reduces syntax errors
✔ Provides help descriptions
```

---

# Function Categories

| Category    | Example |
| ----------- | ------- |
| Financial   | PMT     |
| Math & Trig | SUM     |
| Logical     | IF      |
| Statistical | AVERAGE |

---

# 7. AutoSum Functions

## AutoSum Provides Quick Access To

| Function | Purpose             |
| -------- | ------------------- |
| SUM      | Total values        |
| AVERAGE  | Mean                |
| COUNT    | Count numeric cells |
| MAX      | Largest value       |
| MIN      | Smallest value      |

---

# Common AutoSum Functions

## SUM

```excel id="8v1m4q"
=SUM(B2:B13)
```

---

## AVERAGE

```excel id="3m7q5v"
=AVERAGE(B2:B13)
```

---

## COUNT

```excel id="6x2m8q"
=COUNT(B2:B13)
```

---

## MAX

```excel id="1m5q7v"
=MAX(B2:B13)
```

---

## MIN

```excel id="5q8m2v"
=MIN(B2:B13)
```

---

# COUNT vs COUNTA

| Function | Counts             |
| -------- | ------------------ |
| COUNT    | Numbers only       |
| COUNTA   | Any non-empty cell |

---

# Important Excel Behavior

## Dates Are Numeric

Excel stores dates internally as:

```text id="9m4q1v"
Numbers
```

So:

```excel id="7r2m5q"
COUNT
```

Can count dates.

---

# 8. Autofill

## Purpose

Copy formulas quickly across:

* Rows
* Columns

---

# Workflow

1. Select formula cell
2. Move to bottom-right corner
3. Cursor becomes black cross
4. Drag or double-click

---

# Excel Automatically Adjusts References

Example:

| Original       | Copied         |
| -------------- | -------------- |
| `=SUM(B2:B13)` | `=SUM(C2:C13)` |

---

# 9. Common Mistakes

## Forgetting Parentheses

Causes incorrect calculations.

---

## Wrong Cell Range

Always verify:

```text id="8m1q5v"
Highlighted range
```

---

## Using Relative Instead of Absolute References

Can break copied formulas.

---

## Confusing COUNT and SUM

COUNT counts rows.
SUM totals values.

---

# 10. Productivity Tips

## Use F4

Quickly create:

```excel id="2v7m4q"
Absolute references
```

---

## Use AutoSum

Faster than typing basic functions manually.

---

## Verify Auto-Selected Ranges

Excel suggestions are:

```text id="5m8q2v"
Helpful but not always correct
```

---

# PL-300 / Analyst Focus

## Important Skills Learned

* Formula syntax
* Function syntax
* Aggregations
* Percentage calculations
* Dynamic calculations
* Formula auditing
* Data summarization

---

# Most Important Takeaways

```text id="4r8m1q"
1. Every formula starts with =
2. Use parentheses to control calculations
3. Use $ for absolute references
4. Functions are predefined formulas
5. SUM, AVERAGE, COUNT, MAX, MIN are core analyst functions
6. AutoSum speeds up reporting
7. Autofill copies formulas dynamically
8. Always verify ranges and references
```
