# Day 32: Sprint Tracking, Burndown Charts and Delivery Reporting

**Phase:** 5 — Agile, Scrum and Project Management  
**Approved topic:** Sprint tracking, burndown charts and delivery reporting  
**Approved independent mini-project:** Sprint Progress Report  
**Estimated time:** 2–3 hours  
**Difficulty:** Intermediate  
**Prerequisites:** Days 27–31 — Agile principles, Scrum, product backlog, sprint planning, Scrum accountabilities, Kanban and Jira fundamentals. Day 20–22 KPI and Excel concepts are useful.

---

## 1. Why this matters

A team starts a two-week sprint with 40 story points of planned work. Halfway through the sprint, the product owner asks:

- Are we on track to meet the Sprint Goal?
- How much work remains?
- Has the team completed work at a steady rate?
- What is causing the delay?
- What should stakeholders know, and what action is needed?

A Business Analyst may help clarify scope, acceptance criteria, dependencies and status. The Scrum Team owns the work and its delivery. A useful sprint report makes progress visible without hiding uncertainty or blaming individuals.

**Important:** A chart is a signal, not a promise. It helps a team inspect progress and adapt its plan. It does not prove that a sprint will succeed or measure individual productivity.

## 2. Learning objectives

By the end of this lesson, you should be able to:

1. Explain sprint tracking and distinguish it from individual performance monitoring.
2. Read and interpret a sprint burndown chart.
3. Explain burnup charts, velocity and common delivery metrics.
4. Calculate remaining work, completion percentage and scope change.
5. Prepare a concise, evidence-based sprint progress report.
6. Identify risks, blockers and actions without making unsupported claims.

## 3. Words you need

| Term | Plain-English meaning | Example |
|---|---|---|
| Sprint | A fixed-length Scrum event in which the team works toward a Sprint Goal | A two-week sprint |
| Sprint Goal | The single objective that gives the sprint purpose | Enable customers to track an order |
| Sprint Backlog | Sprint Goal, selected Product Backlog Items and the plan for delivering them | Stories, tasks and the team's delivery plan |
| Story point | A team's relative estimate of effort, complexity and uncertainty | A story estimated at 5 points |
| Remaining work | Work not yet completed | 12 points remain |
| Burndown | A chart showing remaining work over time | 40 points at start, 12 today |
| Burnup | A chart showing completed work against total scope | Completed work rises while total scope may change |
| Velocity | Amount of work a team completed in a sprint, usually in story points | 28 points completed |
| Scope change | Work added, removed or changed after the sprint begins | A 3-point story is added |
| Blocker | An issue preventing progress | Test environment unavailable |
| Impediment | Anything slowing or obstructing the team's progress | Waiting for an external approval |
| Forecast | A reasoned estimate of a possible future outcome | Team may finish 34–38 points |
| Spillover | Work not completed by sprint end | A story moves back to the Product Backlog for re-ordering |
| CFD | Cumulative Flow Diagram showing work in workflow states over time | To Do, In Progress, Done |

**Do not confuse these terms:**
- A story point is not a number of hours.
- Velocity is not a target to force individuals to achieve.
- A task marked In Progress is not automatically completed.
- A sprint burndown tracks the team's remaining sprint work; it is not the same as a product release burndown.

## 4. Sprint tracking: the idea step by step

### 4.1 What should be tracked?

Track information that helps the team inspect progress toward the Sprint Goal:

- Sprint Goal and sprint dates.
- Work selected at the start of the sprint.
- Work completed according to the team's Definition of Done.
- Remaining work.
- Work added, removed or re-estimated.
- Blockers, dependencies and risks.
- Quality signals such as open defects or failed tests, where relevant.
- Decisions and actions, with owners and due dates.

A simple tracking table:

| Item | Start of sprint | Current position |
|---|---:|---:|
| Planned scope | 40 points | — |
| Completed | 0 points | 28 points |
| Remaining | 40 points | 12 points |
| Scope added | 0 points | 3 points |
| Scope removed | 0 points | 0 points |

If 3 points were added, be explicit about whether the 12 remaining points include that added work. Never compare numbers that use different scope definitions.

### 4.2 What counts as completed?

Use the team's agreed Definition of Done (DoD). For example, a story may count as Done only when:

