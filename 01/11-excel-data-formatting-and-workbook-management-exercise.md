# Excel Data Formatting and Workbook Management Exercise

## Objective

Practice real-world Excel data cleaning, formatting, and workbook organization techniques.

Goal:

* clean messy spreadsheet data
* improve readability
* apply professional formatting
* organize worksheets for presentation

---

## Business Scenario

You receive a financial workbook from management.

Problems:

* unnecessary columns
* badly formatted data
* hidden formatting issues
* inconsistent worksheet structure

Your job as an analyst:

> prepare the workbook professionally before presenting it to stakeholders.

---

## Skills Practiced

* Deleting columns
* Inserting rows and columns
* AutoFit column resizing
* Fixing numbers stored as text
* Autofill
* Wrap Text
* Format Painter
* Currency formatting
* Worksheet creation
* Worksheet renaming
* Worksheet reordering
* Hiding sheets

---

# Step-by-Step Implementation

# Remove Unnecessary Column

## Purpose

Clean the worksheet by removing irrelevant data.

---

## Steps

1. Select column:

   ```text id="1bqv5h"
   B
   ```

2. Right-click column header

3. Choose:

   ```text id="4f2ztl"
   Delete Columns
   ```

---

## Result

* Removes unnecessary State Abbreviation data
* Makes sheet cleaner for international reporting

---

## Important Notes

Good analysts remove:

* duplicate fields
* unnecessary columns
* cluttered information

---

# Fix Narrow Column Display

## Problem

Column D content appears inconsistent because the column width is too small.

---

## Steps

1. Hover mouse between:

   ```text id="6mxv3q"
   D | E
   ```

2. Cursor changes to resize icon

3. Double-click

---

## Result

Excel automatically performs:

```text id="lrqjse"
AutoFit
```

---

## Important Notes

### Common Indicators of Narrow Columns

| Problem             | Meaning                     |
| ------------------- | --------------------------- |
| `#####`             | Column too narrow           |
| Scientific notation | Number too large for column |
| Hidden text         | Width issue                 |

---

# Fix Number Stored as Text

## Problem

Value in:

```text id="79t8va"
G18
```

aligns left because Excel detects it as text.

Cause:

```text id="g6i1h4"
~
```

symbol before the number.

---

## Steps

1. Double-click:

   ```text id="gdr56f"
   G18
   ```

2. Remove:

   ```text id="j2p5yv"
   ~
   ```

3. Press:

   ```text id="9i2f35"
   Enter
   ```

---

## Result

* Excel converts value back to numeric format
* Number aligns right automatically

---

## Important Notes

### Quick Rule

| Alignment | Usually Means |
| --------- | ------------- |
| Left      | Text          |
| Right     | Number        |

---

# Insert Country Column

## Purpose

Add country-level categorization for international data.

---

## Steps

1. Select column:

   ```text id="7uw5n7"
   C
   ```

2. Right-click

3. Choose:

   ```text id="g2ndro"
   Insert Columns
   ```

4. Enter heading:

   ```text id="l9b2js"
   Country
   ```

---

## Result

New column added successfully.

---

# Use Autofill for Repeated Data

## Purpose

Quickly populate repeated country names.

---

## Steps

1. Type:

   ```text id="lqg6z6"
   USA
   ```

2. Hover bottom-right corner of cell

3. Cursor changes to black cross

4. Drag downward

---

## Result

Excel copies values automatically.

---

## Important Notes

Autofill saves huge amounts of manual typing time.

---

# Insert Country Section Headers

## Purpose

Separate countries visually for easier reporting.

---

## Steps

### Insert Japan Row

1. Select row:

   ```text id="7y4mvl"
   22
   ```

2. Right-click

3. Choose:

   ```text id="l04u3r"
   Insert Rows
   ```

4. Type:

   ```text id="d3mjf8"
   Japan
   ```

---

### Insert Germany Row

Repeat same process for row:

```text id="1gg50d"
26
```

---

## Result

Country sections become visually separated.

---

# Format Main Headers

## Purpose

Make worksheet easier to read professionally.

---

## Steps

1. Select:

   ```text id="wob2vq"
   A1:H1
   ```

2. Go to:

   ```text id="6k2s2g"
   Home → Font Group
   ```

3. Apply:

   * Font size 14
   * Background color

4. Go to:

   ```text id="4z4myn"
   Home → Alignment
   ```

5. Select:

   ```text id="06d8mc"
   Center
   ```

---

## Result

Headers stand out clearly.

---

# Use AutoFit on Headers

## Purpose

Fix partially hidden column titles.

---

## Steps

1. Double-click border between:

   ```text id="p5c42e"
   E | F
   ```

2. Repeat for:

   ```text id="nblib2"
   H
   ```

---

## Result

Column widths adjust automatically.

---

# Use Wrap Text

## Purpose

Avoid oversized columns.

---

## Steps

