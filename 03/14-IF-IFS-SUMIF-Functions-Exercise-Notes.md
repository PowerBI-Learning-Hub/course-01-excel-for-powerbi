# IF, IFS, and SUMIF Functions — Sales Quotation Worksheet

## Core Idea

Use logical functions to:

* Apply discounts automatically
* Calculate delivery charges by region
* Generate regional sales totals
* Create dynamic business reports

Functions covered:

* `IF`
* `IFS`
* `SUMIF`

---

# Sample Dataset — Contoso Bikes Order Details

| Product    | Qty | Unit Price | Subtotal | Discount | Region | Final Total | Delivery | Grand Total |
| ---------- | --: | ---------: | -------: | -------: | ------ | ----------: | -------: | ----------: |
| Bike Frame |  12 |        950 |    11400 |          | A      |             |          |             |
| Helmet     |  25 |        120 |     3000 |          | B      |             |          |             |
| Tires      |  40 |        180 |     7200 |          | C      |             |          |             |
| Gloves     | 100 |         45 |     4500 |          | A      |             |          |             |

---

# Delivery Charge Table

| Region | Delivery Charge |
| ------ | --------------: |
| A      |             150 |
| B      |             250 |
| C      |             350 |

---

# Business Requirements

Adventure Works needs:

* 10% discount if subtotal > 10,000
* Delivery charge based on region
* Sales totals by region
* Final customer quotation

---

# Step 1 — Apply Discount Using IF

## Rule

* If subtotal > 10,000

  * Apply 10% discount
* Otherwise

  * No discount

---

# IF Formula

```excel id="5v7x2n"
=IF(G7>10000,10%,0)
```

---

# Formula Breakdown

| Part       | Meaning              |
| ---------- | -------------------- |
| `G7>10000` | Check subtotal       |
| `10%`      | Discount if TRUE     |
| `0`        | No discount if FALSE |

---

# Sample Result

| Subtotal | Discount |
| -------- | -------: |
| 11400    |      10% |
| 3000     |       0% |

---

# Step 2 — Delivery Charges Using IFS

## Business Rule

| Region | Delivery |
| ------ | -------: |
| A      |      150 |
| B      |      250 |
| C      |      350 |
| Other  |        0 |

---

# IFS Formula

```excel id="9r3m5k"
=IFS(
J7="A",$D$2,
J7="B",$D$3,
J7="C",$D$4,
TRUE,0
)
```

---

# Why TRUE,0?

Acts as:

```excel id="7q2w8t"
Else → 0
```

Prevents:

```excel id="2p6x4v"
#N/A
```

errors.

---

# Important Observation

## Text Conditions Need Quotes

Correct:

```excel id="4k1m9x"
J7="A"
```

Wrong:

```excel id="8z5r2c"
J7=A
```

---

# Step 3 — Calculate Grand Total

## Formula

Add:

* Final total
* Delivery charge

---

# Formula

```excel id="3n8v1q"
=K7+L7
```

---

# Sample Result

| Final Total | Delivery | Grand Total |
| ----------- | -------: | ----------: |
| 10260       |      150 |       10410 |

---

# Step 4 — Autofill Formulas

## Fastest Method

1. Select formula cells
2. Hover over fill handle
3. Double-click fill handle

Excel copies formulas automatically.

---

# Step 5 — Regional Totals Using SUMIF

---

# Region A Total

```excel id="6x4m7w"
=SUMIF(J7:J16,"A",K7:K16)
```

---

# Region B Total

```excel id="2w8q5r"
=SUMIF(J7:J16,"B",K7:K16)
```

---

# Region C Total

```excel id="5c1v9n"
=SUMIF(J7:J16,"C",K7:K16)
```

---

# SUMIF Breakdown

| Argument | Purpose         |
| -------- | --------------- |
| `J7:J16` | Region column   |
| `"A"`    | Condition       |
| `K7:K16` | Values to total |

---

# Practical Workflow

## Step 1 — Build Raw Dataset

Include:

* Product
* Quantity
* Prices
* Regions

---

## Step 2 — Add Business Rules

Examples:

* Discount thresholds
* Delivery regions
* Bonus structures

---

## Step 3 — Create Logic Columns

Use:

* IF
* IFS
* SUMIF

---

## Step 4 — Autofill

Copy formulas across full dataset.

---

## Step 5 — Validate Results

Cross-check:

* Discount rows
* Delivery charges
* Regional totals

---

# Common Mistakes

## Missing Absolute References

Wrong:

```excel id="1v4m7p"
D2
```

Correct:

```excel id="9q3x6w"
$D$2
```

---

## Missing Quotes Around Text

Wrong:

```excel id="7k2v8r"
J7=A
```

Correct:

```excel id="0n5w3m"
J7="A"
```

---

## Forgetting TRUE in IFS

Without:

```excel id="4r9m1x"
TRUE,0
```

Formula may return:

```excel id="6w2q7p"
#N/A
```

---

# Productivity Tips

## Use Named Ranges

Example:

```excel id="3m7x2q"
=SUMIF(Region,"A",Sales)
```

Cleaner formulas.

---

## Store Lookup Tables Separately

Makes updates easier.

---

## Keep Business Rules Flexible

Avoid hardcoding everywhere.

---

# Analyst Use Cases

## Sales

* Discount automation
* Territory analysis

## Finance

* Invoice calculations
* Regional revenue

## Operations

* Shipping cost calculations

## Reporting

* Dynamic dashboards

---

# Quick Revision

## IF

```excel id="5x2v8q"
=IF(Test,TrueValue,FalseValue)
```

---

## IFS

```excel id="7m4w1p"
=IFS(
Test1,Result1,
Test2,Result2,
TRUE,DefaultResult
)
```

---

## SUMIF

```excel id="2n6q9v"
=SUMIF(range,criteria,sum_range)
```

---

# Best Practice

* Use `IFS` instead of deeply nested IFs.
* Always use absolute references for lookup tables.
* Keep logic readable and scalable.
* Separate business rules from transaction data for easier maintenance.
