# 07 — Excel Profit & Margin Exemplar Solution Walkthrough

## Core Idea

This walkthrough demonstrates how analysts build:

* Revenue models
* Profit calculations
* Margin analysis
* Multi-step formulas
* AutoFill-ready worksheets

The exercise combines:

```text id="7g9t2v"
✔ Formula logic
✔ Percentage calculations
✔ Absolute references
✔ Parentheses
✔ Financial analysis
✔ AutoFill workflows
```

---

# Business Scenario

Adventure Works management needs a worksheet showing:

* Purchase costs
* Shipping costs
* Revenue
* Profit
* Gross profit margin

Prepared for:

```text id="8r3h4j"
Management financial review meeting
```

---

# Sample Dataset

## Revenue Figures Sheet

| Product      | Wholesale Cost | Qty Purchased | Qty Sold | Shipping Per Item |
| ------------ | -------------- | ------------- | -------- | ----------------- |
| Bike Frame   | 217.49         | 4642          | 4652     | 5                 |
| Helmet       | 48.00          | 1200          | 1180     | 5                 |
| Gloves       | 20.00          | 3000          | 2900     | 5                 |
| Tire Pump    | 35.50          | 1500          | 1400     | 5                 |
| Water Bottle | 12.99          | 5000          | 4800     | 5                 |

---

# Worksheet Layout

| Column | Purpose        |
| ------ | -------------- |
| E      | Wholesale Cost |
| F      | Qty Purchased  |
| G      | Purchase Cost  |
| H      | Shipping Cost  |
| I      | Total Cost     |
| J      | Retail Price   |
| K      | Qty Sold       |
| L      | Revenue        |
| M      | Profit         |

---

# Step 1 — Purchase Cost Formula

## Goal

Calculate:

```text id="5z7n8x"
Wholesale Cost × Qty Purchased
```

---

# Formula in G4

```excel id="z5f5w8"
=E4*F4
```

---

# Result Example

```text id="5n9r6k"
$1,010,216.69
```

---

# Analyst Observation

This calculates:

```text id="n6d3g7"
Inventory purchasing cost
```

Used in:

* Inventory analysis
* Procurement reporting
* Cost tracking

---

# Step 2 — Shipping Cost Formula

## Goal

Calculate:

```text id="0r5n8q"
Qty Purchased × Shipping Rate
```

Shipping rate stored in:

```text id="m9w2d4"
P1
```

---

# Formula in H4

```excel id="w9j2l7"
=F4*$P$1
```

---

# Why Absolute Reference Matters

## Important

```excel id="3t7x0m"
$P$1
```

Must remain fixed during AutoFill.

Without dollar signs:

* P1 changes to P2, P3...
* Shipping calculations fail

---

# Result Example

```text id="x2n7f9"
$23,260
```

---

# Step 3 — Total Cost Formula

## Goal

Add:

* Purchase Cost
* Shipping Cost

---

# Formula in I4

```excel id="3h8v7f"
=G4+H4
```

---

# Result Example

```text id="m4g8n6"
$1,033,476.69
```

---

# Step 4 — Retail Price Formula

## Business Requirement

Retail price must include:

* Wholesale cost
* Shipping cost
* 50% markup

---

# Formula Logic

```text id="r0j4f8"
(Wholesale Cost + Shipping Cost) × 150%
```

---

# Formula in J4

```excel id="q8x7m1"
=(E4+$P$1)*150%
```

---

# Alternative Formula

```excel id="2f8x6k"
=(E4+$P$1)*1.5
```

Both formulas produce same result.

---

# Why Parentheses Are Critical

Without brackets:

```text id="4z9m1h"
Excel may multiply before adding
```

Leading to:

* Incorrect retail prices
* Wrong profit calculations

---

# Result Example

```text id="r8h5v4"
$333.24
```

---

# Step 5 — Revenue Formula

## Goal

Calculate:

```text id="5n7j0f"
Qty Sold × Retail Price
```

---

# Formula in L4

```excel id="1v0j7q"
=K4*J4
```

---

# Result Example

```text id="7w8g4r"
$1,550,215.04
```

---

# Analyst Observation

Revenue formulas are foundational for:

* Sales reporting
* KPI dashboards
* Power BI measures
* Forecasting

---

# Step 6 — Profit Formula

## Goal

Calculate:

```text id="5b9r7q"
Revenue - Total Cost
```

---

# Formula in M4

```excel id="9v4h2f"
=L4-I4
```

---

# Result Example

```text id="4r7m2j"
$516,738.35
```

---

# Profit Logic

```text id="v9n4t7"
Profit = Money Earned - Money Spent
```

---

# Step 7 — AutoFill Workflow

## Fastest Method

### Steps

1. Select formula cell
2. Move cursor to bottom-right corner
3. Cursor becomes:

