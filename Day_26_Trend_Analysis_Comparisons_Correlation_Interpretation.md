# TechPhile.ai — Business Analyst Career Pathway

# Day 26: Trend Analysis — Comparisons, Correlation and Interpretation

**Phase:** 4 — Data Analysis for Business Decisions  
**Estimated time:** 2–3 hours  
**Difficulty:** Beginner to Intermediate  
**Prerequisites:** Days 20–25 — KPIs, Excel, pivot tables, SQL and basic statistics.

## Learning objectives

1. Explain trends and distinguish them from seasonality, cycles and irregular variation.
2. Compare performance using MoM, QoQ and YoY calculations.
3. Calculate and interpret a moving average.
4. Read trend charts and identify turning points, volatility and unusual movements.
5. Explain correlation without incorrectly claiming causation.
6. Investigate a business trend and communicate evidence, limitations and recommendations.

## 1. Why trend analysis matters

Imagine an online store reports monthly revenue:

| Month | Revenue (₹ lakh) |
|---|---:|
| January | 10 |
| February | 11 |
| March | 12 |
| April | 9 |
| May | 13 |
| June | 14 |

A manager asks: **“Is our business growing?”**

Looking only at April might suggest revenue is falling. Comparing January and June suggests growth. A Business Analyst examines the full sequence, compares equivalent periods, checks unusual events and explains what the data can and cannot prove.

**Trend analysis** examines a measure over time to understand its general direction and how it changes. It helps answer questions such as:

- Is revenue increasing, decreasing or staying stable?
- Are customer complaints becoming more frequent?
- Is delivery time improving after a process change?
- Did a campaign coincide with a change in conversion?
- Is a recent increase a lasting pattern or a one-time spike?

A trend is evidence about historical movement. It is not automatically a guarantee of future performance.

## 2. Words you need

| Term | Plain-English meaning | Example |
|---|---|---|
| Time series | Measurements recorded in time order | Monthly sales from Jan to Dec |
| Trend | General long-term direction | Revenue gradually increasing |
| Upward trend | Values generally rise over time | Active users grow |
| Downward trend | Values generally fall over time | Defect rate declines |
| Flat/stable trend | No sustained direction | Weekly demand stays near 500 |
| Seasonality | Pattern repeating at regular calendar intervals | Retail sales rise every December |
| Cyclical movement | Longer waves without a fixed calendar repeat | Demand changes with economic conditions |
| Irregular variation | Unexpected movement | A one-off system outage |
| Baseline | Reference value or period | Average complaints before a change |
| Period-over-period | Compare with an earlier period | May vs April |
| Moving average | Average across a rolling group of periods | Average revenue over latest 3 months |
| Correlation | Degree to which two variables move together | Ad spend and website visits |
| Lag | Delay between input and observed outcome | Training affects productivity next month |
| Forecast | Estimate of a future value based on a method and assumptions | Expected demand next month |

### 2.1 Trend vs seasonality vs cycle vs irregular movement

| Component | How it behaves | Business example |
|---|---|---|
| Trend | Persistent direction over time | Annual active customers grow |
| Seasonality | Repeats at a known interval | More orders every weekend |
| Cycle | Longer waves, duration not fixed | Demand rises and falls with economic conditions |
| Irregular | Unplanned, non-repeating disturbance | Flood, outage, strike or policy change |

A seasonal peak is not necessarily growth. If sales rise every December and fall every January, compare December with previous Decembers as well as November.

## 3. Choose the correct time grain and comparison

Before calculating, define the metric, time grain, period boundary, population, unit and data completeness. For example, are you measuring completed orders or all order attempts? Is the period a calendar month or a rolling 30-day window? Is the latest period complete?

Daily data may be too noisy for a management trend. Monthly aggregation can reveal direction but may hide a short-lived operational problem. Match the time grain to the business question.

### 3.1 MoM, QoQ and YoY

- **MoM:** Current month compared with the previous month. Useful for short-term movement, but affected by seasonality and month length.
- **QoQ:** Current quarter compared with the previous quarter. Useful for quarterly planning, but may still be seasonal.
- **YoY:** Current period compared with the same period one year earlier. Often useful when recurring seasonal effects exist.

