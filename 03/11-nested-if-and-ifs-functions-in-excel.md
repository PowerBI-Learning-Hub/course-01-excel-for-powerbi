# Nested IF and IFS Functions in Excel

## Core Idea

* Use **Nested IF** when you need multiple conditions inside one formula.
* Use **IFS** when checking many conditions in sequence without nesting.
* Both functions help automate decision-making in reports and dashboards.

---

# Sample Dataset — Sales Bonus Calculation

| Employee    | Monthly Sales | Target | Above Target | Bonus |
| ----------- | ------------: | -----: | -----------: | ----: |
| Olivia King |        58,000 | 40,000 |       18,000 |       |
| Mason Reed  |        72,000 | 45,000 |       27,000 |       |
| Sophia Hall |        49,000 | 42,000 |        7,000 |       |
| Ethan Clark |        61,000 | 50,000 |       11,000 |       |
| Ava Scott   |        83,000 | 55,000 |       28,000 |       |

---

# Bonus Band Table

| Above Target Amount | Bonus |
| ------------------- | ----: |
| >= 20,000           | 2,000 |
| >= 10,000           | 1,000 |
| Below 10,000        |   500 |

---

# Business Goal

Adventure Works wants to:

* Check employee sales performance.
* Assign bonus amount automatically.
* Avoid manual bonus calculations.

---

# Understanding Nested IF

## Logic Flow

Excel checks conditions one-by-one.

### Example Logic

```excel
If Above Target >= 20000 → Bonus 2000
Else If Above Target >= 10000 → Bonus 1000
Else → Bonus 500
```

---

# Nested IF Formula

## Formula

```excel
=IF(E2>=20000,$J$3,IF(E2>=10000,$J$4,$J$5))
```

## Formula Breakdown

| Part                      | Meaning                       |
| ------------------------- | ----------------------------- |
| `E2>=20000`               | First test                    |
| `$J$3`                    | Return bonus 2000             |
| `IF(E2>=10000,$J$4,$J$5)` | Second IF if first test fails |

---

# Sample Result

| Employee    | Above Target | Bonus |
| ----------- | -----------: | ----: |
| Olivia King |       18,000 | 1,000 |
| Mason Reed  |       27,000 | 2,000 |
| Sophia Hall |        7,000 |   500 |

---

# IFS Function

## Why Use IFS?

* Cleaner than deeply nested IFs.
* Easier to read and maintain.
* Best for multiple conditions.

---

# IFS Formula

```excel
=IFS(
E2>=20000,$J$3,
E2>=10000,$J$4,
TRUE,$J$5
)
```

---

# Important Observation About TRUE

```excel
TRUE,$J$5
```

Acts like:

```excel
Else → 500
```

Without TRUE:

* Excel may return `#N/A`
* Happens when no condition matches.

---

# Practical Workflow

## Step 1 — Prepare Data

Keep:

* Sales
* Target
* Difference/Above Target

in separate columns.

---

## Step 2 — Create Bonus Bands

Store bonus bands separately.

Example:

| J Column | K Column |
| -------- | -------- |
| 20000    | 2000     |
| 10000    | 1000     |
| 0        | 500      |

---

## Step 3 — Write Formula

Use:

* Nested IF
  OR
* IFS

---

## Step 4 — Lock Bonus References

Use:

```excel
$J$3
```

instead of:

```excel
J3
```

Prevents broken references during Autofill.

---

## Step 5 — Autofill Formula

Double-click fill handle to copy down entire column.

---

# Common Mistakes

## Missing Parentheses

Wrong:

```excel
=IF(E2>=20000,J3,IF(E2>=10000,J4,J5)
```

Correct:

```excel
=IF(E2>=20000,J3,IF(E2>=10000,J4,J5))
```

---

## Forgetting Absolute References

Wrong:

```excel
J3
```

Correct:

```excel
$J$3
```

---

## Incorrect Condition Order

Always test:

* highest value first
* lowest value last

Wrong order can return incorrect bonuses.

---

# Nested IF vs IFS

| Feature              | Nested IF | IFS     |
| -------------------- | --------- | ------- |
| Readability          | Harder    | Easier  |
| Multiple Conditions  | Yes       | Yes     |
| Older Excel Versions | Supported | Limited |
| Easier Debugging     | No        | Yes     |

---

# Productivity Tips

## Use Formula Bar

Better visibility for long formulas.

---

## Indent Long IFS Formulas

Makes debugging easier.

Example:

```excel
=IFS(
E2>=20000,$J$3,
E2>=10000,$J$4,
TRUE,$J$5
)
```

---

## Test Conditions Individually

Before combining:

```excel
=E2>=20000
```

Should return:

```excel
TRUE or FALSE
```

---

# Analyst Use Cases

## Sales Bonus Systems

* Commission calculations
* Incentive plans

## HR

* Employee grading
* Salary bands

## Finance

* Tax brackets
* Risk scoring

## Operations

* SLA status
* Performance categories

---

# Quick Revision

## Nested IF Syntax

```excel
=IF(Test1,Result1,IF(Test2,Result2,ElseResult))
```

---

## IFS Syntax

```excel
=IFS(
Test1,Result1,
Test2,Result2,
TRUE,DefaultResult
)
```

---

## Key Functions Covered

* IF
* Nested IF
* IFS
* TRUE

---

# Best Practice

* Use **IFS** for cleaner formulas.
* Use **Nested IF** for compatibility with older Excel versions.
* Always test formulas with sample values before Autofill.
