# Excel Formula Operators, Precedence & Cell References

## Core Idea

Excel formulas are controlled by:

* Operators (`+ - * /`)
* Calculation priority (precedence)
* Parentheses `()`
* Relative references
* Absolute references

These concepts directly affect:

* Financial calculations
* KPI accuracy
* Forecast models
* Power BI source files
* PL-300 exam questions

---

# Formula Operators

| Action   | Operator | Example  |
| -------- | -------- | -------- |
| Add      | `+`      | `=A1+B1` |
| Subtract | `-`      | `=A1-B1` |
| Multiply | `*`      | `=A1*B1` |
| Divide   | `/`      | `=A1/B1` |

---

# Order of Precedence (Very Important)

Excel does NOT always calculate left → right.

## Excel Priority Order

1. `()` Parentheses
2. `/` Division
3. `*` Multiplication
4. `+` Addition
5. `-` Subtraction

---

# Precedence Example

## Formula

```excel
=2+3*4
```

## Excel Execution

```text
3*4 = 12
2+12 = 14
```

## Final Result

```text
14
```

---

# Control Calculations with Parentheses

## Correct Formula

```excel
=(2+3)*4
```

## Excel Execution

```text
2+3 = 5
5*4 = 20
```

## Final Result

```text
20
```

---

# Analyst Rule

## Always Use Parentheses When:

* Combining multiple operations
* Building financial models
* Creating KPI calculations
* Writing nested formulas

Even if formula already works.

This prevents:

* Logical mistakes
* Hidden reporting errors
* Wrong business decisions

---

# Real Business Example

## Incorrect

```excel
=Revenue-Cost*TaxRate
```

## Safer

```excel
=(Revenue-Cost)*TaxRate
```

---

# Relative References

## Definition

Default Excel behavior.

References automatically change when copied.

---

# Example

## Original Formula

```excel
=I3*J3
```

## Copied Down

```excel
=I4*J4
```

Excel adjusts row references automatically.

---

# Best Use Cases for Relative References

| Scenario           |
| ------------------ |
| Sales calculations |
| Inventory totals   |
| Profit per row     |
| Monthly reports    |
| Repeating formulas |

---

# Absolute References

## Definition

Reference stays fixed during copy/paste.

## Syntax

```excel
=$A$1
```

| Symbol | Meaning     |
| ------ | ----------- |
| `$A`   | Lock column |
| `$1`   | Lock row    |

---

# Exchange Rate Example

## Formula

```excel
=K3*$N$2
```

## Behavior

| Reference | Changes? |
| --------- | -------- |
| `K3`      | Yes      |
| `$N$2`    | No       |

---

# Why Absolute References Matter

Without locking:

```excel
=K3*N2
```

Copied version becomes:

```excel
=K4*N3
```

Exchange rate reference shifts incorrectly.

---

# Fast Productivity Shortcut

## Lock References Quickly

Press:

```text
F4
```

After selecting a reference.

## F4 Cycles Through

| Press | Result |
| ----- | ------ |
| 1     | `$A$1` |
| 2     | `A$1`  |
| 3     | `$A1`  |
| 4     | `A1`   |

---

# Formula Copy Workflow

## Recommended Process

1. Create formula in first row
2. Test calculation manually
3. Verify references
4. Lock constants using `F4`
5. Use AutoFill
6. Spot-check copied rows

---

# Automatic Recalculation

Excel automatically recalculates when:

* Values change
* Workbook opens
* Linked formulas update

---

# Calculation Modes

## Navigation

```text
Formulas → Calculation Options
```

| Mode      | Use              |
| --------- | ---------------- |
| Automatic | Normal workbooks |
| Manual    | Large/slow files |

---

# Manual Mode Warning

If calculation mode is Manual:

* Reports may show old numbers
* Dashboards may be incorrect
* Exports may contain stale data

Always refresh before:

* Saving
* Publishing
* Reporting

---

# Common Formula Mistakes

## 1. Missing Parentheses

Wrong:

```excel
=2+3*4
```

---

## 2. Wrong Reference Type

Wrong:

```excel
=A1*B1
```

When B1 should remain fixed.

---

## 3. Hardcoding Rates

Avoid:

```excel
=A1*0.15
```

Better:

```excel
=A1*$F$1
```

---

# Analyst Best Practices

## Build Flexible Models

Prefer:

* Cell references
* Dynamic formulas
* Centralized rates
* Reusable logic

Avoid:

* Hardcoded numbers
* Hidden calculations
* Overly complex formulas

---

# PL-300 Focus

## Important Topics

* Formula precedence
* Relative vs absolute references
* Formula auditing
* Calculation performance
* Spreadsheet reliability

---

# Quick Revision

```text
1. Excel follows precedence rules
2. * and / execute before + and -
3. Parentheses control execution order
4. Relative references change when copied
5. Absolute references stay fixed
6. Use F4 to lock references quickly
7. Test formulas before autofill
```

---

# Mini Practice

## Practice 1

Predict result:

```excel
=10+5*2
```

---

## Practice 2

Force Excel to add first:

```excel
=(10+5)*2
```

---

## Practice 3

Create currency conversion formula:

```excel
=Amount*$B$1
```

Where:

* `Amount` changes
* Exchange rate remains fixed

---

# Most Important Takeaway

Reliable Excel models depend on:

* Correct formula logic
* Proper parentheses
* Correct reference locking
* Safe formula copying
* Careful recalculation management