### 3.2 Formulas

Absolute Change = Current Value − Previous Value

Percentage Change = ((Current Value − Previous Value) / Previous Value) × 100

Example: April revenue is ₹12 lakh and May revenue is ₹15 lakh.

- Absolute change = 15 − 12 = ₹3 lakh.
- Percentage change = (15 − 12) / 12 × 100 = 25%.
- Interpretation: May revenue was 25% higher than April.

If the previous value is zero, percentage change is undefined. Do not divide by zero or invent a percentage. Explain that a different baseline is needed.

If revenue falls from ₹20 lakh to ₹18 lakh, the percentage change is (18 − 20) / 20 × 100 = −10%. State the direction in words.

## 4. Worked example: monthly sales

| Month | Sales (₹ lakh) | Change | MoM change |
|---|---:|---:|---:|
| January | 10 | — | — |
| February | 12 | +2 | +20.0% |
| March | 11 | −1 | −8.3% |
| April | 13 | +2 | +18.2% |
| May | 15 | +2 | +15.4% |
| June | 14 | −1 | −6.7% |

A responsible BA summary:

- Sales increased from ₹10 lakh in January to ₹14 lakh in June.
- The endpoint increase is ₹4 lakh, or 40% relative to January.
- Sales did not rise every month: March and June declined from the preceding month.
- Six observations are not enough to establish a reliable long-term pattern or seasonality.
- Check order volume, average order value, returns, discounts and channel mix before explaining the movement.

**Do not say:** “The marketing campaign caused sales to grow.” The table contains sales only; it does not establish the cause.

## 5. Moving averages: smooth short-term noise

A moving average replaces a value with the average of a fixed number of nearby observations. The window moves forward one period at a time. It helps reveal the underlying direction when individual observations fluctuate.

### 5.1 Three-period moving average

| Month | Orders |
|---|---:|
| January | 100 |
| February | 120 |
| March | 110 |
| April | 130 |
| May | 150 |
| June | 140 |

First 3-month moving average, for March: (100 + 120 + 110) / 3 = 110.

Next 3-month moving average, for April: (120 + 110 + 130) / 3 = 120.

| Month represented | Calculation | 3-month moving average |
|---|---|---:|
| March | (100 + 120 + 110) / 3 | 110.00 |
| April | (120 + 110 + 130) / 3 | 120.00 |
| May | (110 + 130 + 150) / 3 | 130.00 |
| June | (130 + 150 + 140) / 3 | 140.00 |

The moving average rises from 110 to 140. It smooths small fluctuations and reveals an upward pattern.

**Limitations:** A moving average reacts slowly to sudden changes and cannot be calculated for the first periods until enough observations exist. A 3-period window is not automatically best; choose a window that fits the business cycle and data frequency.

### 5.2 Excel moving average

If monthly orders are in column B, rows 2–7:

1. In C4, enter the formula **=AVERAGE(B2:B4)**.
2. Press Enter. The first result should be 110.
3. Copy the formula down to C7.
4. Confirm the remaining results are 120, 130 and 140.
5. Label column C as 3-month moving average.

The range shifts as the formula is copied down: B2:B4, then B3:B5, then B4:B6.

## 6. Trend charts and visual interpretation

A line chart is often a useful first view of a time series. When reading a chart, check direction, magnitude, duration, volatility, turning points, outliers, seasonality and relevant business events.

### 6.1 Avoid misleading charts

- Keep the time axis chronological.
- Label units and date ranges.
- Do not use a truncated axis without marking it; it can exaggerate small differences.
- Do not connect missing periods as if data were observed.
- Distinguish actual values from moving averages or forecasts.
- Avoid comparing different units on one axis.
- State whether the latest period is partial.

A chart helps reveal a pattern; it does not explain why the pattern happened.

## 7. Correlation: do two measures move together?

**Correlation** describes the direction and strength of association between two numeric variables.

Examples include advertising spend and website visits, open support tickets and resolution time, training hours and assessment scores, and delivery distance and delivery time.

The Pearson correlation coefficient, written as r, ranges from −1 to +1.

