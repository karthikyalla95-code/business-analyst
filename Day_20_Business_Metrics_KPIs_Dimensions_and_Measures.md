# TechPhile.ai — Business Analyst Career Pathway

# Day 20: Business Metrics, KPIs, Dimensions and Measures

**Phase:** 4 — Data Analysis for Business Decisions  
**Estimated learning time:** 2–3 hours  
**Difficulty:** Beginner to Intermediate  
**Prerequisites:** Day 19 requirements documentation; basic computer and spreadsheet familiarity.

## Learning objectives
By the end, you can:
1. Distinguish a metric, measure and KPI.
2. Translate a business objective into a measurable KPI.
3. Define numerator, denominator, unit, time window and owner.
4. Separate dimensions from measures.
5. Identify leading, lagging, input and outcome indicators.
6. Document a KPI so two analysts calculate it consistently.

## 1. Why this matters
A manager says, “Customer service is getting worse.” A BA should not simply make a chart. First clarify what “worse” means: longer waiting, more unresolved cases, lower satisfaction, or repeat contacts? Metrics make a business question observable.

Scenario: An online store wants to improve delivery reliability. The team needs agreed measures before it can decide whether a process change worked.

## 2. Essential vocabulary
| Term | Meaning | Example |
|---|---|---|
| Metric | A quantified measurement used to monitor something | Number of orders |
| Measure | A value calculated or observed from data | Total delivery minutes |
| KPI | A key measure tied to an important objective | On-time delivery rate |
| Target | Desired KPI value | At least 95% |
| Baseline | Current/reference performance | 88% last month |
| Dimension | A way to slice or group data | Region, channel, month |
| Fact | A business event or observation being measured | One delivered order |
| Leading indicator | May signal a future outcome | Orders waiting for dispatch |
| Lagging indicator | Records an outcome that already happened | Late-delivery rate |
| Owner | Person accountable for definition/review | Operations manager |
| Grain | What one row represents | One row per order |

A metric is not automatically a KPI. A KPI matters because it tracks progress toward a defined objective.

## 3. Start with the business objective
Use this chain:
Business objective → question → KPI → definition → target → action.

Example:
- Objective: Improve delivery reliability.
- Question: What share of eligible orders arrive by the promised date?
- KPI: On-time delivery rate.
- Definition: Eligible orders delivered on or before promised date ÷ eligible orders due in the period × 100.
- Baseline: 88% (illustrative).
- Target: 95% (must be agreed with stakeholders).
- Action: Investigate regions and carriers with lower rates.

## 4. Build a precise KPI definition
A KPI definition must state:
- Name and purpose.
- Business objective it supports.
- Formula, including numerator and denominator.
- Unit (%, orders, minutes, currency).
- Population and exclusions.
- Time period and refresh frequency.
- Dimensions for analysis.
- Data source and owner.
- Baseline, target and threshold.
- Known limitations and interpretation.

Worked calculation:
In one week, 920 eligible orders were due. 828 arrived on or before the promised date.
On-time delivery rate = 828 / 920 × 100 = 90%.
Do not calculate 828 / all orders created this week if some are not yet due. The denominator must match the KPI definition.

## 5. Dimensions versus measures
A measure is what you calculate; a dimension is how you describe or group it.

| Data item | Type | Why |
|---|---|---|
| Revenue | Measure | Can be summed |
| Order count | Measure | Can be counted |
| Region | Dimension | Groups revenue by geography |
| Sales channel | Dimension | Groups orders by channel |
| Order date | Dimension | Enables daily/monthly analysis |
| Customer segment | Dimension | Compares customer groups |

Example pivot-style view:

| Region | Orders | On-time orders | On-time rate |
|---|---:|---:|---:|
| North | 300 | 282 | 94% |
| South | 250 | 220 | 88% |
| West | 370 | 326 | 88.1% |
| Total | 920 | 828 | 90% |

The total rate is calculated from total counts, not by taking an unweighted average of regional percentages.

## 6. KPI types and balanced measurement
- Input metric: resources used, such as staff hours.
- Process metric: process behaviour, such as time to pack an order.
- Output metric: immediate output, such as orders shipped.
- Outcome metric: business result, such as on-time delivery.
- Leading indicator: may predict future performance.
- Lagging indicator: confirms what happened.

Avoid optimizing one KPI at the expense of the business. If a call centre measures only short call duration, staff may rush customers and increase repeat calls. Pair speed with first-contact resolution and customer satisfaction.

## 7. Follow-along: calculate a KPI
Data:
- Orders due: 100
- Delivered on time: 92
- Delivered late: 8

Steps:
1. Confirm all 100 orders belong in the reporting period.
2. Set numerator = 92.
3. Set denominator = 100.
4. Divide 92 by 100.
5. Multiply by 100.
Expected result: 92%.

Now split by region:
- East: 40 due, 38 on time → 95%.
- Central: 60 due, 54 on time → 90%.
Combined rate = (38 + 54) / (40 + 60) × 100 = 92%. Do not average 95% and 90% equally because group sizes differ.