- Acceptance criteria pass.
- Code or configuration is integrated.
- Required tests pass.
- Relevant review is complete.
- Documentation is updated when required.
- No required work remains under the team's DoD.

A story that is 90% complete is generally not 90% of a completed story point. For a simple sprint burndown, the story usually remains in the remaining-work total until it meets the Definition of Done.

### 4.3 Who updates the sprint information?

In Scrum, Developers are responsible for adapting their plan and updating the Sprint Backlog as more is learned. The Scrum Master helps the Scrum Team understand Scrum and improve effectiveness. The Product Owner manages Product Backlog ordering and product value.

A Business Analyst may:
- Clarify requirements and acceptance criteria.
- Answer questions about business rules.
- Coordinate with stakeholders on decisions.
- Help document scope changes and dependencies.
- Prepare a factual summary for an agreed stakeholder audience.

A BA does not assign story points on behalf of the team, dictate how Developers do the work or become the owner of the Sprint Backlog by default.

## 5. Burndown charts

### 5.1 What is a burndown chart?

A sprint burndown chart plots the amount of work remaining against time.

- Horizontal axis (X): sprint days or dates.
- Vertical axis (Y): remaining work, often story points or hours.
- Ideal line: a reference showing a steady reduction from starting work to zero.
- Actual line: remaining work recorded by the team.

A simplified example:

| Sprint day | Ideal remaining points | Actual remaining points |
|---:|---:|---:|
| 0 | 40 | 40 |
| 1 | 36 | 40 |
| 2 | 32 | 35 |
| 3 | 28 | 35 |
| 4 | 24 | 28 |
| 5 | 20 | 28 |
| 6 | 16 | 20 |
| 7 | 12 | 12 |
| 8 | 8 | 12 |
| 9 | 4 | 5 |
| 10 | 0 | 0 |

Interpretation:
- On day 1, no work has yet been completed.
- By day 4, the team has reduced remaining work to 28 points.
- On day 5, the actual line is above the ideal line: more work remains than the reference line suggests.
- By day 7, actual remaining work is equal to the ideal reference.
- On day 9, 5 points remain; the team finishes by day 10.

The ideal line is not a commitment that work must be completed at a perfectly steady daily rate. Real work is uneven. Stories may be completed in batches, and estimates or scope may change.

### 5.2 How to calculate a simple ideal burndown

Suppose:
- Starting sprint work = 40 points.
- Sprint duration = 10 working days.

Simple ideal reduction per day:

**40 ÷ 10 = 4 points per day**

Ideal remaining work after day 3:

**40 − (3 × 4) = 28 points**

This is a reference calculation only. Do not interpret it as a requirement that the team complete exactly 4 points every day.

### 5.3 How to interpret common patterns

| Actual line pattern | Possible meaning | What to investigate |
|---|---|---|
| Flat line | No work has moved to Done | Is work blocked, too large, or waiting for review/testing? |
| Sharp drop | Several items were completed together | Was work genuinely completed, or was tracking updated in a batch? |
| Above ideal line | More work remains than the ideal reference | Scope, blockers, estimates and dependencies |
| Below ideal line | Less work remains than the ideal reference | Is the team ahead, or was scope removed? |
| Line rises | Remaining work increased | Was scope added or work re-estimated? |
| Ends above zero | Work remains at sprint end | Review unfinished items and re-plan with the Product Owner |

**A rising burndown is not automatically bad data.** It may correctly show new scope or a revised estimate. The report should explain the reason.

### 5.4 Why a burndown can mislead

- Scope changes are not recorded.
- Work is updated only at the end of the sprint.
- Items are marked Done before meeting the Definition of Done.
- Estimates are changed without recording why.
- The team treats the ideal line as a daily quota.
- A chart is used to rank people rather than inspect the work system.

Always add context beside the chart: scope changes, blockers, quality issues and the Sprint Goal status.

## 6. Burnup charts

A burnup chart shows completed work rising toward a total-scope line.

It normally contains:
1. **Completed-work line:** cumulative amount of work completed.
2. **Total-scope line:** total amount of work currently included in the sprint or release.

Example:

| Day | Completed points | Total scope |
|---:|---:|---:|
| 0 | 0 | 40 |
| 2 | 5 | 40 |
| 4 | 12 | 40 |
| 5 | 12 | 43 |
| 7 | 25 | 43 |
| 9 | 35 | 43 |
| 10 | 43 | 43 |