| Approximate r | Interpretation |
|---:|---|
| +1 | Perfect positive linear association |
| Near +0.7 | Strong positive linear association (context matters) |
| 0 | No linear association |
| Near −0.7 | Strong negative linear association (context matters) |
| −1 | Perfect negative linear association |

These labels are rough guides. Meaning depends on domain, sample size, data quality, shape of the relationship and outliers. A correlation near zero does not rule out a nonlinear relationship.

- **Positive:** As X increases, Y tends to increase.
- **Negative:** As X increases, Y tends to decrease.
- **No linear correlation:** A straight-line relationship is not evident.

A scatter plot helps inspect two numeric variables. Look for direction, spread, clusters and unusual points before interpreting a coefficient.

### 7.1 Correlation does not prove causation

Suppose ice-cream sales and swimming-pool visits both increase in summer. It would be incorrect to conclude that buying ice cream causes people to visit a pool. A third factor — hot weather — may influence both.

Other possible confounders include seasonality, holidays, marketing campaigns, price changes, product or customer mix, staffing, capacity and changes in data collection.

A BA should say **“the measures moved together in this dataset”**, not **“X caused Y”**, unless a suitable causal study supports that conclusion.

### 7.2 Questions before reporting correlation

1. Were both variables measured over the same periods and population?
2. Are there enough observations?
3. Is one unusual point driving the result?
4. Is the relationship linear or curved?
5. Could seasonality or a third variable explain it?
6. Could the direction be reversed?
7. Is there a plausible time lag?
8. Is the relationship meaningful to the business?

## 8. Practical trend-analysis workflow

| Step | What the BA does | Output |
|---|---|---|
| 1. Define question | Clarify metric and decision needed | Analysis question |
| 2. Define metric | Confirm formula, unit, population and exclusions | Metric definition |
| 3. Collect data | Retrieve comparable historical periods | Source dataset |
| 4. Validate | Check duplicates, missing periods and changed definitions | Data quality notes |
| 5. Explore | Plot the time series and inspect unusual points | Trend chart |
| 6. Compare | Calculate MoM, QoQ or YoY | Comparison table |
| 7. Smooth | Calculate a moving average if useful | Smoothed series |
| 8. Investigate | Check segments, events and related variables | Findings and hypotheses |
| 9. Interpret | Separate facts from possible explanations | Evidence-based summary |
| 10. Recommend | Propose action and how to measure it | Recommendation and follow-up KPI |

### 8.1 Data validation checklist

- [ ] Dates use a consistent format and time zone where relevant.
- [ ] Periods are sorted chronologically.
- [ ] Duplicate records do not inflate the measure.
- [ ] Missing periods are identified, not silently treated as zero.
- [ ] The latest period is complete or marked partial.
- [ ] KPI definition did not change during the comparison window.
- [ ] Units and currencies are consistent.
- [ ] Filters and exclusions are documented.
- [ ] Extreme values are investigated, not automatically removed.
- [ ] Source and extraction date are recorded.

A missing value is not necessarily zero. No sales because a store was closed is different from sales data that failed to load.

## 9. Excel practice

Assume a worksheet contains Month in column A, Revenue in column B, Absolute change in column C, MoM percentage change in column D and 3-month moving average in column E.

| Cell | Formula | Purpose |
|---|---|---|
| C3 | =B3-B2 | Absolute change |
| D3 | =IFERROR((B3-B2)/B2,"N/A") | MoM percentage change |
| E4 | =AVERAGE(B2:B4) | First 3-month average |

Format column D as Percentage. Copy formulas down where applicable. IFERROR prevents a divide-by-zero error from appearing as a misleading numeric result. In a real report, explain why the percentage is unavailable.

## 10. SQL practice: aggregate data by month

Suppose an orders table contains order_id, order_date, order_amount and status.

PostgreSQL example:

~~~sql
SELECT
    DATE_TRUNC('month', order_date) AS sales_month,
    SUM(order_amount) AS monthly_revenue,
    COUNT(*) AS completed_orders
FROM orders
WHERE status = 'Completed'
GROUP BY DATE_TRUNC('month', order_date)
ORDER BY sales_month;
~~~

Explanation:

- DATE_TRUNC groups dates into calendar months.
- SUM calculates total completed-order value.
- COUNT counts rows remaining after the filter.
- WHERE excludes orders that are not completed.
- GROUP BY produces one result per month.
- ORDER BY displays months chronologically.

Confirm whether cancelled, refunded or partially refunded orders need separate treatment. This example is not a universal revenue-recognition definition.

## 11. Worked business interpretation

A subscription company shares this illustrative dataset:

| Month | New subscribers |
|---|---:|
| Jan | 200 |
| Feb | 220 |
| Mar | 210 |
| Apr | 250 |
| May | 270 |
| Jun | 260 |

A responsible BA summary:

> New subscribers increased from 200 in January to 260 in June, an endpoint increase of 30%. The series shows an overall upward movement, although March and June were lower than the preceding months. The six-month dataset is too short to establish seasonality or a dependable long-term forecast. I recommend checking acquisition channel, marketing spend, cancellations and conversion rate by month before attributing the increase to a specific initiative.

A strong summary states the metric and period, quantifies movement, mentions exceptions, states what cannot yet be concluded and recommends the next analysis.

## 12. Common mistakes and fixes

| Mistake | Why it is a problem | Better approach |
|---|---|---|
| Comparing December with November only | Seasonal effects may distort the result | Also compare with previous December |
| Calling one increase a trend | One point may be random noise | Inspect a longer sequence |
| Using different KPI definitions | Comparison is not like-for-like | Confirm definitions |
| Treating missing data as zero | Creates false drops | Mark missing periods and investigate |
| Ignoring a partial current month | Understates current period | Compare complete periods or label partial data |
| Claiming correlation proves cause | Association alone cannot establish causality | Investigate confounders |
| Choosing a moving-average window arbitrarily | Can hide important changes | Match window to business cycle |
| Forecasting far beyond the data | Uncertainty grows with horizon | State assumptions and validate |
| Reporting only percentages | Small bases can create large percentages | Include absolute values and baseline |
| Ignoring segments | Aggregate trend can hide opposing movements | Break down by region, channel or product |

## 13. Mini-project — Trend Investigation Report

**Estimated time:** 45–75 minutes  
**Objective:** Analyze monthly business data, calculate changes and moving averages, inspect a related variable, and write a careful management summary.

### 13.1 Scenario

An online retailer's operations manager wants to know whether monthly completed orders are improving and whether higher advertising spend appears alongside higher order volume.

This is synthetic practice data, not actual company performance.

### 13.2 Workspace

~~~text
Day_26_Trend_Investigation_Report/
├── README.md
├── inputs/
│   └── monthly_performance.csv
├── analysis.xlsx
└── findings.md
~~~

- monthly_performance.csv is read-only starter data.
- analysis.xlsx is your working analysis.
- findings.md is your management report.
- Do not overwrite the original input data.

### 13.3 Starter data

~~~csv
Month,Completed_Orders,Ad_Spend_INR,Website_Visits
2026-01,1000,50000,20000
2026-02,1100,52000,21500
2026-03,1050,51000,21000
2026-04,1200,60000,23000
2026-05,1350,65000,25000
2026-06,1300,64000,24500
2026-07,1450,70000,27000
2026-08,1500,72000,28000
~~~

### 13.4 Tasks

1. Import the CSV into Excel or Google Sheets.
2. Confirm there are 8 monthly records and dates are chronological.
3. Calculate absolute and percentage month-over-month changes in completed orders.
4. Calculate a 3-month moving average beginning with March.
5. Create a line chart for completed orders and the moving average.
6. Create a scatter plot for advertising spend and completed orders.
7. Describe the direction of the relationship visible in the scatter plot. Do not claim advertising caused the order increase.
8. Identify at least two additional variables you would request before recommending action.
9. Write a report with findings, limitations and next steps.

### 13.5 Expected checks

- Number of monthly records: **8**.
- January completed orders: **1,000**.
- August completed orders: **1,500**.
- Endpoint absolute increase: **500 orders**.
- Endpoint percentage increase: **50%**.
- February MoM change: **+100 orders**, or **+10%**.
- March 3-month moving average: (1000 + 1100 + 1050) / 3 = **1050**.
- April 3-month moving average: (1100 + 1050 + 1200) / 3 = **1116.67** (rounded to 2 decimals).