```text id="g7k1f5"
Black Cross
```

4. Double-click

---

# Excel AutoFill Behavior

Excel copies formulas:

* Downward automatically
* Based on nearby data blocks

---

# Important Observation

AutoFill shortcut works when:

```text id="6x0w5j"
Data exists beside formula column
```

Without nearby data:

* Must drag manually

---

# AutoFill Columns

Repeat for:

```text id="4m8q0x"
G, H, I, J, L, M
```

---

# Automatic Totals

Excel already contains formulas in:

```text id="1q9k6r"
Row 201
```

Totals update automatically after calculations.

---

# Simple Linked Formula Example

## Cell P2

Contains:

```excel id="2v5j0w"
=AnotherCell
```

---

# Why This Matters

Useful for:

* KPI cards
* Dashboards
* Summary sections
* Power BI staging sheets

---

# Step 8 — Gross Profit Margin Formula

## Business Logic

```text id="7k5r3v"
(Total Revenue - Total Costs) / Total Revenue
```

---

# Formula in P3

```excel id="5x0w9m"
=(L201-I201)/L201
```

---

# Why Brackets Matter

Excel must:

1. Subtract costs from revenue
2. Divide remaining amount by revenue

---

# Final Step

Apply:

```text id="8m5f0w"
Percentage Format (%)
```

---

# Result Example

```text id="4r8w7f"
33.33%
```

---

# What Gross Profit Margin Means

```text id="5m0k8q"
33.33% of sales revenue became profit
```

---

# Formula Summary Table

| Calculation   | Formula             |
| ------------- | ------------------- |
| Purchase Cost | `=E4*F4`            |
| Shipping Cost | `=F4*$P$1`          |
| Total Cost    | `=G4+H4`            |
| Retail Price  | `=(E4+$P$1)*150%`   |
| Revenue       | `=K4*J4`            |
| Profit        | `=L4-I4`            |
| Profit Margin | `=(L201-I201)/L201` |

---

# Important Excel Concepts Used

| Concept             | Example                  |
| ------------------- | ------------------------ |
| Multiplication      | `=E4*F4`                 |
| Addition            | `=G4+H4`                 |
| Subtraction         | `=L4-I4`                 |
| Percentages         | `*150%`                  |
| Absolute References | `$P$1`                   |
| Parentheses         | `(E4+$P$1)`              |
| AutoFill            | Double-click fill handle |

---

# Common Mistakes

## Missing Dollar Signs

Wrong:

```excel id="7h3k9m"
=F4*P1
```

Correct:

```excel id="6m8r2x"
=F4*$P$1
```

---

## Missing Parentheses

Wrong:

```excel id="9j4r0q"
=E4+$P$1*150%
```

Correct:

```excel id="2w7k4f"
=(E4+$P$1)*150%
```

---

## Wrong Profit Formula

Wrong:

```excel id="3n5v9t"
=I4-L4
```

Correct:

```excel id="5z8m7j"
=L4-I4
```

---

# Productivity Tips

## Use F4 Constantly

Shortcut:

```text id="8k0x2q"
F4
```

Used for:

* Locking references
* Faster formula building

---

## Audit First Formula Before AutoFill

Always validate:

* Formula logic
* Reference locking
* Percentage calculations

Before copying hundreds of rows.

---

# PL-300 / Analyst Focus

## Important Skills

Understand:

* Profit calculations
* Revenue formulas
* Margin analysis
* Absolute references
* Formula precedence
* Percentage formatting
* AutoFill behavior

---

# Real-World Applications

Used in:

* Financial analysis
* Retail reporting
* Sales dashboards
* Inventory costing
* Pricing models
* Profitability analysis
* Power BI source modeling

---

# Quick Revision

```text id="4v9h0q"
1. Purchase Cost = Cost × Quantity
2. Shipping rates usually use absolute references
3. Retail pricing often uses markup percentages
4. Revenue = Qty Sold × Retail Price
5. Profit = Revenue - Total Cost
6. Gross Margin = (Revenue-Cost)/Revenue
7. Use brackets to control calculations
8. Use AutoFill for scalable models
```

---

# Mini Practice

## Practice 1 — Revenue Formula

Create:

```excel id="7r4f9m"
=QtySold*RetailPrice
```

---

## Practice 2 — Profit Formula

Create:

```excel id="4x0m8q"
=Revenue-TotalCost
```

---

## Practice 3 — Gross Margin

Create:

```excel id="6k2w9j"
=(Revenue-Cost)/Revenue
```

Format result as:

```text id="3w8n5x"
Percentage
```

---

# Most Important Takeaway

Reliable financial worksheets depend on:

* Correct formulas
* Parentheses
* Absolute references
* Safe AutoFill usage
* Percentage formatting
* Careful formula auditing
