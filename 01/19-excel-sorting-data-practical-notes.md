# Excel Sorting Data — Practical Notes

## Core Idea

Sorting helps analysts organize large Excel datasets for faster reading, reporting, and decision-making.

---

# Sample Inventory Dataset

| Product Name | Supplier | Date Entered | Units |
| ------------ | -------- | ------------ | ----- |
| Helmet       | CyclesAZ | 12-Jan-2024  | 20    |
| Bike Frame   | Alpha Co | 03-Feb-2024  | 55    |
| Tire Pump    | CyclesAZ | 18-Jan-2024  | 7     |
| Water Bottle | Beta Ltd | 05-Mar-2024  | 32    |

---

# Add Tracking Row Before Sorting

## Why?

Helps verify that rows moved correctly after sorting.

## Steps

1. Select full row (example: A32:I32)
2. Home → Fill Color
3. Choose Yellow

---

# Sort Product Names (A → Z)

## Steps

1. Click inside Product Name column
2. Data → Sort A to Z

## Result

### Before

| Product    |
| ---------- |
| Tire Pump  |
| Bike Frame |
| Helmet     |

### After

| Product    |
| ---------- |
| Bike Frame |
| Helmet     |
| Tire Pump  |

---

# Important Observation

## Alpha-Numeric Sorting

Excel sorts:

1. Numbers first
2. Then text alphabetically

### Example

| Values |
| ------ |
| 100X   |
| 200Y   |
| Apple  |
| Zebra  |

---

# Sort Product Names (Z → A)

## Shortcut

```text
Alt + D + S
```

## Settings

* Column → Product Name
* Order → Z to A

---

# Sort Dates (Oldest → Newest)

## Steps

1. Click Date column
2. Data → Sort Oldest to Newest

## Analyst Observation

Excel stores dates as numbers internally.

### Example

| Date        |
| ----------- |
| 01-Jan-2024 |
| 15-Jan-2024 |
| 28-Feb-2024 |

---

# Supplier Sorting

## Quick Method

1. Click Supplier column
2. Press:

```text
Alt + H + S + A
```

---

# Multi-Level Sorting

## Business Scenario

Group same suppliers together and show highest stock first.

---

# Multi-Level Sort Setup

## Steps

1. Select dataset
2. Data → Sort
3. Configure:

| Level | Column         | Order              |
| ----- | -------------- | ------------------ |
| 1     | Supplier       | A → Z              |
| 2     | Units in Stock | Largest → Smallest |

4. Click OK

---

# Multi-Level Sort Visual

## Before

| Supplier | Units |
| -------- | ----- |
| CyclesAZ | 7     |
| Alpha Co | 50    |
| CyclesAZ | 25    |

---

## After

| Supplier | Units |
| -------- | ----- |
| Alpha Co | 50    |
| CyclesAZ | 25    |
| CyclesAZ | 7     |

---

# VERY IMPORTANT — Common Sorting Mistake

## Wrong Way ❌

Selecting only column D before sorting.

```text
D Column Only Selected
```

Result:

* Supplier names move
* Other row data stays
* Dataset becomes corrupted

---

## Correct Way ✅

* Click ANY cell inside dataset
* Then apply sort

Excel automatically sorts entire rows together.

---

# Undo Sorting

## Shortcut

```text
Ctrl + Z
```

Important:
Undo BEFORE saving workbook.

---

# Analyst Productivity Tips

* Always keep headers enabled
* Add temporary highlight rows before sorting
* Use multi-level sorting for reports
* Verify row movement after sorting
* Never sort isolated columns

---

# PL-300 Focus

Useful for:

* data preparation
* exported report cleanup
* inventory analysis
* operational reporting
* validating imported datasets

---

# Quick Revision

| Task             | Shortcut        |
| ---------------- | --------------- |
| Open Sort Dialog | Alt + D + S     |
| Sort A-Z         | Alt + H + S + A |
| Undo             | Ctrl + Z        |

---

# Key Takeaways

* Sorting reorganizes entire rows
* Multi-level sorting is extremely important in analyst workflows
* Dates are sorted numerically
* Wrong sorting can corrupt datasets
* Always validate sorted results visually
