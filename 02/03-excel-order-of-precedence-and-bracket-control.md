# Excel Order of Precedence & Bracket Control

## Core Idea

When a formula contains multiple operators, Excel does NOT always calculate left → right.

Excel follows:

```text id="6jgo1m"
Order of Precedence
```

This determines:

* Which operation runs first
* How the final result is produced
* Whether calculations are reliable

---

# Why This Matters for Analysts

Incorrect operator order can cause:

* Wrong KPIs
* Incorrect profit calculations
* Financial reporting errors
* Broken Power BI source data
* Misleading dashboards

---

# Excel Formula Basics

## Formula Structure

```excel id="ygr4wv"
=Calculation
```

Example:

```excel id="iq1m6j"
=A1+B1
```

---

# Excel Operator Priority

| Priority | Operator | Purpose        | Example  |
| -------- | -------- | -------------- | -------- |
| 1        | `^`      | Exponent       | `=10^2`  |
| 2        | `*`      | Multiplication | `=10*2`  |
| 3        | `/`      | Division       | `=10/2`  |
| 4        | `+`      | Addition       | `=10+2`  |
| 5        | `-`      | Subtraction    | `=10-2`  |
| 6        | `=`      | Equal To       | `=A1=B1` |
| 7        | `>`      | Greater Than   | `=A1>B1` |
| 8        | `<`      | Less Than      | `=A1<B1` |

---

# Important Rule

## Equal-Level Operators Work Left → Right

### Same Priority Examples

* `+` and `-`
* `*` and `/`
* `>` and `<`

Excel processes them:

```text id="yn8x6g"
Left → Right
```

---

# Example — Left to Right Processing

## Formula

```excel id="6nj5l7"
=A4+C10-D15
```

## Excel Execution

1. Add `A4+C10`
2. Subtract `D15`

Because:

* `+` and `-` have equal priority

---

# Example — NOT Left to Right

## Formula

```excel id="24pkzj"
=B4-D10/H9
```

## What Excel Does

1. Divide `D10/H9`
2. Subtract result from `B4`

Because:

```text id="9s7z2i"
Division has higher priority than subtraction
```

---

# Brackets Override Precedence

## Formula

```excel id="rn7u7z"
=(B4-D10)/H9
```

## Excel Execution

1. Subtract `B4-D10`
2. Divide by `H9`

Reason:

```text id="ow86xq"
Brackets force Excel to calculate that section first
```

---

# Most Important Excel Rule

## If Formula Looks Complex:

Use brackets.

Even when:

* Formula already works
* Order seems obvious

This improves:

* Accuracy
* Readability
* Auditing
* Maintenance

---

# Nested Brackets (Brackets Inside Brackets)

## Example Formula

```excel id="d1ljrn"
=((30+20)-(5*2))/2
```

---

# Step-by-Step Excel Execution

## Step 1 — First Inner Bracket

```excel id="76n80o"
(30+20)
```

Result:

```text id="gvlhhn"
50
```

---

## Step 2 — Second Inner Bracket

```excel id="pdklmh"
(5*2)
```

Result:

```text id="rqm4hl"
10
```

---

## Step 3 — Outer Bracket

```excel id="l3hhwb"
(50-10)
```

Result:

```text id="d3lcgx"
40
```

---

## Step 4 — Final Division

```excel id="r8cxhi"
40/2
```

Final Result:

```text id="vgv4f3"
20
```

---

# Visual Breakdown

```text id="obn2mr"
=((30+20)-(5*2))/2

= (50-10)/2
= 40/2
= 20
```

---

# BEDMAS / PEMDAS in Excel

## Excel Follows Standard Math Rules

| Rule | Meaning        |
| ---- | -------------- |
| B    | Brackets       |
| E    | Exponents      |
| D    | Division       |
| M    | Multiplication |
| A    | Addition       |
| S    | Subtraction    |

---

# Important Excel Observation

## Multiplication & Division Have Equal Status

Excel calculates:

```text id="chjcru"
Left → Right
```

Example:

```excel id="m6p3qm"
=20/5*2
```

Execution:

```text id="m4zcxj"
20/5 = 4
4*2 = 8
```

---

# Addition & Subtraction Also Have Equal Status

Example:

```excel id="87nq0f"
=20-5+2
```

Execution:

```text id="0z06ht"
20-5 = 15
15+2 = 17
```

---

# Real Business Examples

## Profit Margin

```excel id="8r2b03"
=(Revenue-Cost)/Revenue
```

---

## Tax Calculation

```excel id="h1l2nz"
=(Subtotal-Discount)*TaxRate
```

---

## Weighted Sales

```excel id="9v6h3m"
=(Units*Price)-Returns
```

---

# Common Analyst Mistakes

## Missing Brackets

Wrong:

```excel id="ndewhm"
=Revenue-Cost/Revenue
```

---

## Assuming Left → Right

Excel may prioritize:

* Division
* Multiplication

Before subtraction/addition.

---

## Overcomplicated Formulas

Long formulas without brackets become:

* Hard to debug
* Risky to audit
* Error-prone

---

# Best Practices

## Always Use Brackets For:

* Financial formulas
* KPI calculations
* Percentages
* Ratios
* Nested calculations

---

## Build Formulas in Steps

Instead of:

```excel id="5h4t8h"
=((A1+B1-C1)*D1)/E1
```

Test smaller pieces first.

---

## Audit Complex Calculations

Double-click formula cells to:

* See references
* Trace logic
* Detect issues

---

# Formula Reliability Checklist

```text id="g1d8ut"
✔ Use brackets
✔ Test formulas manually
✔ Verify order of operations
✔ Check edge cases
✔ Avoid unnecessary complexity
✔ Review copied formulas
```

---

# PL-300 / Data Analyst Focus

## Important Exam Concepts

Understand:

* Formula precedence
* BEDMAS/PEMDAS
* Nested calculations
* Bracket logic
* Formula debugging

---

# Real-World Uses

Used in:

* Financial modeling
* Margin calculations
* Forecasting
* Budget analysis
* Inventory valuation
* Power BI source preparation

---

# Quick Revision

```text id="12x2n2"
1. Excel follows operator precedence
2. * and / run before + and -
3. Equal-level operators work left → right
4. Brackets override precedence
5. Nested brackets calculate inside → outside
6. Use brackets for safer formulas
```

---

# Mini Practice

## Practice 1

Predict result:

```excel id="kmpv4i"
=10+5*2
```

---

## Practice 2

Force addition first:

```excel id="mrrwma"
=(10+5)*2
```

---

## Practice 3

Calculate:

```excel id="vq3qxo"
=((50-20)+(5*4))/2
```

---

# Most Important Takeaway

Reliable Excel formulas depend on:

* Correct operator order
* Proper bracket placement
* Understanding precedence
* Careful formula testing
