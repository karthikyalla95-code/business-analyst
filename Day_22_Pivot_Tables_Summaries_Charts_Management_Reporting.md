# TechPhile.ai — Business Analyst Career Pathway

# Day 22: Pivot Tables, Summaries, Charts and Management Reporting

**Phase:** 4 — Data Analysis for Business Decisions  
**Estimated learning time:** 2–3 hours  
**Difficulty:** Beginner to Intermediate  
**Prerequisites:** Day 19 requirements documentation; basic computer and spreadsheet familiarity.

## Learning objectives
1. Prepare a flat, analysis-ready table.
2. Build a PivotTable and place fields in Rows, Columns, Values and Filters.
3. Summarize counts, sums and averages correctly.
4. Select charts that fit the business question.
5. Design a concise management dashboard.
6. Write insight statements that distinguish observation from recommendation.

## 1. Why this matters
Managers rarely need 5,000 raw rows. They need answers: Which region has the most late orders? Is sales performance improving? Which category needs attention? PivotTables turn detailed records into summaries; charts make patterns easier to see.

## 2. Terms
- PivotTable: interactive summary of a source table.
- Rows: categories displayed vertically.
- Columns: categories displayed horizontally.
- Values: numbers summarized using sum, count, average, etc.
- Filters/slicers: controls to focus the report.
- Aggregation: combining records into a summary.
- Dashboard: compact view of key metrics and trends.
- Refresh: recalculate a PivotTable after source data changes.
- Chart: visual representation of values.
- Insight: evidence-based interpretation relevant to a decision.

## 3. Prepare the source
A PivotTable works best with one header row, no merged cells, one record per row, consistent data types and no blank header names. Convert the range into an Excel Table (Insert → Table) so new rows can be included more easily. Confirm the grain before summarizing.

Example source:
| Order_ID | Region | Category | Status | Sales |
|---|---|---|---|---:|
| 1 | East | Home | Delivered | 500 |
| 2 | West | Tech | Pending | 900 |
| 3 | East | Tech | Delivered | 700 |
| 4 | North | Home | Late | 300 |
| 5 | West | Home | Delivered | 600 |

## 4. Build a PivotTable (Excel)
1. Click a cell in the clean source table.
2. Choose Insert → PivotTable.
3. Confirm the table/range and choose New Worksheet.
4. Drag Region to Rows.
5. Drag Sales to Values; confirm it says Sum of Sales, not Count.
6. Drag Status to Columns to compare statuses.
7. Add Category to Filters if needed.
8. Use Refresh after source updates.

Expected regional sales:
- East: 1,200
- West: 1,500
- North: 300
- Grand total: 3,000

If Excel shows Count of Sales, the source values may be stored as text. Correct the source data and refresh.

## 5. Choose the right aggregation
| Question | Aggregation |
|---|---|
| How many orders? | Count of Order_ID |
| Total sales? | Sum of Sales |
| Average order value? | Average of order-level value |
| How many late orders? | Count filtered to Late |
| On-time percentage? | Calculate eligible on-time count / eligible total × 100 |

Be careful with averages. Average of order-level values is not the same as total sales divided by number of line items if the grain differs.

## 6. Charts: match visual to question
| Business question | Useful chart | Avoid |
|---|---|---|
| Trend over time | Line chart | Pie chart |
| Compare categories | Bar/column chart | 3D chart |
| Share of a small whole | Pie/doughnut with few categories | Many tiny slices |
| Actual vs target | Bar or bullet-style comparison | Decorative gauge |
| Relationship between two numeric variables | Scatter plot | Stacked bar without reason |

Good chart habits:
- Use clear title and units.
- Label axes and time period.
- Sort categories when ranking.
- Keep colours consistent and accessible.
- Avoid 3D effects and unnecessary decoration.
- Show target/baseline where useful.
- Do not imply causation from a simple correlation.

## 7. Management reporting: observation → interpretation → action
Example:
- Observation: West generated 1,500 of 3,000 sales (50%).
- Interpretation: West is the largest sales region in this sample.
- Action: Review whether West's practices can be replicated; check margin and delivery quality before scaling.

A dashboard should answer:
1. What is happening?
2. Where is it happening?
3. Why might it be happening?
4. What decision is needed?

## 8. Follow-along summary
Use the sample table:
- Put Region in Rows.
- Put Sales in Values (Sum).
- Put Status in Columns.
- Add a chart to compare sales by region.
Expected total = 3,000.
Then filter Status to Delivered and note that the total changes. Record the filter in the report so readers understand the population.

## 9. Common mistakes
| Mistake | Fix |
|---|---|
| Count instead of Sum | Check source numeric types and Value Field Settings |
| New rows not included | Use an Excel Table and refresh |
| Wrong average | Confirm row grain and definition |
| Too many chart types | Use visuals that answer a question |
| No filter context | Display selected date/region/status |
| Dashboard overloaded | Keep only decision-relevant KPIs |
| Chart hides denominator | Show counts alongside rates where useful |

