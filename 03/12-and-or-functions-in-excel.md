# AND and OR Functions in Excel

## Core Idea

* **AND** → All conditions must be TRUE.
* **OR** → At least one condition must be TRUE.
* Commonly combined with:

  * `IF`
  * `IFS`
  * Nested logical formulas
* Used for advanced filtering, performance tracking, validation, and business rules.

---

# Sample Dataset — Sales Performance Review

| Employee    | Sales Q1 | Sales Q2 | Sales Q3 | Status |
| ----------- | -------: | -------: | -------: | ------ |
| Olivia King |      250 |      320 |      290 |        |
| Ethan Clark |      180 |      220 |      210 |        |
| Ava Scott   |      300 |      350 |      400 |        |
| Mason Reed  |      150 |      190 |      170 |        |

---

# Understanding the AND Function

## Purpose

Checks whether **all conditions** are TRUE.

---

# AND Syntax

```excel id="r1x9wa"
=AND(logical_test1, logical_test2, ...)
```

---

# Example 1 — Basic AND Formula

## Business Requirement

Employee must achieve:

* Q1 > 200
* Q2 > 200
* Q3 > 200

## Formula

```excel id="hv7l5o"
=AND(B2>200,C2>200,D2>200)
```

---

# Result Example

| Employee    | Formula Result |
| ----------- | -------------- |
| Olivia King | TRUE           |
| Ethan Clark | FALSE          |
| Ava Scott   | TRUE           |
| Mason Reed  | FALSE          |

---

# How AND Works

| Condition | Result |
| --------- | ------ |
| All TRUE  | TRUE   |
| One FALSE | FALSE  |

---

# Understanding the OR Function

## Purpose

Checks whether **at least one condition** is TRUE.

---

# OR Syntax

```excel id="wr0d8s"
=OR(logical_test1, logical_test2, ...)
```

---

# Example 2 — Basic OR Formula

## Business Requirement

Employee qualifies if:

* Any quarter sales exceed 300.

## Formula

```excel id="f8s9jm"
=OR(B2>300,C2>300,D2>300)
```

---

# OR Result Example

| Employee    | Formula Result |
| ----------- | -------------- |
| Olivia King | TRUE           |
| Ethan Clark | FALSE          |
| Ava Scott   | TRUE           |
| Mason Reed  | FALSE          |

---

# How OR Works

| Condition | Result |
| --------- | ------ |
| One TRUE  | TRUE   |
| All FALSE | FALSE  |

---

# Using AND with IF

## Real Business Scenario

Adventure Works wants:

* Employee status = "On Target"
* Only if ALL quarterly sales exceed 200.

---

# Formula

```excel id="v0p2lx"
=IF(AND(B2>200,C2>200,D2>200),"On Target","Target Not Met")
```

---

# Formula Logic

| Condition          | Output         |
| ------------------ | -------------- |
| All quarters > 200 | On Target      |
| Any quarter <= 200 | Target Not Met |

---

# Result Example

| Employee    | Status         |
| ----------- | -------------- |
| Olivia King | On Target      |
| Ethan Clark | Target Not Met |
| Ava Scott   | On Target      |
| Mason Reed  | Target Not Met |

---

# Using OR with IF

## Scenario

Employee gets attention if:

* Any quarter falls below 180.

---

# Formula

```excel id="d9x0ra"
=IF(OR(B2<180,C2<180,D2<180),"Needs Review","Good")
```

---

# Practical Workflow

## Step 1 — Define Conditions

Clearly identify:

* Thresholds
* Limits
* Required criteria

---

## Step 2 — Choose Correct Function

| Requirement              | Function |
| ------------------------ | -------- |
| All conditions required  | AND      |
| Any condition acceptable | OR       |

---

## Step 3 — Wrap with IF

Use IF to return readable business messages.

Example:

```excel id="5e0vwl"
=IF(AND(...),"Approved","Rejected")
```

---

## Step 4 — Autofill

Copy formula down entire dataset.

---

# Important Observations

## AND is Strict

Even one failed condition returns FALSE.

Example:

```excel id="6s8jow"
=AND(TRUE,TRUE,FALSE)
```

Result:

```excel id="s5vylr"
FALSE
```

---

## OR is Flexible

Only one successful test needed.

Example:

```excel id="tk2v0m"
=OR(FALSE,FALSE,TRUE)
```

Result:

```excel id="m3e4qz"
TRUE
```

---

# Common Mistakes

## Wrong Comparison Operator

Wrong:

```excel id="84r8ql"
=AND(B2=200)
```

Correct:

```excel id="w6fkr0"
=AND(B2>200)
```

---

## Missing Quotes in IF Result

Wrong:

```excel id="vc6i0n"
=IF(AND(B2>200),"Pass",Fail)
```

Correct:

```excel id="d7x2fo"
=IF(AND(B2>200),"Pass","Fail")
```

---

## Confusing AND vs OR

| Wrong Usage                              | Problem                |
| ---------------------------------------- | ---------------------- |
| Using OR when all conditions required    | Too many TRUE results  |
| Using AND when only one condition needed | Too many FALSE results |

---

# Productivity Tips

## Test Logic Separately

Before IF:

```excel id="2ntk2x"
=AND(B2>200,C2>200,D2>200)
```

Then combine with IF.

---

## Use Helper Columns

Large datasets become easier to debug.

---

## Format TRUE/FALSE Columns

Use conditional formatting:

* TRUE → Green
* FALSE → Red

---

# Analyst Use Cases

## HR

* Attendance validation
* Promotion eligibility

## Sales

* Bonus qualification
* KPI achievement

## Finance

* Loan approvals
* Risk checks

## Operations

* SLA tracking
* Quality control

---

# Quick Revision

## AND

```excel id="79m56j"
=AND(Test1,Test2)
```

Returns TRUE only if ALL tests are TRUE.

---

## OR

```excel id="0r4xst"
=OR(Test1,Test2)
```

Returns TRUE if ANY test is TRUE.

---

## IF + AND

```excel id="2f7lx9"
=IF(AND(A2>100,B2>100),"Pass","Fail")
```

---

## IF + OR

```excel id="4t8k0p"
=IF(OR(A2>100,B2>100),"Pass","Fail")
```

---

# Best Practice

* Use **AND** for strict validation.
* Use **OR** for flexible checks.
* Combine with IF for business-friendly outputs.
* Keep formulas readable using indentation and helper columns.