On day 5, total scope rises from 40 to 43 because 3 points were added. The burnup chart makes that scope change visible while the completed-work line continues to rise.

### Burndown vs burnup

| Comparison | Burndown | Burnup |
|---|---|---|
| Main view | Remaining work | Completed work and total scope |
| Typical direction | Remaining work trends down | Completed work trends up |
| Scope increase | Can make the line rise | Total-scope line rises |
| Useful question | How much work remains? | How much is complete, and how has scope changed? |
| Limitation | Scope change may be less obvious | Does not alone explain blockers or quality |

Use the chart that best answers the audience's question. A chart does not replace a conversation about the Sprint Goal.

## 7. Velocity and forecasting

### 7.1 What is velocity?

Velocity is the amount of work a team completes in a sprint, usually measured in the team's own story points.

Example:

| Sprint | Work completed |
|---|---:|
| Sprint 1 | 24 points |
| Sprint 2 | 28 points |
| Sprint 3 | 26 points |

Average velocity:

**(24 + 28 + 26) ÷ 3 = 26 points per sprint**

If the next backlog contains 52 points, a rough forecast using this historical average is:

**52 ÷ 26 = 2 sprints**

This is a planning aid, not a guarantee. Actual delivery depends on availability, complexity, dependencies, quality and changes in the work.

### 7.2 Responsible use of velocity

Use velocity:
- To help the same team forecast its future work.
- Alongside historical context and known risks.
- As one input to sprint planning.

Do not:
- Compare story-point velocity between different teams.
- Increase estimates to make velocity look higher.
- Set an individual developer's performance target from story points.
- Assume the next sprint will match the average exactly.

A team's estimation scale is local. One team's 5 points may not equal another team's 5 points.

## 8. Other useful delivery measures

| Measure | Meaning / formula | Example |
|---|---|---|
| Completion percentage | Completed points ÷ total points × 100 | 28 ÷ 40 × 100 = 70% |
| Scope change | Current scope − baseline scope | 43 − 40 = +3 points |
| Throughput | Number of work items completed in a period | 8 stories completed |
| Cycle time | Time from work starting to completion | 3 working days |
| Lead time | Time from request to delivery | 8 calendar days |
| Defect count | Number of defects found in a defined period | 4 open defects |
| Blocked work | Work currently unable to progress | 2 stories blocked |

Be precise about the unit and time period. “70% complete” is ambiguous unless you say whether it means points, stories, tasks or another measure.

### Example calculation

At the end of day 7:
- Baseline scope = 40 points.
- Added scope = 3 points.
- Current scope = 43 points.
- Completed work = 28 points.
- Remaining work = 15 points.

Completion percentage against current scope:

**28 ÷ 43 × 100 = 65.1%**

Remaining work check:

**43 − 28 = 15 points**

If someone reports 70% complete, they may have calculated 28 ÷ 40. That uses the original baseline rather than current scope. Both numbers can be useful, but label them clearly:
- 70% of baseline scope completed.
- 65.1% of current scope completed.

## 9. Delivery reporting: turn data into a decision

A useful report answers five questions:

1. **Goal:** What outcome is the sprint trying to achieve?
2. **Status:** What is complete and what remains?
3. **Change:** Has scope, estimate or timing changed?
4. **Risk:** What could prevent the Sprint Goal from being achieved?
5. **Action:** What decision or support is needed, from whom and by when?

### 9.1 One-page sprint report structure

| Section | What to include |
|---|---|
| Sprint details | Name, dates, reporting date and team |
| Sprint Goal | One sentence describing the intended outcome |
| Overall status | On track / At risk / Off track, with evidence |
| Progress | Planned, completed and remaining work |
| Scope movement | Added or removed items and reason |
| Quality | Relevant test results and open defects |
| Risks and blockers | Impact, owner, next action and due date |
| Decisions needed | Clear question, decision-maker and deadline |
| Forecast | Evidence-based view with assumptions |

Use status labels consistently:
- **On track:** current evidence supports the Sprint Goal and no unresolved critical issue is threatening it.
- **At risk:** a material uncertainty or blocker could affect the Sprint Goal; action is underway or required.
- **Off track:** current evidence indicates the Sprint Goal is unlikely to be achieved without a material change or decision.

