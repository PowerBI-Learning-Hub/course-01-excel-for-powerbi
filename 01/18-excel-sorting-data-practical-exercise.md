Here’s the practical compact version your new prompt should generate:

# Excel Sorting Data Practical Exercise

## Objective

Practice sorting Excel data using:

* A-Z / Z-A sorting
* Date sorting
* Multi-level sorting
* Undoing sorts safely

---

## Skills Practiced

* Sorting text data
* Sorting dates
* Multi-level sorting
* Using Sort dialog
* Using keyboard shortcuts
* Tracking row movement during sorting

---

# Practical Workflow

## Add a Tracking Row

### Purpose

Helps verify whether sorting is working correctly.

### Steps

1. Select a full row (example: A32:I32)
2. Home → Fill Color
3. Apply a bright color like Yellow

### Result

You can visually track row movement after sorting.

---

## Sort Product Names (A → Z)

### Steps

1. Click any cell inside Product Name column
2. Home/Data → Sort A to Z

### Result

Products arranged alphabetically.

### Important Notes

* Cursor must be inside correct column before sorting.
* Entire rows move together, not just one column.

---

## Sort Product Names (Z → A)

### Steps

1. Click Product Name column
2. Open Sort dialog:

   * Shortcut: `Alt + D + S`
3. Choose:

   * Column: Product Name
   * Order: Z to A

### Result

Products sorted reverse alphabetically.

---

## Sort Dates (Oldest → Newest)

### Steps

1. Select any cell in Date Entered column
2. `Alt + D + S`
3. Choose:

   * Column: Date Entered
   * Order: Oldest to Newest

### Result

Oldest records appear first.

### Important Observations

* Excel stores dates as numbers.
* Date sorting is actually numeric sorting.

---

## Sort Supplier Names Quickly

### Steps

1. Click inside Supplier column
2. Shortcut:

   * `Alt + H + S + A`

### Result

Supplier names sorted A → Z.

---

## Multi-Level Sorting

### Purpose

Sort by multiple conditions together.

### Example

* Supplier → A-Z
* Units in Stock → Largest to Smallest

### Steps

1. Select dataset
2. `Alt + D + S`
3. Add Level:

   * Level 1:

     * Supplier → A to Z
   * Level 2:

     * Units in Stock → Largest to Smallest
4. Click OK

### Result

Data grouped by supplier while highest stock appears first inside each supplier group.

### Analyst Use Case

Very common in:

* inventory reports
* sales analysis
* finance reports
* operational dashboards

---

## Undo a Sort

### Steps

* Press:

  * `Ctrl + Z`

### Important Notes

* Undo immediately after sorting.
* Saving workbook may make sort permanent.

---

# Common Mistakes

* Sorting only one column instead of full dataset
* Forgetting headers
* Wrong cursor position before sorting
* Saving workbook before verifying sort
* Forgetting multi-level sort order

---

# Productivity Tips

* Use keyboard shortcuts for faster sorting
* Add temporary highlight rows before major sorts
* Use multi-level sorting for business reports
* Always verify headers before sorting

---

# Quick Revision

| Action           | Shortcut        |
| ---------------- | --------------- |
| Open Sort Dialog | Alt + D + S     |
| Sort A-Z         | Alt + H + S + A |
| Undo             | Ctrl + Z        |

---

# PL-300 / Analyst Focus

Sorting is important for:

* reviewing raw exported data
* preparing reports
* identifying trends
* organizing inventory/sales/customer data
* improving readability before Power BI import