Your chart should show actual monthly orders and the smoothed moving average. There is no moving-average value for January or February because there are not yet three observations.

### 13.6 Suggested findings.md structure

~~~markdown
# Trend Investigation Report

## Business question
Is completed-order volume improving?

## Metric definition
Completed orders per calendar month.

## Data quality checks
- Record count:
- Missing periods:
- Duplicate periods:
- Latest period complete:

## Key findings
1.
2.
3.

## Trend interpretation
Describe direction, volatility and moving-average pattern.

## Correlation interpretation
Describe the observed relationship between ad spend and completed orders.
Do not state causation.

## Limitations
List data gaps, short time window and possible confounders.

## Recommendations
List practical next steps and the KPI to monitor.
~~~

### 13.7 Review checklist

- [ ] Original CSV is unchanged.
- [ ] All eight periods are included.
- [ ] Months are sorted correctly.
- [ ] MoM changes use the previous month as denominator.
- [ ] Moving-average window contains exactly three observations.
- [ ] Line chart labels actual values and moving averages separately.
- [ ] Scatter plot uses advertising spend and completed orders.
- [ ] Findings include absolute and percentage movement.
- [ ] Correlation is not described as proof of causation.
- [ ] Limitations and further data requests are included.
- [ ] Recommendations connect to measurable business outcomes.

### 13.8 Hints if you are stuck

1. Revisit Sections 3 and 5 for comparison and moving-average formulas.
2. For the first 3-month average, use January, February and March.
3. For the next average, drop January and include April.
4. In a scatter plot, use one numeric variable on each axis.
5. If two measures rise together, write “they moved together in this sample” rather than “one caused the other.”
6. Check whether ad spend, website visits and completed orders are measured for the same month.

**Optional extension:** Calculate orders per 1,000 website visits for each month and examine whether traffic growth is accompanied by a change in conversion efficiency. Define the formula before comparing.

## 14. Daily quiz

Try each question before checking the answer.

**Q1. What does a trend describe?**

A. A single unusual observation  
B. The general direction of a measure over time  
C. The number of categories in a dataset  
D. The cause of every change  

**Answer: B.** A trend describes the general direction across a sequence. It does not by itself explain the cause.

**Q2. Revenue rises every December because of holiday demand. Which concept describes this repeating calendar pattern?**

A. Seasonality  
B. Random variation  
C. Data duplication  
D. Correlation coefficient  

**Answer: A.** Seasonality repeats at a regular calendar interval. Compare December with previous Decembers.

**Q3. Orders were 200 last month and 250 this month. What is the percentage change?**

A. 20%  
B. 25%  
C. 50%  
D. −25%  

**Answer: B.** (250 − 200) / 200 × 100 = 25%.

**Q4. What is the 3-period moving average of 10, 20 and 30?**

A. 10  
B. 15  
C. 20  
D. 30  

**Answer: C.** (10 + 20 + 30) / 3 = 20.

**Q5. A BA finds a positive correlation between ad spend and orders. What is the safest conclusion?**

A. Advertising definitely caused every additional order.  
B. Orders and ad spend moved together in the observed data; more analysis is needed to test causation.  
C. The data must be incorrect.  
D. The relationship will continue forever.  

**Answer: B.** Correlation describes association. Confounders, timing, seasonality and other factors may explain the relationship.

## 15. Interview preparation

### Q1. What is trend analysis, and why is it useful to a Business Analyst?

**Answer:** Trend analysis examines historical measurements in time order to identify their general direction and changes. A BA uses it to monitor KPIs, identify emerging problems, assess whether performance is improving and support planning. For example, I can examine monthly complaint volume and resolution time to see whether customer support performance is changing. I would validate the KPI definition and data completeness before drawing conclusions.

**Follow-up:** How would you distinguish a genuine trend from seasonality?

**Answer:** Compare equivalent periods across multiple cycles, such as this December with previous Decembers, and inspect the series for recurring calendar patterns.

### Q2. Explain MoM and YoY comparisons. When would you use each?

