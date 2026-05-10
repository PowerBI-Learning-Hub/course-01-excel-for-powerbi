# Excel Filtering Data — Exemplar Notes

## Core Idea

Use Excel filters to answer business questions quickly from large datasets without manually scanning rows.

---

# Sample Dataset

| Product Name            | Supplier | Year | Units |
| ----------------------- | -------- | ---- | ----- |
| Mountain Bike Frame     | Z123     | 2023 | 650   |
| Mountain Bike Helmet    | Z123     | 2022 | 320   |
| Road Tire               | Alpha Co | 2023 | 120   |
| Mountain Bike Frame Pro | Z123     | 2023 | 720   |

---

# Turn On Filters

## Steps

1. Click inside dataset
2. Data → Filter

## Result

Filter dropdown arrows appear beside headers.

---

# Filter Gear Components

## Steps

1. Open Category filter
2. Remove:

   * Select All
3. Select:

   * Gear Components
4. Click OK

---

# Visual Result

## Before

| Category |
| -------- |
| Gear     |
| Frames   |
| Clothing |
| Gear     |

---

## After

| Category |
| -------- |
| Gear     |
| Gear     |

---

# Identify Z123 Orders in 2023

## Steps

### Supplier Filter

1. Open Supplier filter
2. Select:

   * Z123

### Year Filter

1. Open Date/Year filter
2. Select:

   * 2023

---

# Result Example

| Supplier | Year |
| -------- | ---- |
| Z123     | 2023 |
| Z123     | 2023 |
| Z123     | 2023 |

Visible row count = answer.

---

# Change Only One Filter

## Smart Analyst Workflow

DO NOT clear all filters.

Only:

1. Open Year filter
2. Change:

   * 2023 → 2022

This preserves Supplier filtering.

---

# Partial Text Search (Very Important)

## Problem

Different frame variations exist:

* Mountain Bike Frame
* Mountain Bike Frame Pro
* Mountain Bike Frame Carbon

Manual ticking becomes slow.

---

# Better Method → Text Filters

## Steps

1. Open Product Name filter

2. Text Filters → Contains

3. Type:

   * mountain

4. Click OK

---

# Result

| Product Name            |
| ----------------------- |
| Mountain Bike Frame     |
| Mountain Bike Helmet    |
| Mountain Bike Frame Pro |

---

# Number Filters

## Find Units Greater Than 500

### Steps

1. Open Units filter
2. Number Filters → Greater Than
3. Enter:

   * 500

---

# Result Example

| Product                 | Units |
| ----------------------- | ----- |
| Mountain Bike Frame     | 650   |
| Mountain Bike Frame Pro | 720   |

---

# IMPORTANT Visual Indicators

## How To Know Filters Are Active

### Signs

* Funnel icon on headers
* Missing row numbers
* Reduced record count

### Example

```text
Rows:
1
2
7
8
```

Rows 3–6 are hidden.

---

# Clear Filters

## Remove One Filter

Header dropdown → Clear Filter

## Remove All Filters

Data → Clear

---

# Common Mistakes

* Forgetting active filters
* Clearing all filters unnecessarily
* Using exact text instead of Contains
* Applying filters on wrong column
* Ignoring hidden rows

---

# Productivity Tips

* Use Text Filters for large datasets
* Stack filters for deeper analysis
* Always monitor visible record count
* Use filters before charts/reporting

---

# PL-300 Focus

Filtering logic is heavily used in:

* Power Query
* Report filters
* Slicers
* Visual interactions
* Data exploration

---

# Quick Revision

| Task              | Path                    |
| ----------------- | ----------------------- |
| Enable Filters    | Data → Filter           |
| Partial Match     | Text Filters → Contains |
| Numeric Filtering | Number Filters          |
| Clear All Filters | Data → Clear            |

---

# Key Takeaways

* Filters hide rows, not delete them
* Multiple filters can work together
* Partial text matching is extremely useful
* Number Filters help identify thresholds quickly
* Filtering is foundational for data analysis workflows