Do not select green simply because most points are complete. A single unfinished critical item may prevent the Sprint Goal from being achieved.

### 9.2 Write evidence-based status statements

Weak: “The team is slow.”

Better: “Two stories totalling 8 points remain In Progress. Both depend on access to the test environment. The environment owner has been asked to restore access by Tuesday 2 PM.”

Weak: “We will definitely finish.”

Better: “The team has completed 28 of 43 current points. Fifteen points remain, including the order-tracking integration. Completion by Friday is uncertain until the integration dependency is resolved.”

A good status statement contains **fact + impact + action**.

## 10. Follow along: build a sprint report in Excel or Google Sheets

You already learned spreadsheet basics in Days 21–22. Use a blank workbook and create a sheet named **Sprint_Data**.

Enter this sample data:

| Work item | Type | Points | Status | Added after start? | Blocked? |
|---|---|---:|---|---|---|
| US-101 Login | Story | 5 | Done | No | No |
| US-102 Order list | Story | 8 | Done | No | No |
| US-103 Order details | Story | 5 | In Progress | No | No |
| US-104 Tracking API | Story | 8 | In Progress | No | Yes |
| US-105 Email update | Story | 3 | To Do | No | No |
| US-106 Cancel order | Story | 5 | To Do | No | No |
| US-107 Tracking status | Story | 3 | To Do | Yes | No |
| US-108 Error handling | Story | 6 | Done | No | No |

The baseline is 40 points. Current scope is 43 points because US-107 added 3 points.

### Step 1 — Calculate current scope

If Points are in column C and all eight items are in rows 2–9:

~~~excel
=SUM(C2:C9)
~~~

Expected result: **43**

### Step 2 — Calculate completed work

~~~excel
=SUMIF(D2:D9,"Done",C2:C9)
~~~

Expected result: **19**

### Step 3 — Calculate remaining work

~~~excel
=SUM(C2:C9)-SUMIF(D2:D9,"Done",C2:C9)
~~~

Expected result: **24**

### Step 4 — Calculate completion percentage

~~~excel
=SUMIF(D2:D9,"Done",C2:C9)/SUM(C2:C9)
~~~

Format the cell as Percentage. Expected result: **44.2%** (approximately).

### Step 5 — Count blocked stories

~~~excel
=COUNTIF(F2:F9,"Yes")
~~~

Expected result: **1**

### Step 6 — Create a burndown data table

Create another sheet called **Daily_Tracking**:

| Day | Ideal remaining | Actual remaining |
|---:|---:|---:|
| 0 | 40 | 40 |
| 1 | 36 | 40 |
| 2 | 32 | 35 |
| 3 | 28 | 35 |
| 4 | 24 | 28 |
| 5 | 20 | 28 |
| 6 | 16 | 24 |
| 7 | 12 | 20 |
| 8 | 8 | 15 |
| 9 | 4 | 10 |
| 10 | 0 | 0 |

Select the table and insert a **Line Chart**. Label the X-axis “Sprint day” and Y-axis “Remaining story points”. Name the chart “Sprint Burndown”.

This tracking series is a separate illustrative sprint history. Do not combine it with the eight current work items as if they were the same snapshot. In a real report, use one consistent source and clearly record the reporting date.

### Step 7 — Interpret the chart

In the sample, actual remaining work stays flat on days 1 and 3, then drops. Ask:
- Were items waiting for review or testing?
- Was work completed but updated late?
- Did a dependency block progress?
- Was the work broken into pieces that could be completed earlier?

Do not guess the cause from the line alone. Confirm it with the team.

## 11. Common mistakes and fixes

| Mistake | Why it is a problem | Fix |
|---|---|---|
| Counting In Progress work as complete | Overstates delivery | Count only work meeting Definition of Done |
| Hiding added scope | Makes progress look worse or better than reality | Record baseline and current scope separately |
| Treating the ideal line as a deadline quota | Encourages gaming and poor decisions | Use it as a visual reference |
| Comparing velocity across teams | Estimates are team-specific | Use a team's own history |
| Reporting only percentages | Hides important unfinished work | Include item names, points and Sprint Goal impact |
| Saying “on track” without evidence | Stakeholders cannot assess the claim | State facts, risks and assumptions |
| Treating all stories as equal | A critical story may matter more than several small ones | Explain Sprint Goal relevance and dependencies |
| Updating charts irregularly | The picture may not reflect current reality | Agree a lightweight update cadence |
| Moving unfinished work silently | Breaks transparency | Review it and re-order it with the Product Owner |

