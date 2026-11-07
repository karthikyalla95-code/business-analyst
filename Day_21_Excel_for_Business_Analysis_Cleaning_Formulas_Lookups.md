# TechPhile.ai — Business Analyst Career Pathway

# Day 21: Excel for Business Analysis — Cleaning, Formulas and Lookups

**Phase:** 4 — Data Analysis for Business Decisions  
**Estimated learning time:** 2–3 hours  
**Difficulty:** Beginner to Intermediate  
**Prerequisites:** Day 19 requirements documentation; basic computer and spreadsheet familiarity.

## Learning objectives
1. Inspect a worksheet and identify data-quality problems.
2. Clean text, dates, blanks and duplicate records safely.
3. Use relative and absolute cell references.
4. Apply common formulas for business reporting.
5. Use lookup functions to enrich a dataset.
6. Validate totals and document cleaning decisions.

## 1. Why this matters
A BA often receives spreadsheets exported from different systems. Names may have extra spaces, dates may be text, IDs may be duplicated and categories may be inconsistent. A report built on poor data can mislead managers.

Scenario: Operations receives an order export and a product master list. You must clean the order data, attach product categories and calculate order values before reporting.

## 2. Workbook vocabulary
| Term | Meaning |
|---|---|
| Workbook | Excel file containing sheets |
| Worksheet | One tab in a workbook |
| Cell | Intersection of row and column, e.g. B3 |
| Range | Group of cells, e.g. A2:D20 |
| Formula | Expression beginning with = |
| Function | Built-in formula such as SUM |
| Relative reference | Changes when copied, e.g. A2 |
| Absolute reference | Fixed when copied, e.g. $A$2 |
| Table | Structured dataset with headers and filters |
| Lookup | Find a matching key and return related information |
| Data validation | Rule controlling permitted input |
| Duplicate | Repeated record/key requiring investigation |

## 3. Inspect before changing data
1. Keep an untouched copy of the source file.
2. Identify what one row represents (the grain).
3. Check column names and data types.
4. Count rows and inspect blank cells.
5. Check duplicate IDs.
6. Review date range, category spelling and numeric outliers.
7. Record every cleaning rule.

Never delete a duplicate merely because two rows look similar. Confirm whether the row is an accidental duplicate or a legitimate repeated transaction.

## 4. Common cleaning operations
- TRIM: removes leading/trailing and repeated ordinary spaces.
- CLEAN: removes many non-printing characters.
- PROPER: capitalizes words (use cautiously for names/IDs).
- UPPER/LOWER: normalizes case.
- SUBSTITUTE: replaces specified text.
- Remove Duplicates: removes duplicate rows based on selected columns; use a copy and choose key columns carefully.
- Find and Replace: standardizes known category variants.
- Text to Columns: splits delimited text into fields.
- Date conversion: convert text dates using the correct locale/order; verify ambiguous dates such as 03/04/2026.

Examples:
`=TRIM(A2)`
`=CLEAN(A2)`
`=UPPER(TRIM(B2))`
`=IF(C2="","Missing","Present")`

## 5. Essential formulas
| Function | Purpose | Example |
|---|---|---|
| SUM | Add values | =SUM(E2:E100) |
| AVERAGE | Arithmetic mean | =AVERAGE(E2:E100) |
| MIN / MAX | Smallest/largest | =MAX(E2:E100) |
| COUNT | Count numeric cells | =COUNT(E2:E100) |
| COUNTA | Count non-empty cells | =COUNTA(A2:A100) |
| COUNTIF | Count one condition | =COUNTIF(D2:D100,"Delivered") |
| SUMIF | Sum for one condition | =SUMIF(D2:D100,"Delivered",E2:E100) |
| IF | Return result based on condition | =IF(E2>=1000,"High","Standard") |
| IFERROR | Handle formula errors | =IFERROR(A2/B2,0) |
| ROUND | Round a number | =ROUND(F2,2) |
| LEFT/RIGHT/MID | Extract characters | =LEFT(A2,3) |
| TODAY | Current date | =TODAY() |

Use IFERROR thoughtfully: returning 0 for every error can hide data problems. Sometimes “Check source” is safer.

## 6. Cell references
Suppose tax rate is in H1 and net amount is in E2.
- `=E2*$H$1` keeps the tax-rate cell fixed when copied down.
- `=E2*H1` shifts both references when copied and may point to the wrong cell.

Relative references move; absolute references lock row and column. Mixed references such as $A2 or A$2 lock only one part.

## 7. Lookups
A lookup matches a key in one table and returns a related value from another.

Example product master:
| Product_ID | Category |
|---|---|
| P101 | Electronics |
| P102 | Home |

Orders:
| Order_ID | Product_ID | Qty | Unit_Price |
|---|---|---:|---:|
| O1 | P101 | 2 | 500 |
| O2 | P102 | 1 | 800 |

With modern Excel:
`=XLOOKUP(B2,ProductMaster[Product_ID],ProductMaster[Category],"Not found")`

With VLOOKUP:
`=VLOOKUP(B2,$J$2:$K$3,2,FALSE)`
The FALSE argument requests an exact match. VLOOKUP searches the first column of the supplied range and returns a column to its right.

Check unmatched IDs rather than silently accepting “Not found”. Confirm lookup keys have the same data type and no hidden spaces.

