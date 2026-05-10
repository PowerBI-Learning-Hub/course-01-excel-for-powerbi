# 04 — Excel Multi-Step Formulas, Absolute References & AutoFill

## Core Idea

Complex Excel formulas often include:

* Multiple operators
* Parentheses
* Discounts
* Delivery charges
* Relative references
* Absolute references

To build reliable calculations, analysts must control:

```text id="j9q2yr"
1. Formula execution order
2. Reference behavior during copy/paste
3. AutoFill behavior
```

---

# Business Scenario

Adventure Works is preparing:

* Product quotes
* Discounts
* Delivery charges
* Final customer totals

For:

```text id="srb7mz"
Contoso Bikes
```

---

# Worksheet Workflow

| Column | Purpose                        |
| ------ | ------------------------------ |
| E      | Unit Price                     |
| F      | Quantity                       |
| G      | Subtotal                       |
| H      | Discount                       |
| I      | Total Excluding Delivery       |
| J      | Final Total Including Delivery |

---

# Step 1 — Calculate Subtotal

## Goal

```text id="32vn7f"
Unit Price × Quantity
```

---

## Formula in G6

```excel id="u8q0k9"
=E6*F6
```

---

# Step 2 — Calculate 10% Discount

## Goal

Find:

```text id="r0x9zu"
10% of subtotal
```

---

## Formula in H6

```excel id="2l22gl"
=G6/100*10
```

---

# Excel Execution

## Step-by-Step

```text id="s9ydw9"
1. Divide G6 by 100
2. Multiply result by 10
```

---

# Better Analyst Formula

Instead of:

```excel id="f72sxy"
=G6/100*10
```

Prefer:

```excel id="y2bqah"
=G6*10%
```

Cleaner and easier to audit.

---

# Step 3 — Total Excluding Delivery

## Initial Formula

```excel id="mt77zx"
=G6-H6*I2
```

---

# Problem

Result becomes incorrect because:

```text id="a4wzpr"
Multiplication executes before subtraction
```

Excel calculates:

```text id="j8xv4n"
H6*I2 first
```

---

# Correct Formula Using Parentheses

## Fixed Formula

```excel id="4jw1pa"
=(G6-H6)*I2
```

---

# Why This Works

Excel now:

1. Calculates subtotal minus discount
2. Multiplies remaining amount by value in I2

---

# Analyst Observation

## Parentheses Prevent Hidden Errors

Without brackets:

* Formula may still look believable
* Financial totals become inaccurate
* Errors are harder to detect

---

# Step 4 — Add Delivery Charges

## Goal

Add:

* Region A delivery
* Region B delivery

To total amount.

---

# Formula in J6

```excel id="bl80pw"
=I6+(2*M2)+(2*M3)
```

---

# Formula Breakdown

| Part     | Meaning                  |
| -------- | ------------------------ |
| `I6`     | Total excluding delivery |
| `(2*M2)` | Two Region A deliveries  |
| `(2*M3)` | Two Region B deliveries  |

---

# Why Brackets Matter Here

Without brackets:

* Multiplication/addition order may create incorrect totals
* Formula becomes harder to read

---

# Formula Design Best Practice

## Good Formula Design

```excel id="v0ys7q"
=BaseAmount+(Qty*Rate)
```

Instead of:

```excel id="ml1gfy"
=BaseAmount+Qty*Rate
```

Even if both work.

---

# Relative vs Absolute References

## Problem During AutoFill

When formulas are copied:

* Excel changes references automatically

This is useful for:

* Product rows
* Quantities
* Prices

But dangerous for:

* Fixed rates
* Delivery charges
* Tax percentages

---

# Absolute Reference Syntax

## Example

```excel id="ivwl4r"
=$I$2
```

---

# Meaning

| Symbol | Purpose     |
| ------ | ----------- |
| `$I`   | Lock column |
| `$2`   | Lock row    |

---

# Why Absolute References Were Needed

## In Formula

```excel id="n7n2a6"
=(G6-H6)*$I$2
```

The value in:

```text id="g0j27g"
I2
```

Must stay fixed when copied downward.

---

# F4 Shortcut (Very Important)

## Fastest Way to Lock References

### Steps

1. Select reference in formula
2. Press:

```text id="7k9wqv"
F4
```

---

# F4 Cycles Through

| Press | Result |
| ----- | ------ |
| 1     | `$A$1` |
| 2     | `A$1`  |
| 3     | `$A1`  |
| 4     | `A1`   |

---

# Example in Delivery Formula

## Before F4

```excel id="ywxy4e"
=M2
```

## After F4

```excel id="wq35cl"
=$M$2
```

---

# Safe AutoFill Workflow

## Recommended Process

### Step 1

Create first formula manually.

### Step 2

Test result carefully.

### Step 3

Lock fixed references using:

```text id="sny1yw"
F4
```

### Step 4

Use AutoFill.

### Step 5

Spot-check copied formulas.

---

# AutoFill Shortcut

## Fastest Method

1. Select formula cell
2. Move cursor to bottom-right corner
3. Cursor becomes:

```text id="v74k9n"
Black Cross
```

4. Double-click

---

# What Excel Does

Excel copies formula:

* Downward automatically
* Based on adjacent data range

---

# Real Analyst Use Cases

Used in:

* Pricing sheets
* Invoice models
* Margin calculations
* Forecast templates
* Financial statements
* Power BI staging workbooks

---

# Common Mistakes

## Forgetting Absolute References

Wrong:

```excel id="h5xqrc"
=M2
```

Copied formula becomes:

```excel id="wx1xwx"
=M3
```

---

## Missing Parentheses

Wrong:

```excel id="svlz58"
=G6-H6*I2
```

---

## Hardcoding Discounts

Avoid:

```excel id="6qjlwm"
=G6*0.10
```

Better:

```excel id="z0z9n2"
=G6*$B$1
```

---

# Productivity Tips

## Use F4 Constantly

Huge time saver during:

* Financial modeling
* Formula building
* Dashboard preparation

---

## Use Parentheses Generously

Makes formulas:

* Easier to audit
* Safer
* More readable

---

## Test First Row Before AutoFill

Never autofill untested formulas across large datasets.

---

# PL-300 / Analyst Focus

## Important Concepts

Understand:

* Formula precedence
* Nested calculations
* Relative references
* Absolute references
* AutoFill behavior
* Formula reliability

---

# Quick Revision

```text id="hpmu5w"
1. Complex formulas require parentheses
2. Multiplication executes before subtraction/addition
3. Absolute references stay fixed during copy
4. Use F4 to lock references quickly
5. AutoFill copies formulas automatically
6. Always test formulas before mass copy
```

---

# Mini Practice

## Practice 1 — Subtotal

Create:

```excel id="qk3zpm"
=Price*Quantity
```

---

## Practice 2 — Discount

Create:

```excel id="3v7rqj"
=Subtotal*10%
```

---

## Practice 3 — Fixed Tax Rate

Create:

```excel id="5a4d90"
=Amount*$B$1
```

---

# Most Important Takeaway

Reliable Excel calculations depend on:

* Correct precedence handling
* Proper bracket placement
* Smart use of absolute references
* Safe AutoFill practices
* Careful formula testing