## 12. Industry scenario

An online retailer is delivering an order-tracking improvement. The Sprint Goal is to let customers view the latest status of an order.

At the mid-sprint review:
- Current scope is 43 points.
- 19 points meet the Definition of Done.
- 24 points remain.
- The tracking API story is blocked by test-environment access.
- A 3-point status story was added after the sprint started.

A useful BA contribution is to confirm whether the added story is essential to the Sprint Goal, document the scope change, clarify the business impact of the API dependency and help obtain a decision from the relevant stakeholders. The BA should not hide the added work or promise a completion date without evidence.

## 13. Independent mini-project: Sprint Progress Report

### 13.1 Problem statement

A product team needs a clear sprint update for its product owner and business stakeholders. Create a report that shows progress, scope movement, risks and actions using the supplied synthetic data.

**Objective:** Produce a one-page Sprint Progress Report and a burndown chart that another person can understand without verbal explanation.

### 13.2 Skills practiced

- Sprint tracking and Scrum terminology.
- Burndown and burnup interpretation.
- Scope-change tracking.
- Spreadsheet formulas and charts.
- Risk and blocker reporting.
- Clear business communication.

### 13.3 Functional requirements

Your report must:
1. State the Sprint Goal and sprint dates.
2. Show baseline scope, current scope, completed work and remaining work.
3. Calculate completion percentage against current scope.
4. Identify added or removed scope.
5. Include a burndown chart using the supplied daily data.
6. Explain at least one trend in the chart without assuming its cause.
7. List blockers with impact, owner and next action.
8. Give an overall status and justify it with evidence.
9. State assumptions and data limitations.

### 13.4 Workspace and files

Create a folder named **Day_32_Sprint_Progress_Report**.

~~~text
Day_32_Sprint_Progress_Report/
├── README.md
├── sprint_items.csv
├── daily_burndown.csv
├── sprint_report.xlsx
└── Sprint_Progress_Report.md
~~~

| File | Purpose | Your action |
|---|---|---|
| README.md | Project instructions and submission checklist | Read and complete |
| sprint_items.csv | Work item input data below | Read-only input |
| daily_burndown.csv | Daily chart input data below | Read-only input |
| sprint_report.xlsx | Calculations, summary and chart | Create and edit |
| Sprint_Progress_Report.md | Written stakeholder update | Create and edit |

### 13.5 Input data

Save the following as **sprint_items.csv**:

~~~csv
work_item,type,story_points,status,added_after_start,blocked
US-101,Story,5,Done,No,No
US-102,Story,8,Done,No,No
US-103,Story,5,In Progress,No,No
US-104,Story,8,In Progress,No,Yes
US-105,Story,3,To Do,No,No
US-106,Story,5,To Do,No,No
US-107,Story,3,To Do,Yes,No
US-108,Story,6,Done,No,No
~~~

Save the following as **daily_burndown.csv**:

~~~csv
day,ideal_remaining,actual_remaining
0,40,40
1,36,40
2,32,35
3,28,35
4,24,28
5,20,28
6,16,24
7,12,20
8,8,15
9,4,10
10,0,0
~~~

### 13.6 Implementation plan

1. Create the folder and save both CSV files exactly as shown.
2. Open Excel or Google Sheets and import the work-item CSV.
3. Calculate baseline scope using only items where added_after_start is No.
4. Calculate current scope using all rows.
5. Calculate completed and remaining points.
6. Calculate current-scope completion percentage.
7. Count blocked items and list their IDs.
8. Import daily burndown data and create a two-series line chart.
9. Write the stakeholder report using the template below.
10. Check every number against the expected results before submitting.

### 13.7 Report template

Save as **Sprint_Progress_Report.md** and fill in the values:

~~~markdown
# Sprint Progress Report

## Sprint details
- Sprint:
- Sprint dates:
- Reporting date:
- Sprint Goal: Enable customers to track an order.

## Executive status
- Status: On track / At risk / Off track
- Evidence:
- Main concern:
- Decision or support required:

## Progress
- Baseline scope:
- Current scope:
- Completed points:
- Remaining points:
- Completion against current scope:
- Added scope:
- Removed scope:

