# 06 — Excel Profit, Revenue & Margin Calculations Exercise

## Core Idea

This exercise combines:

* Multi-step formulas
* Absolute references
* Percentage calculations
* Revenue analysis
* Profit margin formulas
* AutoFill workflows

These are common real-world analyst tasks used in:

* Financial reporting
* Business analysis
* Power BI source preparation
* PL-300 scenarios

---

# Business Scenario

Adventure Works management needs:

* Purchase costs
* Shipping costs
* Revenue calculations
* Profit analysis
* Profit margin reporting

Prepared by:

```text id="0kq0mu"
Aimee
```

---

# Sample Practice Data Sheet

## Jan-Dec Sales Dataset

| Product      | Qty Purchased | Wholesale Cost | Qty Sold | Shipping Per Item |
| ------------ | ------------- | -------------- | -------- | ----------------- |
| Bike Frame   | 120           | 250            | 110      | 15                |
| Helmet       | 200           | 45             | 180      | 15                |
| Gloves       | 350           | 20             | 320      | 15                |
| Water Bottle | 500           | 12             | 460      | 15                |
| Tire Pump    | 150           | 35             | 140      | 15                |

---

# Worksheet Structure

| Column | Purpose        |
| ------ | -------------- |
| D      | Qty Purchased  |
| E      | Wholesale Cost |
| G      | Purchase Cost  |
| H      | Shipping Cost  |
| I      | Total Cost     |
| J      | Retail Price   |
| K      | Qty Sold       |
| L      | Revenue        |
| M      | Profit         |

---

# Step 1 — Calculate Purchase Cost

## Goal

```text id="5g8yfz"
Qty Purchased × Wholesale Cost
```

---

# Formula in G4

```excel id="n6m3dy"
=D4*E4
```

---

# What This Calculates

Total inventory purchasing cost.

---

# Step 2 — Calculate Shipping Cost

## Goal

```text id="9v8t1l"
Qty Purchased × Shipping Cost Per Item
```

Shipping cost stored in:

```text id="jnhv1x"
P1
```

---

# Formula in H4

```excel id="m7y6qk"
=D4*$P$1
```

---

# Why Use Absolute Reference

## Important

```excel id="5nzzb9"
$P$1
```

Must stay fixed during AutoFill.

Without dollar signs:

* P1 changes to P2, P3...
* Shipping calculations break

---

# Step 3 — Calculate Total Cost

## Formula in I4

```excel id="w9q0mb"
=G4+H4
```

---

# What This Includes

* Purchase Cost
* Shipping Cost

---

# Step 4 — Calculate Retail Price

## Requirements

Retail price must cover:

* Wholesale cost
* Shipping
* 50% markup

---

# Formula Logic

## Step-by-Step

```text id="f3wy7r"
(Wholesale Cost + Shipping Cost) × 150%
```

---

# Formula in J4

```excel id="97y0ma"
=(E4+$P$1)*150%
```

---

# Why Parentheses Matter

Without brackets:

* Excel may multiply before adding
* Retail pricing becomes incorrect

---

# Step 5 — Calculate Revenue

## Goal

```text id="6k0m8w"
Qty Sold × Retail Price
```

---

# Formula in L4

```excel id="j9x5qz"
=K4*J4
```

---

# Step 6 — Calculate Profit

## Goal

```text id="6h0h56"
Revenue - Total Cost
```

---

# Formula in M4

```excel id="y4r8qq"
=L4-I4
```

---

# Step 7 — Use AutoFill

## Fast Workflow

### Steps

1. Select formula cell
2. Move cursor to bottom-right corner
3. Cursor becomes:

```text id="4h4p3g"
Black Cross
```

4. Double-click

---

# Excel AutoFill Behavior

Excel copies formulas:

* Downward automatically
* Based on nearby data range

---

# Important AutoFill Check

Always verify:

```text id="k6f1s4"
Formula stopped at correct row
```

---

# Step 8 — Calculate Profit Margin

## Business Formula

```text id="4f5s9n"
(Total Revenue - Total Costs) / Total Revenue
```

---

# Formula in P3

```excel id="l2v2x8"
=(L201-I201)/L201
```

---

# Final Step

Apply:

```text id="4k9t8d"
Percentage Format (%)
```

---

# Profit Margin Meaning

## Example

If result is:

```text id="q8y0dj"
25%
```

Meaning:

```text id="u6r4rx"
25% of revenue became profit
```

---

# Important Formula Concepts Used

| Concept             | Example                  |
| ------------------- | ------------------------ |
| Multiplication      | `=D4*E4`                 |
| Addition            | `=G4+H4`                 |
| Subtraction         | `=L4-I4`                 |
| Percentages         | `*150%`                  |
| Absolute References | `$P$1`                   |
| Parentheses         | `(E4+$P$1)`              |
| AutoFill            | Double-click fill handle |

---

# Analyst Observations

## Retail Price Logic

Markup formulas are common in:

* Retail analysis
* Manufacturing
* E-commerce
* Inventory planning

---

## Absolute References Are Critical

Used for:

* Shipping rates
* Tax rates
* Discount percentages
* Currency conversion

---

## Profit Margin Is a KPI

Management uses profit margin to measure:

* Business performance
* Pricing strategy
* Operational efficiency

---

# Common Mistakes

## Missing Dollar Signs

Wrong:

```excel id="z5r8vw"
=D4*P1
```

Correct:

```excel id="0q2q9w"
=D4*$P$1
```

---

## Missing Parentheses

Wrong:

```excel id="8r2l2w"
=E4+$P$1*150%
```

Correct:

```excel id="k2f9jh"
=(E4+$P$1)*150%
```

---

## Wrong Profit Formula

Wrong:

```excel id="y3r5vz"
=I4-L4
```

Correct:

```excel id="1q6vkp"
=L4-I4
```

---

# Productivity Tips

## Use F4 for Absolute References

Shortcut:

```text id="v4h7sn"
F4
```

---

## Test First Formula Before AutoFill

Never autofill untested formulas across hundreds of rows.

---

## Use Percentage Formatting

Avoid manually typing `%`.

Use:

```text id="0w9b8j"
Home → Number Group → %
```

---

# Mini Practice Exercises

## Practice 1 — Purchase Cost

Create:

```excel id="1s2n7j"
=QtyPurchased*WholesaleCost
```

---

## Practice 2 — Revenue

Create:

```excel id="7w0v2s"
=QtySold*RetailPrice
```

---

## Practice 3 — Profit Margin

Create:

```excel id="3t5j7k"
=(Revenue-Cost)/Revenue
```

Format as:

```text id="z5v9j1"
Percentage
```

---

# PL-300 / Analyst Focus

## Important Skills

Understand:

* Revenue calculations
* Profit formulas
* Margin calculations
* Absolute references
* Formula precedence
* Percentage formatting
* AutoFill workflows

---

# Real-World Applications

Used in:

* Financial statements
* Sales reporting
* Retail analytics
* Budgeting
* Margin analysis
* Pricing models
* Power BI staging files

---

# Quick Revision

```text id="4x5f8q"
1. Purchase Cost = Qty × Wholesale Cost
2. Shipping formulas usually use absolute references
3. Retail price often includes markup %
4. Revenue = Qty Sold × Retail Price
5. Profit = Revenue - Cost
6. Profit Margin = (Revenue-Cost)/Revenue
7. Use brackets to control calculations
8. Use F4 to lock references
```

---

# Most Important Takeaway

Reliable financial models depend on:

* Correct formulas
* Proper parentheses
* Absolute references
* Accurate percentages
* Safe AutoFill usage
* Careful formula validation
