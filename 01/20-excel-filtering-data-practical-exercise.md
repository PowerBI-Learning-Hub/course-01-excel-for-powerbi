Here are compact practical notes in your updated style.

# Excel Filtering Data — Practical Exercise

## Core Idea

Filtering helps analysts display only the required records from large datasets without deleting data.

---

# Sample Inventory Dataset

| Product Name            | Category | Supplier | Year | Units |
| ----------------------- | -------- | -------- | ---- | ----- |
| Mountain Bike Frame     | Frames   | Z123     | 2023 | 650   |
| Road Helmet             | Gear     | Alpha Co | 2022 | 120   |
| Mountain Bike Frame Pro | Frames   | Z123     | 2022 | 450   |
| Gear Cable              | Gear     | Z123     | 2023 | 75    |

---

# Turn On Filters

## Steps

1. Click anywhere inside dataset
2. Data → Filter

## Result

Dropdown arrows appear on headers.

---

# Filter Gear Components

## Purpose

Find only Gear category records.

## Steps

1. Open Category filter
2. Uncheck Select All
3. Select Gear
4. Click OK

---

# Visual Example

## Before Filter

| Category |
| -------- |
| Gear     |
| Frames   |
| Gear     |
| Clothing |

---

## After Filter

| Category |
| -------- |
| Gear     |
| Gear     |

---

# Filter Supplier Z123 Orders

## Steps

1. Open Supplier filter
2. Select only:

   * Z123
3. Click OK

---

# Add Year Filter

## For 2023 Orders

1. Open Year filter
2. Select:

   * 2023

## Result

Only Z123 orders from 2023 remain visible.

---

# Change to 2022 Orders

## Important Analyst Workflow

DO NOT clear all filters.

Only:

1. Open Year filter
2. Change:

   * 2023 → 2022

This saves time.

---

# Filter Mountain Bike Frames

## Problem

There may be multiple versions:

* Mountain Bike Frame
* Mountain Bike Frame Pro
* Mountain Bike Frame Carbon

---

# Best Method → Text Filters

## Steps

1. Open Product Name filter
2. Text Filters → Contains
3. Type:

   * Mountain Bike Frame

## Result

All frame variations appear.

---

# Filter Stock Greater Than 500

## Steps

1. Open Units filter
2. Number Filters → Greater Than
3. Enter:

   * 500

---

# Final Result Example

| Product                    | Units |
| -------------------------- | ----- |
| Mountain Bike Frame        | 650   |
| Mountain Bike Frame Carbon | 720   |

---

# VERY IMPORTANT Observations

## Filter vs Sort

| Filter              | Sort                  |
| ------------------- | --------------------- |
| Hides rows          | Reorders rows         |
| Data stays in place | Data physically moves |

---

# How to Know Filters Are Active

## Signs

* Funnel icon appears on header
* Row numbers skip
* Record count changes at bottom

### Example

```text
Rows:
1
2
8
9
```

Means rows 3–7 are hidden.

---

# Clear Filters

## Remove One Filter

Open filter → Clear Filter

## Remove All Filters

Data → Clear

---

# Common Mistakes

* Forgetting active filters
* Filtering wrong column
* Missing partial text matches
* Clearing all filters accidentally
* Using exact match instead of Contains

---

# Productivity Tips

* Use Contains for flexible searches
* Stack multiple filters for deeper analysis
* Always check visible record count
* Use filters before creating reports

---

# PL-300 Focus

Filtering concepts are important for:

* Power Query filtering
* Report filtering
* Slicers
* Drill-down analysis
* Data exploration

---

# Quick Revision

| Task              | Path                    |
| ----------------- | ----------------------- |
| Turn On Filter    | Data → Filter           |
| Text Search       | Text Filters → Contains |
| Number Filter     | Number Filters          |
| Clear All Filters | Data → Clear            |

---

# Key Takeaways

* Filters hide data, not delete it
* Multiple filters can work together
* Text Filters are very useful in analyst workflows
* Number Filters help identify thresholds quickly
* Filtering is one of the most-used Excel analysis skills
