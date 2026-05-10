# Excel Sorting Data Practical Exercise

## Core Idea

Use Excel sorting features to organize large datasets for easier analysis, reporting, and management review.

---

## Practical Workflow

### Create a Visual Tracking Row

Purpose:
Track row movement after sorting.

Steps:

1. Select an entire row (example: A32:I32)
2. Home → Fill Color
3. Apply Yellow color

Result:
Easy to verify whether sorting worked correctly.

---

## Example Dataset

| Product Name | Supplier | Date Entered | Units in Stock |
| ------------ | -------- | ------------ | -------------- |
| Helmet       | Alpha Co | 12-Jan-2024  | 25             |
| Bike Seat    | CyclesAZ | 03-Mar-2024  | 7              |
| Tire Pump    | Beta Ltd | 20-Feb-2024  | 40             |

---

## Sort Text Data (A → Z)

### Sort Product Name Ascending

Steps:

1. Click inside Product Name column
2. Home/Data → Sort A to Z

Result:
Products arranged alphabetically.

---

## Sort Text Data (Z → A)

Steps:

1. Click Product Name column
2. Press:

   * `Alt + D + S`
3. Choose:

   * Column → Product Name
   * Order → Z to A

Result:
Reverse alphabetical sorting applied.

---

## Sort Dates

### Oldest → Newest

Steps:

1. Select Date Entered column
2. Press:

   * `Alt + D + S`
3. Choose:

   * Column → Date Entered
   * Order → Oldest to Newest

Result:
Oldest records appear first.

### Important Observation

Excel stores dates as numbers internally.

---

## Quick Supplier Sort

Steps:

1. Click Supplier column
2. Press:

   * `Alt + H + S + A`

Result:
Supplier names sorted alphabetically.

---

## Multi-Level Sorting

### Scenario

Sort:

1. Supplier → A to Z
2. Units in Stock → Largest to Smallest

### Steps

1. Select dataset
2. Press:

   * `Alt + D + S`
3. Add Level:

   * Level 1:

     * Supplier → A to Z
   * Level 2:

     * Units in Stock → Largest to Smallest
4. Click OK

---

## Multi-Level Sort Visual

### Before Sorting

| Supplier | Units |
| -------- | ----- |
| CyclesAZ | 7     |
| Alpha Co | 30    |
| CyclesAZ | 20    |

### After Sorting

| Supplier | Units |
| -------- | ----- |
| Alpha Co | 30    |
| CyclesAZ | 20    |
| CyclesAZ | 7     |

---

## Undo a Sort

Steps:

* Press:

  * `Ctrl + Z`

Important:
Undo immediately before saving workbook.

---

## Important Observations

* Entire rows move during sorting
* Wrong cursor position = wrong sorting column
* Multi-level sorting is heavily used in analyst workflows
* Always check if headers are enabled

---

## Common Mistakes

* Sorting only one column
* Forgetting headers
* Saving incorrect sort permanently
* Using text dates instead of real dates

---

## Productivity Tips

* Use keyboard shortcuts for faster workflow
* Add temporary colored rows before major sorts
* Use multi-level sorting for inventory/sales analysis
* Verify dataset before sorting

---

## PL-300 Focus

Useful for:

* preparing imported datasets
* organizing exported reports
* inventory analysis
* sales reporting
* operational data cleanup

---

## Quick Revision

| Action           | Shortcut        |
| ---------------- | --------------- |
| Open Sort Dialog | Alt + D + S     |
| Sort A-Z         | Alt + H + S + A |
| Undo             | Ctrl + Z        |