## 10. Interview revision
- PivotTables summarize records without manually writing many formulas.
- Rows/Columns define grouping; Values define aggregation; Filters narrow the population.
- Refresh updates the PivotTable from changed source data.
- Line charts show trends; bars compare categories.
- Management reporting should connect evidence to a decision.

### Interview questions
**Q1. How would you create a management dashboard from raw order data?**  
I would define the business questions and KPI definitions, inspect and clean the source, confirm its grain, build PivotTables for the required summaries, choose charts suited to each question, show targets and filters, validate totals against the source, and add concise insight/action notes.

**Q2. Why might a PivotTable show Count instead of Sum?**  
The values may be stored as text or contain non-numeric entries. I would inspect the source, convert values correctly, refresh the PivotTable and confirm the aggregation.

**Q3. What makes a dashboard useful to managers?**  
It highlights a small number of relevant measures, makes trends and exceptions visible, states the period and filters, and helps a manager decide what action to take.

## 11. Mini-project — Business Performance Dashboard
**Time:** 60–75 minutes.

Workspace:
```text
Day_22_Business_Performance_Dashboard/
├── README.md
├── inputs/
│   └── sales_data.csv
├── pivot_summary.xlsx
├── dashboard.xlsx
└── insight_notes.md
```

Starter data:
```csv
Order_ID,Order_Date,Region,Category,Channel,Status,Sales
O1,2026-09-01,East,Home,Online,Delivered,500
O2,2026-09-02,West,Tech,Store,Pending,900
O3,2026-09-03,East,Tech,Online,Delivered,700
O4,2026-09-04,North,Home,Online,Late,300
O5,2026-09-05,West,Home,Store,Delivered,600
O6,2026-09-06,South,Tech,Online,Late,800
O7,2026-09-07,East,Home,Store,Pending,400
O8,2026-09-08,West,Tech,Online,Delivered,1000
```

Tasks:
1. Import the data and verify types and row count.
2. Create PivotTable: sales by region.
3. Create PivotTable: order count by status.
4. Create PivotTable: sales by category and channel.
5. Add at least two charts with titles and units.
6. Put at least three KPIs at the top of a dashboard.
7. Write three evidence-based insights and one recommended action for each.
8. State limitations: the sample is small and only covers eight orders.

Expected checks:
- Total sales = 5,200.
- Order count = 8.
- East sales = 1,600; West = 2,500; North = 300; South = 800.
- Delivered orders = 4; Pending = 2; Late = 2.

Checker:
- [ ] Source is a clean table with headers.
- [ ] Pivot summaries reconcile to source totals.
- [ ] Sales is summarized as Sum.
- [ ] Order_ID is counted for order volume.
- [ ] At least two appropriate charts exist.
- [ ] Period and filters are visible.
- [ ] Insights cite values from the summaries.
- [ ] Recommendations do not claim causation without evidence.
- [ ] Limitations are documented.

Hints: If your total is not 5,200, inspect whether every row is included and Sales is numeric. If regional values differ, check filters and source range. For a trend chart, group dates by week/month only when the date range supports it.

Extension: Add a target column and compare regional sales against an agreed target; clearly mark targets as illustrative if they are not business-approved.

## 12. Knowledge check
1. Where do numeric summaries go in a PivotTable? A) Rows B) Values C) Filters only D) Sheet tabs. **Answer: B**.
2. Best chart for monthly trend? A) Line B) Pie C) 3D doughnut D) Map by default. **Answer: A**.
3. Why refresh a PivotTable? A) Change font B) Include updated source data C) Delete filters D) Rename workbook. **Answer: B**.
4. What should be checked if Sum becomes Count? A) Numeric data type B) Screen size C) Chart title D) Workbook colour. **Answer: A**.
5. Which is an insight? A) “There are 8 rows” B) “West has the highest sample sales at 2,500; investigate whether this is repeatable” C) “The chart is blue” D) “Excel is open”. **Answer: B**.

## 13. Assessment and bridge
Complete Day 22 when the dashboard reconciles to source data, uses suitable charts, clearly states its filters and period, and includes evidence-based insight notes.

**Bridge to Day 23:** Excel supports quick analysis. Next, use SQL to retrieve and aggregate business data directly from relational databases.


---

## Visual references to add manually

### 1. PivotTable field list and layout areas
- **Filename:** `day_22_concept_01_excel_pivottable_field_areas.png`
- **Insert under heading:** `## 4. Build a PivotTable (Excel)`
- **What it should show:** The PivotTable Fields pane and the four drop zones: Filters, Columns, Rows and Values.
- **Search phrase:** `Excel PivotTable Fields pane Filters Columns Rows Values screenshot`
- **Reference:** [Nexacu — PivotTable fields pane](https://nexacu.com.au/insights-blog/pivot-tables-in-excel-complete-tutorial/)

*Image note: prefer a genuine Excel screenshot with the four areas clearly labelled. Check reuse terms before copying.*