## Burndown interpretation
- What the chart shows:
- Significant flat/rising/falling periods:
- What needs investigation:

## Risks and blockers
| Item | Impact | Owner | Next action | Due date |
|---|---|---|---|---|

## Assumptions and limitations
- 
~~~

### 13.8 Expected results

Use these values to check your calculations:

| Measure | Expected result |
|---|---:|
| Baseline scope | 40 points |
| Current scope | 43 points |
| Completed work | 19 points |
| Remaining work | 24 points |
| Completion against current scope | 44.2% |
| Added scope | 3 points |
| Removed scope | 0 points |
| Blocked items | 1 item — US-104 |

Check: **19 + 24 = 43 points**. If your figures do not add up, inspect your formulas and status filters.

### 13.9 Validation rules

- [ ] Baseline scope excludes items added after sprint start.
- [ ] Current scope includes all current sprint items.
- [ ] Completed work includes only items marked Done.
- [ ] Remaining work equals current scope minus completed work.
- [ ] Completion percentage uses current scope as its denominator.
- [ ] Blocked items are listed by ID.
- [ ] Chart contains both ideal and actual series.
- [ ] Chart axes and units are labelled.
- [ ] Report status is supported by evidence.
- [ ] Scope changes and assumptions are disclosed.

### 13.10 Common project errors

| Symptom | Likely cause | How to fix |
|---|---|---|
| Baseline and current scope both show 43 | Added items were not filtered out | Filter added_after_start = No for baseline |
| Completed total is too high | In Progress items included | Sum only rows with status = Done |
| Remaining points are negative | Completed total or scope formula is wrong | Recheck source rows and formula ranges |
| Percentage exceeds 100% | Wrong denominator or duplicate rows | Use current scope and verify unique work items |
| Chart has one line only | One series was not selected | Add both ideal_remaining and actual_remaining |
| Chart dates appear as categories out of order | Day values imported as text | Convert day to numeric values |

### 13.11 Stuck ladder

1. Re-read Sections 5–9 for chart and reporting concepts.
2. Hint: calculate baseline scope and current scope separately.
3. Compare your formulas with the worked Excel example in Section 10.
4. Review the common project errors table above.
5. Only after attempting the project, compare your calculations with the expected-results table and explain any difference.

### 13.12 Submission evidence

Submit:
- Completed **sprint_report.xlsx** with formulas and chart.
- Completed **Sprint_Progress_Report.md**.
- A screenshot of the summary and chart (hide personal account details).
- A short explanation of one risk and one action.

Optional extension: create a burnup chart from daily completed work and total scope. Explain how the chart makes scope change visible.

## 14. Daily quiz

Choose one answer for each question. Answers and explanations follow the questions.

**Q1. What does a sprint burndown chart primarily show?**

A. Individual developer productivity  
B. Remaining work over time  
C. Customer satisfaction by month  
D. Number of meetings held  

**Q2. A sprint starts with 40 points across 10 working days. What is the simple ideal remaining work after day 4?**

A. 4 points  
B. 16 points  
C. 24 points  
D. 36 points  

**Q3. Current scope is 50 points and completed work is 30 points. What is the completion percentage against current scope?**

A. 30%  
B. 40%  
C. 60%  
D. 80%  

**Q4. Why can a burnup chart be useful when scope changes?**

A. It removes the need to estimate work  
B. It shows completed work and the total-scope line separately  
C. It proves the sprint will finish on time  
D. It measures each developer's speed  

**Q5. A burndown line rises from 12 to 17 remaining points. What is the best first response?**

A. Accuse the team of losing productivity  
B. Delete the previous data point  
C. Investigate whether scope or estimates changed and record the reason  
D. Mark five points as Done  

### Answers and explanations

1. **B — Remaining work over time.** A burndown is a view of work left, not a ranking of people.
2. **C — 24 points.** Ideal reduction is 40 ÷ 10 = 4 points per day. After four days: 40 − 16 = 24.
3. **C — 60%.** 30 ÷ 50 × 100 = 60%.
4. **B — It shows completed work and total scope separately.** This makes scope growth or reduction visible.
5. **C — Investigate scope or estimate changes.** A rise can be valid if work was added or re-estimated. Confirm the cause before reporting it.

## 15. Interview preparation

