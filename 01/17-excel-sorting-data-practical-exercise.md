# Exercise: Sorting Data in Excel

## Core Idea

This exercise focuses on using Excel sorting tools to organize large datasets efficiently.

You learn how to:

* sort text
* sort numbers
* sort dates
* apply multi-level sorting
* verify sorting behavior

Main goal:

Make inventory data easier to read and analyze.

---

## Why This Matters

Businesses constantly organize data by:

* product names
* suppliers
* sales dates
* stock quantity
* revenue

Sorting helps analysts:

* find records faster
* group similar data
* identify trends
* improve reporting quality

This is a daily task in Excel-based reporting.

---

# Skills Practiced

* Ascending sort
* Descending sort
* Date sorting
* Multi-level sorting
* Undo sorting
* Tracking row movement
* Sort dialog box usage
* Keyboard shortcuts

---

# Practical Setup

# Create a Tracking Marker

Before sorting large datasets:

create a visible tracking row.

---

## Why?

Sorting physically moves rows.

A colored row helps confirm:

* sorting worked correctly
* rows moved properly
* data remained connected

---

## Steps

1. Select:

```text id="srtx11"
A32:I32
```

2. Go to:

```text id="srtx17"
Home → Fill Color
```

3. Apply:

```text id="srtx1d"
Yellow
```

---

# Sort by Product Name (Ascending)

## Goal

Arrange products alphabetically:

```text id="srtx28"
A → Z
```

---

## Steps

1. Click inside:

```text id="srtx2d"
Product Name
```

column

2. Go to:

```text id="srtx2j"
Data → Sort A to Z
```

---

## Result

Products appear alphabetically.

---

# Sort by Product Name (Descending)

## Goal

Arrange products:

```text id="srtx36"
Z → A
```

---

## Steps

1. Select Product Name column

2. Use:

```text id="srtx3d"
Sort Z to A
```

---

# Keyboard Shortcut

```text id="srtx3n"
Alt + D + S
```

Opens Sort dialog box.

---

# Sort by Date (Oldest to Newest)

## Goal

Show earliest records first.

---

## Important Concept

Excel stores dates as:

```text id="srtx49"
numbers
```

So date sorting behaves like numeric sorting.

---

## Steps

1. Select Date Entered column

2. Open:

```text id="srtx4h"
Sort Dialog
```

3. Configure:

| Setting | Value            |
| ------- | ---------------- |
| Column  | Date Entered     |
| Order   | Oldest to Newest |

4. Click:

```text id="srtx4w"
OK
```

---

# Sort by Supplier (Ascending)

## Goal

Group records alphabetically by supplier.

---

## Shortcut Method

### Keyboard Shortcut

```text id="srtx5g"
Alt + H + S + A
```

---

## Ribbon Method

```text id="srtx5n"
Home → Sort & Filter → Sort A to Z
```

---

# Multi-Level Sorting

# Goal

Sort by:

1. Supplier (A→Z)
2. Units in Stock (Largest→Smallest)

---

# Why Multi-Level Sorting?

Single sorting only organizes one condition.

Multi-level sorting allows:

* grouped suppliers
* highest stock first within each supplier

Very common in business reporting.

---

# Steps

1. Select dataset

2. Open:

```text id="srtx6f"
Data → Sort
```

---

# First Level

| Setting | Value    |
| ------- | -------- |
| Column  | Supplier |
| Order   | A to Z   |

---

# Second Level

1. Select:

```text id="srtx73"
Add Level
```

2. Configure:

| Setting | Value               |
| ------- | ------------------- |
| Column  | Units in Stock      |
| Order   | Largest to Smallest |

---

3. Click:

```text id="srtx7h"
OK
```

---

# Result

Data becomes:

* grouped by supplier
* highest stock displayed first inside supplier groups

---

# Undo Sorting

# Purpose

Reverse accidental sorting.

---

## Shortcut

```text id="srtx84"
CTRL + Z
```

---

## Important Warning

Undo only works reliably:

* before saving
* immediately after sort

---

# Real-World Business Usage

| Sort Type      | Example              |
| -------------- | -------------------- |
| Product Name   | Product catalogs     |
| Supplier       | Vendor analysis      |
| Date           | Transaction history  |
| Stock Quantity | Inventory management |
| Revenue        | Sales reporting      |

---

# Common Mistakes

| Mistake                      | Problem                        |
| ---------------------------- | ------------------------------ |
| Sorting wrong column         | Incorrect organization         |
| Forgetting selected column   | Wrong sort behavior            |
| Saving after accidental sort | Permanent data order change    |
| Ignoring headers             | Header row gets sorted         |
| Using single sort repeatedly | Previous sort gets overwritten |

---

# Productivity Tips

### Use Colored Tracking Rows

Excellent for learning sorting behavior.

---

### Always Verify Header Detection

Ensure:

```text id="srtx9j"
My data has headers
```

is enabled.

---

### Multi-Level Sort Is Essential

Very common in:

* finance
* inventory
* operations
* reporting

---

### Learn Keyboard Shortcuts Early

Speeds up Excel workflow dramatically.

---

# Keyboard Shortcuts Summary

| Action           | Shortcut        |
| ---------------- | --------------- |
| Open Sort Dialog | ALT + D + S     |
| Sort Ascending   | ALT + H + S + A |
| Undo             | CTRL + Z        |

---

# PL-300 Exam Focus

Sorting concepts are foundational for:

* preparing clean datasets
* organizing data models
* filtering records
* report preparation

These concepts later connect with:

* Power Query sorting
* Power BI visuals
* table organization
* dashboard filtering

---

# Quick Revision

* Sorting physically moves rows
* Dates are treated as numbers in Excel
* Multi-level sorting supports multiple conditions
* CTRL + Z reverses recent sort
* Colored rows help verify sorting
* Sort dialog gives more control than quick sort
* Sorting improves readability and analysis speed

---

# Summary

* Sorting is essential for organizing large datasets.
* Excel supports text, number, and date sorting.
* Multi-level sorting allows advanced organization.
* Keyboard shortcuts improve efficiency.
* These skills are heavily used in business reporting and data analysis.
