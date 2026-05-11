````md
# 15-IFS-SUMIFS-Exercise-Exemplar-Notes.md

# IF, IFS & SUMIFS Functions — Exercise Notes

## Overview

This exercise focused on using logical functions in Excel to:

- Apply discounts automatically
- Calculate delivery charges based on region
- Generate region-wise sales totals

Functions used:

- IF
- IFS
- SUMIFS

---

# Sample Dataset

## Delivery Charges

| Region | Charge |
|---|---|
| A | 50 |
| B | 75 |
| C | 100 |

---

## Order Details

| Product | Qty | Unit Price | Subtotal | Region |
|---|---|---|---|---|
| Bike Frame | 15 | 1050 | 15750 | B |
| Helmet | 20 | 450 | 9000 | A |
| Wheels | 25 | 650 | 16250 | C |
| Gloves | 40 | 120 | 4800 | B |

---

# Step 1 — Discount Formula Using IF

## Requirement

- If subtotal > 10000 → apply 10% discount
- Otherwise → 0

---

## Formula

```excel
=IF(G7>10000,10%,0)
```

---

## Result Example

| Subtotal | Discount |
|---|---|
| 15750 | 10% |
| 9000 | 0% |

---

# Step 2 — Delivery Charge Using IFS

## Requirement

Assign delivery charge based on region.

---

## Formula

```excel
=IFS(J7="A",$D$2,J7="B",$D$3,J7="C",$D$4,TRUE,0)
```

---

## Important Notes

- `IFS` checks multiple conditions
- Dollar signs make references absolute
- Text values must use double quotes
- `TRUE,0` acts as default fallback

---

## Example Output

| Region | Delivery Charge |
|---|---|
| A | 50 |
| B | 75 |
| C | 100 |
| Other | 0 |

---

# Step 3 — Final Total Calculation

## Requirement

Add:

- Sales total
- Delivery charge

---

## Formula

```excel
=K7+L7
```

---

## Example

| Sales Total | Delivery | Final Total |
|---|---|---|
| 14175 | 75 | 14250 |

---

# Step 4 — Autofill Formulas

## Fast Method

- Select formulas
- Double-click fill handle
- Copy formulas down automatically

---

## Important Observation

Excel may show:

- Green triangle
- “Inconsistent Formula” warning

This is normal because column H intentionally uses different logic.

Choose:

```text
Ignore Error
```

---

# Step 5 — Region Total Using SUMIFS

## Region A Total

### Formula

```excel
=SUMIFS(K7:K16,J7:J16,"A")
```

### Result

```text
40382.50
```

---

## Region B Total

### Formula

```excel
=SUMIFS(K7:K16,J7:J16,"B")
```

### Result

```text
35100
```

---

## Region C Total

### Formula

```excel
=SUMIFS(K7:K16,J7:J16,"C")
```

### Result

```text
21350
```

---

# Important Formula Pattern

## SUMIFS Syntax

```excel
=SUMIFS(sum_range,criteria_range,criteria)
```

---

# Common Mistakes

| Mistake | Problem |
|---|---|
| Missing quotes around text | Formula error |
| Forgetting dollar signs | Wrong copied results |
| Wrong SUMIFS order | Incorrect totals |
| Using IF instead of IFS | Difficult multiple-condition logic |

---

# Productivity Tips

- Use Autofill double-click shortcut
- Use absolute references for lookup tables
- Keep criteria tables separate
- Use IFS instead of nested IF for readability

---

# Quick Revision

| Function | Purpose |
|---|---|
| IF | Single condition |
| IFS | Multiple conditions |
| SUMIFS | Conditional totals |

---

# Final Result

This exercise demonstrated how analysts use logical functions to:

- Automate discounts
- Apply region-based pricing
- Generate dynamic totals
- Reduce manual calculations

Excel logical functions are heavily used in:

- Sales reports
- Pricing models
- Dashboards
- Financial analysis
- Operational reporting

````
