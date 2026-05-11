# 10-Logical-Functions-IF-Function.md

# Logical Functions in Excel — IF Function

## Core Idea

Logical functions allow Excel to make decisions based on conditions.

Excel checks:

* TRUE
* FALSE

Then performs different actions based on the result.

---

# Real Business Use Case

Adventure Works wants to:

* Check employee sales targets
* Award bonuses automatically
* Identify underperforming staff

This is done using the:

```excel id="nqkg8m"
IF()
```

function.

---

# Sample Dataset

## Monthly Sales Worksheet

| Employee Name | Monthly Sales | Sales Target | Bonus Amount |
| ------------- | ------------- | ------------ | ------------ |
| Michelle Cook | 52000         | 50000        |              |
| James Hall    | 47000         | 50000        |              |
| Sarah Green   | 61000         | 55000        |              |
| Robert Lee    | 43000         | 45000        |              |
| Emma Davis    | 70000         | 65000        |              |

---

# Bonus Configuration

## Cell H4

| Bonus Value |
| ----------- |
| 500         |

---

# IF Function Structure

## Syntax

```excel id="zj5vs9"
=IF(logical_test, value_if_true, value_if_false)
```

---

# Formula Breakdown

| Part             | Meaning                    |
| ---------------- | -------------------------- |
| `logical_test`   | Condition to check         |
| `value_if_true`  | Result if condition passes |
| `value_if_false` | Result if condition fails  |

---

# Example Formula

## Cell E4

### Formula

```excel id="i9j9q1"
=IF(B4>=C4,$H$4,0)
```

---

# Formula Logic

| Condition       | Result    |
| --------------- | --------- |
| Sales >= Target | Give $500 |
| Sales < Target  | Give 0    |

---

# Example Results

| Employee      | Sales | Target | Bonus |
| ------------- | ----- | ------ | ----- |
| Michelle Cook | 52000 | 50000  | 500   |
| James Hall    | 47000 | 50000  | 0     |
| Sarah Green   | 61000 | 55000  | 500   |

---

# Logical Operators in Excel

## Equal To

```excel id="nhbldj"
=
```

Checks if values are equal.

Example:

```excel id="ddxrlm"
=A1=B1
```

---

## Greater Than

```excel id="wj5f40"
>
```

Checks if one value is larger.

Example:

```excel id="8rzvku"
=A1>100
```

---

## Less Than

```excel id="utff9e"
<
```

Checks if one value is smaller.

Example:

```excel id="d81t7x"
=A1<100
```

---

## Greater Than or Equal To

```excel id="d0pk2o"
>=
```

Example:

```excel id="q9y5ik"
=A1>=500
```

---

## Less Than or Equal To

```excel id="ob1vsi"
<=
```

Example:

```excel id="0e3kbo"
=A1<=500
```

---

## Not Equal To

```excel id="0jw7j0"
<>
```

Example:

```excel id="2f92sp"
=A1<>B1
```

---

# Why Absolute Reference Was Used

## Correct Formula

```excel id="c7m37z"
=IF(B4>=C4,$H$4,0)
```

---

# Why `$H$4`?

Bonus amount must remain fixed when formula is copied down.

Without dollar signs:

```excel id="pvjvgi"
=IF(B4>=C4,H4,0)
```

Autofill changes references incorrectly.

---

# Autofill Process

## Steps

1. Select E4
2. Move cursor to bottom-right corner
3. Black cross appears
4. Double-click

Excel copies formula down automatically.

---

# Final Output Example

| Employee      | Sales | Target | Bonus |
| ------------- | ----- | ------ | ----- |
| Michelle Cook | 52000 | 50000  | 500   |
| James Hall    | 47000 | 50000  | 0     |
| Sarah Green   | 61000 | 55000  | 500   |
| Robert Lee    | 43000 | 45000  | 0     |
| Emma Davis    | 70000 | 65000  | 500   |

---

# Important Excel Concepts

# TRUE vs FALSE

IF functions always return:

| Result | Meaning          |
| ------ | ---------------- |
| TRUE   | Condition passed |
| FALSE  | Condition failed |

---

# Example

```excel id="odw8bq"
=10>5
```

Result:

```text id="7jqvfp"
TRUE
```

---

```excel id="4j8e0k"
=5>10
```

Result:

```text id="g5n6yn"
FALSE
```

---

# Common Mistakes

## Missing Commas

Wrong:

```excel id="p7g8bb"
=IF(B4>=C4 $H$4 0)
```

Correct:

```excel id="ms14dg"
=IF(B4>=C4,$H$4,0)
```

---

## Forgetting Dollar Signs

Wrong:

```excel id="sh0e0m"
=IF(B4>=C4,H4,0)
```

Correct:

```excel id="6h9wul"
=IF(B4>=C4,$H$4,0)
```

---

## Wrong Logical Operator

Wrong:

```excel id="g6ps22"
=IF(B4>C4,$H$4,0)
```

This ignores employees exactly meeting target.

Correct:

```excel id="x39v2w"
=IF(B4>=C4,$H$4,0)
```

---

# Practical Business Uses

## HR & Payroll

* Bonus calculations
* Attendance tracking
* Salary conditions

---

## Sales Reporting

* Target achievement
* Commission calculations
* Incentive tracking

---

## Inventory

* Low stock alerts
* Reorder status
* Product availability

---

## Finance

* Budget checks
* Expense approvals
* Risk flags

---

# Productivity Tips

## Quick Absolute Reference

Press:

```text id="3htmgf"
F4
```

---

## Autofill Shortcut

Double-click fill handle to copy formulas quickly.

---

## Formula Help Popup

Excel automatically shows:

```text id="i6lf8n"
logical_test, value_if_true, value_if_false
```

while typing IF function.

---

# PL-300 / Analyst Focus

Understand:

* TRUE/FALSE logic
* Conditional calculations
* Logical operators
* Relative vs absolute references
* IF function syntax

These are heavily used in:

* Power BI DAX
* KPI logic
* Conditional columns
* Business rules
* Dashboard indicators

---

# Quick Revision

| Operator | Meaning          |
| -------- | ---------------- |
| `=`      | Equal            |
| `>`      | Greater than     |
| `<`      | Less than        |
| `>=`     | Greater or equal |
| `<=`     | Less or equal    |
| `<>`     | Not equal        |

---

# IF Function Template

```excel id="vlf4fq"
=IF(condition, result_if_true, result_if_false)
```

---

# Key Takeaway

IF functions help analysts:

* Automate decision-making
* Apply business rules
* Create dynamic reports
* Reduce manual checking
* Build smarter spreadsheets
