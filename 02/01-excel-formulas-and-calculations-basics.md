# Excel Formulas & Calculations — Practical Analyst Notes

## Core Idea

* A **formula** in Excel performs a calculation using:

  * Numbers
  * Cell references
  * Operators (`+`, `-`, `*`, `/`)
  * Functions (`SUM`, `AVERAGE`, etc.)

* Every formula:

  * Starts with `=`
  * Returns a result
  * Can also return errors (`#DIV/0!`, `#VALUE!`, etc.)

---

# Formula Syntax Basics

## Structure

```excel
=Calculation
```

## Examples

### Add Numbers

```excel
=10+5
```

### Add Cell Values

```excel
=A1+B1
```

### Multiply Cells

```excel
=I3*J3
```

---

# Mathematical Operators in Excel

| Operation      | Symbol | Example  |
| -------------- | ------ | -------- |
| Addition       | `+`    | `=A1+B1` |
| Subtraction    | `-`    | `=A1-B1` |
| Multiplication | `*`    | `=A1*B1` |
| Division       | `/`    | `=A1/B1` |

---

# Static vs Dynamic Formulas

## Static Formula

Uses fixed numbers.

```excel
=100*5
```

### Important

* Result never changes unless formula is manually edited.
* Not ideal for live business reports.

---

## Dynamic Formula

Uses cell references.

```excel
=A2*B2
```

### Important

* Updates automatically when source cells change.
* Preferred in dashboards, reports, and financial models.

---

# How Excel Processes Calculations

## Excel Reads Formulas

* Usually left → right
* Calculates using referenced cell values
* Recalculates automatically after data changes

---

# Formula Bar vs Cell Display

## Formula Bar

Shows:

* Actual formula

Example:

```excel
=I3*J3
```

---

## Worksheet Cell

Shows:

* Result only

Example:

```excel
79050
```

---

# Practical Workflow — Supplier Cost Calculation

## Scenario

Calculate purchase cost:

```text
Cost = Unit Price × Quantity Ordered
```

---

## Step-by-Step

### Step 1 — Select Result Cell

Click:

```text
K3
```

---

### Step 2 — Start Formula

Type:

```excel
=
```

---

### Step 3 — Select Unit Price

Click:

```text
I3
```

Formula becomes:

```excel
=I3
```

---

### Step 4 — Add Multiplication Operator

Type:

```excel
*
```

Formula becomes:

```excel
=I3*
```

---

### Step 5 — Select Quantity

Click:

```text
J3
```

Final formula:

```excel
=I3*J3
```

---

### Step 6 — Press Enter

Excel calculates result automatically.

Example:

```text
79,050
```

---

# Automatic Recalculation

## Example

If quantity changes:

```text
J3 = reduced by 250 units
```

Excel recalculates automatically.

New result:

```text
65,875
```

---

# Formula Chains (Dependent Calculations)

## Example Structure

### Cell C1

```excel
=A1+B1
```

### Cell E1

```excel
=C1*2
```

---

## What Happens

If:

```text
A1 or B1 changes
```

Then:

* C1 recalculates
* E1 recalculates automatically

---

# Cross-Sheet References

## Syntax

```excel
=SheetName!CellReference
```

## Example

```excel
=Products!H2+A1
```

Meaning:

* Take value from:

  * `H2` in Products sheet
  * Add value from current sheet `A1`

---

# External References (Links)

## Can Reference

* Another worksheet
* Another workbook

Used in:

* Financial reporting
* Consolidation models
* Multi-file reporting systems

---

# Edit Mode & Formula Auditing

## Double-Click a Formula Cell

Excel:

* Enters edit mode
* Highlights referenced cells in colors

Very useful for:

* Debugging formulas
* Understanding logic
* Auditing spreadsheets

---

# Important Shortcut

## Cancel Formula Editing Safely

Press:

```text
Esc
```

Use when:

* Accidentally entered edit mode
* Reviewing formulas without changing them

---

# Common Mistakes

## Forgetting `=`

Wrong:

```excel
A1+B1
```

Correct:

```excel
=A1+B1
```

---

## Using `x` Instead of `*`

Wrong:

```excel
=A1xB1
```

Correct:

```excel
=A1*B1
```

---

## Hardcoding Numbers

Avoid:

```excel
=100*25
```

Prefer:

```excel
=A1*B1
```

Reason:

* Dynamic formulas update automatically.

---

## Editing Formula Accidentally

* Double-click enters edit mode
* Press `Esc` to exit safely

---

# Productivity Tips

## Use Cell References Instead of Numbers

Benefits:

* Easier maintenance
* Dynamic updates
* Better scalability

---

## Watch Formula Colors

Excel color-matches:

* Referenced cells
* Formula parts

Helps prevent:

* Wrong references
* Broken calculations

---

## Use Formula Bar for Long Formulas

Better visibility for:

* Nested formulas
* Financial models
* Complex logic

---

# Analyst Observations

## Dynamic Formulas Are Critical

Most real business models rely on:

* Linked calculations
* Automatic recalculation
* Reference-based logic

---

## Formula Chains Can Create Risks

Changing one input can affect:

* Entire dashboards
* Financial statements
* KPIs

Always audit dependencies carefully.

---

# PL-300 / Data Analyst Focus

## Important Concepts

Know:

* Formula syntax
* Cell references
* Dynamic calculations
* Cross-sheet references
* Formula auditing basics

---

## Real Business Uses

Used for:

* Cost calculations
* Sales analysis
* Budgeting
* Forecasting
* Inventory management

---

# Quick Revision

## Formula Rules

```text
1. Every formula starts with =
2. Use operators (+ - * /)
3. Cell references make formulas dynamic
4. Excel recalculates automatically
5. Formula bar shows logic
6. Cells show results
```

---

# Mini Practice Exercises

## Exercise 1 — Revenue

Create:

```excel
=Price*Quantity
```

---

## Exercise 2 — Profit

Create:

```excel
=Revenue-Cost
```

---

## Exercise 3 — Tax Calculation

Create:

```excel
=Subtotal*0.15
```

---

# Most Important Takeaway

## Think Like an Analyst

Good Excel models should be:

* Dynamic
* Easy to update
* Easy to audit
* Reference-driven
* Error-resistant
