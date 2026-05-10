# Sorting and Filtering Data in Excel

## Core Idea

Large Excel datasets become difficult to understand when data is randomly arranged.

This lecture focuses on:

* sorting data
* filtering records
* organizing spreadsheets
* finding information quickly

Main goal:

Make large datasets easier to read and analyze.

---

## Why This Matters

Businesses constantly work with:

* inventory records
* customer lists
* sales reports
* employee databases
* transaction history

Without sorting and filtering:

* analysis becomes slow
* important insights are hidden
* reports become difficult to review

These are core Excel skills used daily in data analysis.

---

# Understanding Sorting vs Filtering

| Feature | What It Does                    |
| ------- | ------------------------------- |
| Sort    | Reorders rows physically        |
| Filter  | Hides unwanted rows temporarily |

---

# Important Difference

## Sorting

* changes row positions
* permanently changes order if file is saved

---

## Filtering

* does NOT move rows
* only hides rows temporarily
* safer for analysis

---

# Practical Skills Covered

* Sort A to Z
* Sort Oldest to Newest
* Multi-level sorting
* Enable filters
* Apply text filters
* Apply number filters
* Clear filters
* Identify filtered data

---

# Sorting Data in Excel

# Quick Sort (Single Column)

## Purpose

Organize data quickly using one column.

---

## Example

Sort inventory by:

* supplier
* price
* date
* quantity

---

## Steps

1. Click inside target column

Example:

```text id="srt11"
Date Entered
```

2. Go to:

```text id="srt17"
Data → Sort & Filter
```

3. Choose:

```text id="srt1d"
Sort Ascending
```

or

```text id="srt1j"
Sort Descending
```

---

# Date Sorting

Excel treats dates as numbers.

---

## Example

| Sort Type        | Result               |
| ---------------- | -------------------- |
| Oldest to Newest | Earliest dates first |
| Newest to Oldest | Latest dates first   |

---

# Important Warning About Sorting

Sorting physically moves rows.

If workbook is saved:

* original order is lost
* Undo may not work later

---

# Multi-Level Sorting

## Purpose

Sort data using multiple conditions simultaneously.

---

## Example

Sort inventory:

1. by Supplier
2. then by Date

---

# Why Multi-Level Sort Matters

Single sorting causes problems.

Example:

* sorting by Supplier removes previous Date sort
* sorting by Date removes previous Supplier grouping

Multi-level sorting solves this issue.

---

# Steps for Multi-Level Sorting

1. Select dataset

2. Go to:

```text id="srt2n"
Data → Sort
```

3. Confirm:

```text id="srt2t"
My data has headers
```

is checked.

---

## First Sort Level

### Configure:

| Setting | Value       |
| ------- | ----------- |
| Column  | Supplier    |
| Sort On | Cell Values |
| Order   | A to Z      |

---

## Add Second Level

1. Click:

```text id="srt36"
Add Level
```

2. Configure:

| Setting | Value            |
| ------- | ---------------- |
| Column  | Date Entered     |
| Sort On | Cell Values      |
| Order   | Newest to Oldest |

---

3. Click:

```text id="srt3k"
OK
```

---

# Result

Data becomes:

* grouped by supplier
* newest records shown first inside each supplier group

---

# Filtering Data

# Purpose

Show only records matching specific conditions.

---

# Enable Filters

## Steps

1. Select dataset

2. Go to:

```text id="flt11"
Data → Filter
```

---

## Result

Dropdown arrows appear in column headers.

---

# Text Filtering Example

## Goal

Show only supplier:

```text id="flt1c"
CyclesAZ
```

---

## Steps

1. Click filter dropdown in Supplier column

2. Uncheck:

```text id="flt1j"
Select All
```

3. Check:

```text id="flt1p"
CyclesAZ
```

4. Click:

```text id="flt1v"
Apply
```

---

# Result

Only CyclesAZ records remain visible.

All other rows are hidden.

---

# Apply Multiple Filters

## Example

Show rows where:

* Supplier = CyclesAZ
* Unit Price = 7

---

## Steps

1. Filter Supplier column

2. Then filter Unit Price column

3. Select desired value

4. Apply filter

---

# Result

Excel displays only rows matching BOTH conditions.

---

# Important Filtering Concept

Additional filters work only on:

```text id="flt2m"
currently visible rows
```

---

# How to Know Data is Filtered

# Method 1 — Funnel Icon

Filter dropdown shows:

```text id="flt34"
funnel symbol
```

This means filter is active.

---

# Method 2 — Missing Row Numbers

Example:

| Visible Rows |
| ------------ |
| 8            |
| 9            |
| 112          |

Rows between 10–111 are hidden.

---

# Clear Filters

# Clear Single Filter

## Steps

1. Open filtered column dropdown

2. Select:

```text id="flt3u"
Clear Filter
```

---

# Clear All Filters

## Steps

1. Go to:

```text id="flt44"
Data → Sort & Filter
```

2. Select:

```text id="flt49"
Clear
```

---

# Result

All hidden rows become visible again.

---

# Real-World Business Usage

| Use Case             | Example                  |
| -------------------- | ------------------------ |
| Inventory management | Filter suppliers         |
| Sales reporting      | Sort by revenue          |
| HR analysis          | Filter departments       |
| Finance              | Sort by transaction date |
| Customer analysis    | Filter locations         |

---

# Common Mistakes

| Mistake                        | Problem                |
| ------------------------------ | ---------------------- |
| Forgetting active filters      | Missing data confusion |
| Sorting only one column        | Data mismatch          |
| Saving after accidental sort   | Permanent row changes  |
| Not selecting headers properly | Header row gets sorted |
| Applying filters incorrectly   | Incomplete analysis    |

---

# Productivity Tips

### Always Check “My Data Has Headers”

Prevents header row from being included in sort.

---

### Use Multi-Level Sorting for Reports

Very common in business reporting.

---

### Filtering is Safer Than Sorting

Filtering preserves original data order.

---

### Check Bottom Left Status Bar

Excel often displays:

```text id="flt59"
10 records found
```

Useful for validation.

---

### Use Filters Before Analysis

Helps focus only on relevant data.

---

# PL-300 Exam Focus

Important Excel preparation concepts relevant for Power BI:

* data organization
* filtering logic
* sorting structures
* preparing clean datasets
* understanding row visibility

These concepts later transfer into:

* Power Query
* Power BI visuals
* report filtering
* slicers

---

# Quick Revision

* Sorting changes row order
* Filtering hides rows temporarily
* Multi-level sort allows multiple sort conditions
* Filters use dropdown arrows
* Funnel icon indicates active filter
* Clear Filter removes single filter
* Clear removes all filters
* Excel treats dates as numbers during sorting

---

# Summary

* Sorting and filtering are essential Excel data analysis skills.
* Sorting reorganizes rows physically.
* Filtering temporarily hides irrelevant records.
* Multi-level sorting helps organize complex datasets.
* These tools make large spreadsheets faster to analyze and easier to understand.