**Answer:** MoM compares a month with the immediately previous month and helps identify short-term movement. YoY compares a month with the same month in the previous year and can reduce the effect of recurring seasonality. I would select the comparison based on the business question and state the baseline and time period.

**Follow-up:** What if the previous period had zero revenue?

**Answer:** Percentage change cannot be calculated by dividing by zero. I would report the absolute change and explain that the percentage comparison is undefined.

### Q3. What is a moving average? What is one limitation?

**Answer:** A moving average calculates the average of a fixed number of consecutive observations, then moves the window forward. It smooths short-term fluctuations and helps reveal an underlying direction. A limitation is that it responds slowly to sudden changes and loses values at the beginning where there are not enough observations.

**Follow-up:** How would you choose the window size?

**Answer:** Consider data frequency, the business cycle and the question. A three-month window may be useful for monthly data when short smoothing is appropriate, but I would check whether it hides important changes.

### Q4. What is the difference between correlation and causation?

**Answer:** Correlation means two variables move together in some way. Causation means a change in one variable produces a change in another. Correlation alone does not prove causation because a third variable, seasonality or reverse direction may explain the relationship. I would investigate other factors and use an appropriate experimental or causal method before making a causal claim.

**Follow-up:** Give an example of a confounding variable.

**Answer:** Hot weather may increase both ice-cream sales and swimming-pool visits. Weather is a possible confounding variable.

### Q5. How would you explain a downward KPI trend to a manager?

**Answer:** I would confirm the KPI definition, data quality and comparison period. Then I would quantify the decrease, show the trend over time, identify affected segments and check relevant operational events. I would separate confirmed observations from hypotheses, explain limitations and recommend the next investigation or corrective action with a measurable follow-up KPI.

**Follow-up:** What if the latest month is incomplete?

**Answer:** I would mark it as partial and avoid comparing it directly with complete months unless I use a clearly explained like-for-like method.

## 16. Revision sheet

| Concept | Remember |
|---|---|
| Trend | General direction over time |
| Seasonality | Repeating calendar pattern |
| Cycle | Longer wave without fixed repeat interval |
| Irregular variation | Unexpected disturbance |
| MoM | Current month vs previous month |
| YoY | Current period vs same period last year |
| Percentage change | (current − previous) / previous × 100 |
| Moving average | Average across a rolling window |
| Correlation | Direction and strength of association |
| Causation | One factor produces a change in another |
| Good BA interpretation | Evidence + context + limitations + next action |

## 17. Daily completion checklist

- [ ] I can explain trend, seasonality, cyclical and irregular variation.
- [ ] I can calculate absolute and percentage change.
- [ ] I can choose between MoM, QoQ and YoY comparisons.
- [ ] I can calculate and explain a 3-period moving average.
- [ ] I can read a trend chart and identify unusual movements.
- [ ] I can explain positive and negative correlation.
- [ ] I do not confuse correlation with causation.
- [ ] I completed the Trend Investigation Report.
- [ ] I checked calculations, labels, data quality and limitations.
- [ ] I attempted the quiz and reviewed the explanations.
- [ ] I can answer the interview questions in my own words.

**Day 26 is complete when** you can independently analyze a time-based KPI, show its movement clearly, explain what the evidence supports, identify what remains unknown and recommend a sensible next step.

## 18. References and further learning

The lesson examples and practice dataset above are original synthetic teaching examples. Use these sources to deepen your understanding:

1. [ACCA — Time series and moving averages](https://www.accaglobal.com/my/en/student/exam-support-resources/fundamentals-exams-study-resources/f5/technical-articles/time-series.html) — moving averages and seasonal variation.
2. [NIST/SEMATECH e-Handbook — Introduction to Time Series Analysis](https://www.itl.nist.gov/div898/handbook/pmc/section4/pmc4.htm) — time-series structure and smoothing methods.
3. [Metabase Learn — Overview of time series analysis](https://www.metabase.com/learn/metabase-basics/querying-and-dashboards/time-series/start) — business questions, rolling metrics and trends.
4. [OpenStax — Introductory Statistics](https://openstax.org/details/books/introductory-statistics) — correlation and statistical interpretation.