1. Select:

   ```text id="hm3a0o"
   F1:G1
   ```

2. Go to:

   ```text id="o84m9m"
   Home → Alignment
   ```

3. Select:

   ```text id="nwn2t3"
   Wrap Text
   ```

---

## Result

Text appears on multiple lines inside cells.

---

# Apply Format Painter

## Purpose

Copy formatting quickly.

---

## Steps

1. Select formatted cell:

   ```text id="wxj4mb"
   A1
   ```

2. Go to:

   ```text id="5gt37m"
   Home → Clipboard
   ```

3. Select:

   ```text id="4wcaym"
   Format Painter
   ```

4. Click target cell:

   ```text id="g2iv4y"
   A22
   ```

5. Repeat for:

   ```text id="mbcywj"
   A26
   ```

---

## Result

Formatting copied instantly.

---

# Apply Currency Formatting

## Purpose

Differentiate international currencies clearly.

---

## USD Formatting

### Steps

1. Select:

   ```text id="jz6o25"
   E2:H21
   ```

2. Go to:

   ```text id="4y1hqq"
   Home → Number Group
   ```

3. Choose:

   ```text id="vy49zi"
   $
   ```

---

# Euro Formatting

## Steps

1. Select:

   ```text id="uz0pl0"
   E25:H27
   ```

2. Choose:

   ```text id="ig7fko"
   €
   ```

---

# Japanese Yen Formatting

## Steps

1. Select:

   ```text id="ehhjlwm"
   E23:H25
   ```

2. Open:

   ```text id="yup0ca"
   More Accounting Formats
   ```

3. Select:

   ```text id="v2nv76"
   Currency
   ```

4. Choose:

   ```text id="v4gqpo"
   ¥ Japanese Yen
   ```

---

## Result

All financial regions now use correct currency formats.

---

# Create Exchange Rates Worksheet

## Purpose

Store supporting reference data separately.

---

## Steps

1. Select:

   ```text id="24k9bd"
   +
   ```

2. Create new worksheet

3. Add headings:

   ```text id="zq0bg8"
   USD Amount
   Currency
   Rate
   ```

4. Add exchange rate values manually

---

## Result

Workbook now contains supporting conversion data.

---

# Rename Worksheets

## Purpose

Use professional worksheet names.

---

## Method 1

1. Double-click worksheet tab
2. Type new name
3. Press Enter

---

## Method 2

1. Right-click worksheet tab
2. Select:

   ```text id="ljlwm3"
   Rename
   ```

---

## Example Names

```text id="4mg1ls"
Sample Figures
Exchange Rates
```

---

# Reorder Worksheets

## Purpose

Keep workbook flow logical.

---

## Steps

1. Hold worksheet tab
2. Drag left/right
3. Release mouse

---

## Result

Worksheets appear in desired sequence.

---

# Hide Worksheet

## Purpose

Temporarily remove unnecessary sheets without deleting data.

---

## Steps

1. Select worksheet tab

2. Go to:

   ```text id="vv6czq"
   Home → Cells Group
   ```

3. Select:

   ```text id="rk9nd2"
   Format → Hide & Unhide
   ```

4. Choose:

   ```text id="5k7mrx"
   Hide Sheet
   ```

---

## Result

Worksheet disappears but remains recoverable.

---

# Practical Analyst Takeaways

* Clean spreadsheets improve business communication
* Formatting affects readability significantly
* Numbers stored as text are dangerous for analysis
* Workbook organization matters in professional reporting
* Supporting data should live on separate worksheets
* Consistent formatting improves trust in reports

---

# Common Mistakes

| Mistake                         | Problem                |
| ------------------------------- | ---------------------- |
| Over-widening columns           | Wasted space           |
| Ignoring text-formatted numbers | Broken calculations    |
| Deleting sheets permanently     | Data loss              |
| Using generic sheet names       | Poor organization      |
| Inconsistent formatting         | Unprofessional reports |

---

# Productivity Tips

### AutoFit Shortcut

Double-click column border.

---

### Autofill Shortcut

Drag black cross from cell corner.

---

### Format Painter

Copies formatting instantly.

---

### Wrap Text

Better than creating huge columns.

---

### Hide Instead of Delete

Safer for temporary sheets.

---

# Quick Revision

* Delete unnecessary columns
* Use AutoFit to resize columns
* Fix numbers stored as text
* Insert rows and columns
* Use Autofill for repeated values
* Apply professional formatting
* Use Format Painter for consistency
* Apply currency formats correctly
* Create supporting worksheets
* Rename and organize worksheet tabs
* Hide sheets instead of deleting them

---

# Summary

* This exercise simulated a real analyst spreadsheet-cleaning workflow.
* You practiced cleaning, formatting, organizing, and presenting Excel data professionally.
* Workbook structure and readability are critical business skills.
* Many of these techniques directly support future Power BI and reporting work.
* Professional spreadsheets prioritize clarity, consistency, and usability.
