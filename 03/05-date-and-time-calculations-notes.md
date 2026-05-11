# Date & Time Calculations in Excel

## Core Idea

Date and time calculations help analysts:

* Track delivery timelines
* Calculate project deadlines
* Monitor sales trends over time
* Measure working days, delays, and performance intervals
* Build dynamic dashboards that update automatically

Excel stores every date as a **serial number** behind the scenes.
This allows Excel to:

* Subtract dates
* Compare dates
* Filter by month/year
* Calculate durations automatically

---

# Sample Dataset — Delivery Tracking

| Order ID | Dispatch Date | Delivery Date | Delivery Days | Month | Year | Current Date |
| -------- | ------------- | ------------- | ------------- | ----- | ---- | ------------ |
| ORD-1001 | 01/05/2026    | 05/05/2026    | 4             | May   | 2026 |              |
| ORD-1002 | 03/05/2026    | 08/05/2026    | 5             | May   | 2026 |              |
| ORD-1003 | 06/05/2026    | 10/05/2026    | 4             | May   | 2026 |              |

---

# Important Date Functions

| Function  | Purpose                     |
| --------- | --------------------------- |
| `TODAY()` | Returns current date        |
| `NOW()`   | Returns current date + time |
| `DAY()`   | Extracts day number         |
| `MONTH()` | Extracts month              |
| `YEAR()`  | Extracts year               |
| `DATE()`  | Creates a custom date       |

---

# Understanding Excel Date Serial Numbers

## How Excel Stores Dates

Excel converts dates into numbers internally.

| Date       | Serial Number |
| ---------- | ------------- |
| 01/01/1900 | 1             |
| 02/01/1900 | 2             |
| 01/05/2026 | Larger number |

Later dates always have larger serial numbers.

---

# Practical Workflow

## 1. Calculate Delivery Days

### Formula

```excel
=C2-B2
```

### Explanation

* Delivery Date minus Dispatch Date
* Excel subtracts serial numbers internally

### Result

| Dispatch Date | Delivery Date | Delivery Days |
| ------------- | ------------- | ------------- |
| 01/05/2026    | 05/05/2026    | 4             |

---

## 2. Display Current Date Dynamically

### Formula

```excel
=TODAY()
```

### Use Cases

* Daily reports
* SLA tracking
* Aging reports
* Deadline monitoring

### Important

Updates automatically every 24 hours.

---

## 3. Display Current Date + Time

### Formula

```excel
=NOW()
```

### Example Result

```text
11/05/2026 14:35
```

### Use Cases

* Timestamping
* Refresh tracking
* Audit logs

---

## 4. Extract Month from Date

### Formula

```excel
=MONTH(B2)
```

### Result

```text
5
```

Useful for:

* Monthly analysis
* Pivot tables
* Trend reporting

---

## 5. Extract Year from Date

### Formula

```excel
=YEAR(B2)
```

### Result

```text
2026
```

Useful for:

* Year-over-year analysis
* Fiscal reporting

---

## 6. Extract Day Number

### Formula

```excel
=DAY(B2)
```

### Result

```text
1
```

Useful for:

* Daily trend analysis
* Peak sales day tracking

---

## 7. Create Custom Date Using DATE Function

### Formula

```excel
=DATE(2026,5,11)
```

### Result

```text
11/05/2026
```

### Useful For

* Building dynamic reports
* Combining separate year/month/day columns
* Power Query preprocessing

---

# Business Use Cases

## Delivery Tracking

```excel
=Delivery Date - Dispatch Date
```

Find:

* Late deliveries
* Average shipping time
* Fastest suppliers

---

## Project Planning

Calculate:

* Working days
* Deadlines
* Remaining days

---

## Sales Trend Analysis

Break data by:

* Month
* Quarter
* Year
* Weekday

---

## Attendance Monitoring

Track:

* Login times
* Shift duration
* Overtime hours

---

# Important Observations

## Dates Are Numbers

Excel only recognizes valid dates if:

* Correct separators are used (`/` or `-`)
* Date format is valid

Correct:

```text
11/05/2026
```

Incorrect:

```text
11.05.2026
```

Incorrect formats may become text values.

---

## TODAY vs NOW

| Function  | Returns     |
| --------- | ----------- |
| `TODAY()` | Date only   |
| `NOW()`   | Date + Time |

---

## Dynamic Nature

Functions like:

```excel
=TODAY()
=NOW()
```

automatically recalculate.

No manual update required.

---

# Common Mistakes

## Storing Dates as Text

Problem:

* Sorting breaks
* Calculations fail
* Filters behave incorrectly

Fix:

* Use proper date formatting
* Convert text to dates

---

## Wrong Regional Format

US Format:

```text
MM/DD/YYYY
```

European Format:

```text
DD/MM/YYYY
```

Can create incorrect calculations.

---

## Forgetting Cell Formatting

Sometimes result appears as:

```text
45789
```

Fix:

* Change format from General → Date

---

# Productivity Tips

## Shortcut — Current Date

```text
Ctrl + ;
```

---

## Shortcut — Current Time

```text
Ctrl + Shift + ;
```

---

## AutoFill Date Series

Drag fill handle:

```text
01/05/2026
02/05/2026
03/05/2026
```

---

# Analyst Workflow Example

## Delivery Performance Dashboard

### Raw Data

| Order ID | Dispatch | Delivery |
| -------- | -------- | -------- |

### Calculated Columns

* Delivery Days
* Delivery Month
* Delivery Year
* Delay Status

### Final Analysis

* Avg delivery time
* Late shipment %
* Monthly delivery trend

---

# PL-300 / Data Analyst Focus

Understand:

* Date intelligence basics
* Dynamic calculations
* Time-based reporting
* Extracting date components
* Data cleaning for date fields

Very important for:

* Power BI
* DAX Time Intelligence
* Excel dashboards
* SQL reporting

---

# Quick Revision

| Task                | Formula            |
| ------------------- | ------------------ |
| Current Date        | `=TODAY()`         |
| Current Date + Time | `=NOW()`           |
| Extract Day         | `=DAY(A2)`         |
| Extract Month       | `=MONTH(A2)`       |
| Extract Year        | `=YEAR(A2)`        |
| Create Date         | `=DATE(2026,5,11)` |
| Days Between Dates  | `=B2-A2`           |

---

# Key Takeaway

Excel treats dates as serial numbers internally.
This makes it possible to:

* Calculate durations
* Build dynamic reports
* Analyze trends over time
* Automate scheduling and tracking workflows

Date functions are foundational for:

* Excel Analytics
* Power BI
* DAX Time Intelligence
* Business Reporting