## 8. Follow-along calculation
Order line value = quantity × unit price.
If Qty is C2 and Unit_Price is D2:
`=C2*D2`
Copy down. Then:
- Total line value: `=SUM(E2:E3)` → 1800.
- Delivered order count: `=COUNTIF(F2:F3,"Delivered")`.
- Delivered value: `=SUMIF(F2:F3,"Delivered",E2:E3)`.
Expected result depends on the status in the sample rows; verify the filter criteria matches the exact category.

## 9. Common errors
| Error/problem | Likely cause | Fix |
|---|---|---|
| #N/A | Lookup key missing | Check key spelling/type and master data |
| #VALUE! | Wrong data type | Convert text numbers/dates |
| #DIV/0! | Denominator is zero/blank | Define handling and inspect source |
| Formula copied incorrectly | Reference not locked | Use $ absolute references |
| Wrong date | Locale ambiguity | Confirm source format and validate |
| Duplicate count unexpectedly high | Wrong grain/key | Define what one row represents |
| TRIM did not remove odd spaces | Non-breaking spaces | Use SUBSTITUTE with CHAR(160), then TRIM |

## 10. Interview revision
- Preserve raw data and work on a copy.
- Define row grain before deduplication.
- Use exact-match lookups for identifiers.
- Validate lookup coverage and totals.
- Absolute references are useful for fixed rates or parameters.
- Cleaning rules should be documented and repeatable.

### Interview questions
**Q1. How would you clean an operational Excel file?**  
I preserve the raw export, inspect columns and row grain, check blanks and duplicates, standardize text and dates, validate numeric fields, enrich using a reference table, and reconcile row counts and totals. I record each transformation so the result is reproducible.

**Q2. XLOOKUP versus VLOOKUP?**  
Both retrieve a value based on a key. XLOOKUP separates lookup and return ranges and can return a not-found result. VLOOKUP uses a table range and column index and typically searches from its first column to the right. Exact matching should be used for IDs.

**Q3. Why use $ in a formula?**  
It locks a row, column or both when copying formulas. For example, `=E2*$H$1` allows E2 to change down the rows while the rate remains in H1.

## 11. Mini-project — Business Operations Report
**Time:** 45–75 minutes.

Workspace:
```text
Day_21_Business_Operations_Report/
├── README.md
├── inputs/
│   ├── orders_raw.csv
│   └── product_master.csv
├── cleaned_orders.csv
├── operations_summary.xlsx
└── cleaning_log.md
```

Starter data for orders_raw.csv:
```csv
Order_ID,Product_ID,Customer,Qty,Unit_Price,Status,Order_Date
O100,P101,"  Asha ",2,500,Delivered,2026-10-01
O101,P102,"Ravi",1,800,Pending,2026-10-02
O102,P101,"Asha",1,500,Delivered,2026-10-03
O103,P999,"Meera",3,200,Delivered,2026-10-04
O103,P999,"Meera",3,200,Delivered,2026-10-04
```
product_master.csv:
```csv
Product_ID,Category
P101,Electronics
P102,Home
```

Tasks:
1. Import both files and keep the raw inputs unchanged.
2. Standardize customer names with TRIM.
3. Investigate duplicate Order_ID O103; document whether it should be removed. Do not assume without checking.
4. Calculate line value = Qty × Unit_Price.
5. Look up product category; identify P999 as unmatched.
6. Create a summary of order count and line value by status.
7. Write a cleaning log with original issue, action, reason and impact.

Expected evidence: cleaned data, formula evidence, lookup coverage, summary by status, reconciliation of original versus cleaned rows, and a note for unresolved P999.

Checker:
- [ ] Raw input files unchanged.
- [ ] One-row grain documented.
- [ ] Duplicate treatment justified.
- [ ] Text and date fields checked.
- [ ] Line value formula correct.
- [ ] Lookup uses exact match.
- [ ] Unmatched product IDs reported.
- [ ] Summary totals reconcile to cleaned records.
- [ ] Cleaning log records each decision.

Hints: Filter Product_ID for P999; inspect O103 before removing; verify Qty and Unit_Price are numeric. If your Excel version lacks XLOOKUP, use VLOOKUP with FALSE or INDEX/MATCH.

Extension: Add a low-stock flag using a product inventory table and a lookup.

## 12. Knowledge check
1. Which reference locks both row and column? A) A1 B) $A$1 C) A$1 D) $A1. **Answer: B**.
2. Which function counts cells meeting a condition? A) SUM B) COUNTIF C) LEFT D) ROUND. **Answer: B**.
3. What should happen before removing duplicates? A) Delete all repeated names B) Define row grain and duplicate key C) Sort by colour D) Hide rows. **Answer: B**.
4. What does FALSE mean in VLOOKUP? A) Approximate match B) Exact match C) Ignore errors D) Reverse order. **Answer: B**.
5. Why retain raw inputs? A) To avoid documentation B) To preserve source and support audit/rework C) To increase duplicates D) To avoid validation. **Answer: B**.

## 13. Assessment and bridge
Complete Day 21 when you can clean a copy of a dataset, explain each cleaning decision, use core formulas and exact-match lookups, and reconcile totals.

**Bridge to Day 22:** Once the data is reliable, summarize it with PivotTables and communicate patterns through charts and management reporting.