## 8. Common mistakes
| Mistake | Fix |
|---|---|
| Calling every metric a KPI | Link KPIs to a strategic objective |
| Undefined denominator | Document eligibility and exclusions |
| Mixing time windows | Use consistent dates and due-date logic |
| Averaging percentages incorrectly | Recalculate from underlying counts |
| Too many KPIs | Prioritize a small set tied to decisions |
| Rewarding a single metric | Add balancing quality/outcome measures |
| No owner | Assign accountability for definition and action |

## 9. Interview revision
- A KPI measures progress toward a business objective.
- A dimension is an analysis category; a measure is a value to aggregate or calculate.
- A baseline describes current performance; a target describes desired performance.
- A KPI needs a documented formula and denominator.
- A dashboard should support a decision, not merely display numbers.

### Interview questions
**Q1. What is the difference between a metric and a KPI?**  
A metric is any quantitative measure. A KPI is a metric selected because it directly indicates progress toward an important business objective. For example, page views are a metric; conversion rate may be a KPI for an e-commerce sales objective. Follow-up: Can a KPI change? Yes, when business priorities change, but definitions and historical comparability must be managed.

**Q2. What are dimensions and measures?**  
Measures are values such as sales, order count or delivery time. Dimensions describe how to group those values, such as region, month or product category. A manager can compare sales (measure) by region (dimension). Follow-up: What is grain? The level represented by one record, such as one row per order.

**Q3. Why is a KPI definition important?**  
Without a common formula, different teams may report different values under the same name. A definition makes the calculation, population, time window and owner explicit.

## 10. Mini-project — Business KPI Catalogue
**Time:** 45–60 minutes.

Create:
```text
Day_20_Business_KPI_Catalogue/
├── README.md
├── kpi_catalogue.csv
├── business_objectives.md
└── checker_checklist.md
```

Business scenario: An online retailer wants to monitor sales, fulfilment and customer service.

Starter objectives:
- Improve revenue.
- Improve on-time delivery.
- Reduce customer support backlog.

Tasks:
1. Define at least 8 KPIs across the three objectives.
2. Include columns: KPI_ID, KPI_Name, Objective, Formula, Numerator, Denominator, Unit, Time_Window, Dimensions, Owner, Baseline, Target, Source, Caveat.
3. Include at least 2 balancing KPIs to avoid harmful incentives.
4. Mark unknown targets/baselines as “To be agreed”; do not invent approved targets.
5. Explain what decision each KPI supports.

Sample rows:
| KPI | Formula | Dimensions | Decision |
|---|---|---|---|
| Conversion rate | Orders placed / sessions × 100 | Channel, device, week | Which channel needs funnel improvement? |
| On-time delivery | On-time eligible orders / eligible orders due × 100 | Region, carrier, week | Where should delivery issues be investigated? |
| First-contact resolution | Cases resolved on first contact / eligible cases × 100 | Queue, issue type | Which support queues need training? |

Checker:
- [ ] Each KPI maps to an objective.
- [ ] Numerator and denominator are explicit.
- [ ] Unit and reporting window are stated.
- [ ] Dimensions are not confused with measures.
- [ ] Owner and source are identified or marked pending.
- [ ] Target and baseline are sourced or marked “To be agreed”.
- [ ] At least two balancing measures are present.
- [ ] A decision is stated for each KPI.

Hints: If a rate has no denominator, it is incomplete. If “region” appears in a formula, it is probably a dimension, not part of the arithmetic. Ask whether the KPI can be manipulated by changing behaviour in an undesirable way.

Extension: Add a KPI tree showing how a top-level objective such as revenue growth can be influenced by traffic, conversion rate and average order value.

## 11. Knowledge check
1. Which is a dimension? A) Revenue B) Region C) Order count D) Total cost. **Answer: B** — it groups records.
2. What is a baseline? A) Desired future value B) Current/reference value C) Formula D) Owner. **Answer: B**.
3. Why define the denominator? A) To decorate a chart B) To make the population clear C) To change the target D) To remove data. **Answer: B**.
4. Which is a lagging indicator? A) Open backlog before shift B) Training hours planned C) Last month's late-delivery rate D) Staff schedule. **Answer: C**.
5. A KPI is best selected because it: A) Is easy to count B) Looks impressive C) Tracks an important objective D) Has many dimensions. **Answer: C**.

## 12. Assessment and bridge
Complete Day 20 when you can explain metrics/KPIs/dimensions/measures, calculate a weighted rate correctly, and submit a catalogue with formulas, owners, time windows and decision use.

**Bridge to Day 21:** A KPI catalogue defines what to measure. Next, learn how to prepare operational data in Excel using cleaning, formulas and lookups.


---

## Visual references to add manually

### 1. KPI hierarchy: objectives, KPIs, metrics and measures
- **Filename:** `day_20_concept_01_kpi_hierarchy_pyramid.png`
- **Insert under heading:** `## 3. Start with the business objective`
- **What it should show:** A hierarchy connecting business goals/objectives to critical success factors, KPIs, metrics and raw measures.
- **Search phrase:** `KPI hierarchy goals objectives critical success factors metrics measures pyramid`
- **Reference:** [KPI hierarchy diagram](https://www.slideshare.net/Unilytics/a-step-by-step-approach-to-actionable-kp-is)

*Image note: make sure the visual distinguishes KPIs from all other metrics; do not imply every metric is a KPI. Check reuse terms before copying.*