### Question 1: What is a sprint burndown chart, and how would you use it?

**Answer:** A sprint burndown chart shows the amount of remaining sprint work over time. The horizontal axis represents sprint days and the vertical axis represents remaining work, often story points. I would compare the actual trend with the ideal reference, then discuss unusual flat or rising periods with the team. I would also check scope changes and blockers before communicating a forecast.

**Example:** If a sprint starts with 40 points and 24 remain on day 4, I would report the remaining work and investigate any gap from the ideal line. I would not conclude that the team is underperforming based on the chart alone.

**Follow-up:** What could cause a burndown line to move upward?

**Answer:** Added scope, revised estimates or corrections to previously recorded work can increase remaining work. The team should record the reason so the chart remains understandable.

### Question 2: What is the difference between burndown and burnup charts?

**Answer:** A burndown chart shows remaining work trending down. A burnup chart shows completed work trending up alongside a total-scope line. Burnup can make scope changes easier to see because the total-scope line moves when work is added or removed.

**Example:** If a sprint begins at 40 points and 3 points are added, the burnup total-scope line moves from 40 to 43 while the completed-work line continues to rise.

**Follow-up:** Does either chart prove that a Sprint Goal will be achieved?

**Answer:** No. Charts show progress against recorded work. The team must also inspect whether the completed work achieves the Sprint Goal and meets the Definition of Done.

### Question 3: How would you communicate a sprint that is at risk?

**Answer:** I would state the Sprint Goal, the current evidence, the impact of the risk, the action being taken and any decision needed. I would avoid unsupported predictions or blaming individuals.

**Example:** “The API integration story is blocked by test-environment access. It represents 8 points and is needed for the order-tracking flow. The environment owner has been contacted; access is requested by Tuesday 2 PM. If access is not restored, the Product Owner and team need to inspect the impact on the Sprint Goal.”

**Follow-up:** What if a stakeholder asks you to hide the risk?

**Answer:** I would explain that transparent reporting supports informed decisions. I would correct inaccurate wording if needed, but I would not knowingly omit a material risk.

## 16. Revision sheet

- **Burndown:** remaining work against time.
- **Burnup:** completed work and total scope against time.
- **Velocity:** work completed by a team during a sprint; useful for that team's forecasting.
- **Completion percentage:** completed work ÷ current scope × 100.
- **Scope change:** current scope compared with baseline scope.
- **Definition of Done:** shared quality standard for work to count as Done.
- **Good reporting:** goal + facts + change + risk + action.
- **Key warning:** never use story points or velocity to rank individuals or compare teams.

## 17. Daily assessment and completion checklist

### Concept completion
- [ ] I can explain sprint tracking and the Sprint Goal.
- [ ] I can interpret burndown and burnup charts.
- [ ] I can distinguish velocity from individual productivity.
- [ ] I can explain how scope change affects reporting.
- [ ] I can describe evidence-based status reporting.

### Practical completion
- [ ] I created the project folder and imported both CSV files.
- [ ] I calculated baseline and current scope separately.
- [ ] I calculated completed, remaining and percentage values.
- [ ] I created and labelled the burndown chart.
- [ ] I completed the written Sprint Progress Report.

### Validation and communication
- [ ] All calculations match the expected results or differences are explained.
- [ ] Blockers include impact and next action.
- [ ] Status is supported by facts.
- [ ] Assumptions and limitations are documented.
- [ ] I completed the quiz and reviewed incorrect answers.
- [ ] I can answer at least two interview questions without reading.

**Day 32 is complete when the report, calculations, chart and evidence are present and you can explain what the data does and does not prove.**

## 18. References

- Scrum Guide (2020): https://scrumguides.org/scrum-guide.html
- Atlassian Agile Coach — Burndown charts: https://www.atlassian.com/agile/tutorials/burndown-charts
- Atlassian Agile Coach — Burnup charts: https://www.atlassian.com/agile/project-management/burn-up-chart
- Atlassian Agile Coach — Velocity: https://www.atlassian.com/agile/project-management/velocity
- Atlassian Jira documentation: https://support.atlassian.com/jira-software-cloud/

---

**Roadmap alignment:** Day 32 follows the approved syllabus topic “Sprint tracking, burndown charts and delivery reporting” and uses the exact approved mini-project title “Sprint Progress Report”.
