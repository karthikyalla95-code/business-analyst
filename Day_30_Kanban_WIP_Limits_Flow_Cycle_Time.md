# TechPhile.ai — Business Analyst Career Pathway

# Day 30: Kanban, WIP Limits, Flow and Cycle Time

**Phase:** 5 — Agile, Scrum and project management  
**Estimated time:** 2–3 hours  
**Difficulty:** Beginner to Intermediate  
**Prerequisites:** Days 27–29 — Agile principles, Product Backlog, Sprint Planning and Scrum responsibilities.

## Learning objectives

By the end of this lesson, you should be able to:

1. Explain Kanban and the purpose of a Kanban system.
2. Visualize work using a Kanban board and meaningful workflow columns.
3. Distinguish work items, workflow states, policies and blockers.
4. Explain Work in Progress (WIP) and set practical WIP limits.
5. Identify bottlenecks and improve the movement of work.
6. Calculate and interpret lead time, cycle time, throughput and work item age.
7. Use cumulative flow diagrams and basic flow metrics.
8. Apply Kanban practices to a Business Analyst team's workflow.
9. Build a Kanban Workflow Board and analyze its flow.

## 1. What is Kanban?

**Kanban** is a way to manage and improve the flow of work. It makes work visible, helps teams limit work in progress, and encourages continuous improvement.

The word Kanban is commonly translated as "visual signal" or "signboard." In modern knowledge work, a Kanban system helps a team see:
- What work exists.
- What stage each item is in.
- Which items are currently being worked on.
- Where work is waiting or blocked.
- Whether the team is completing work at a steady pace.

**Simple example:** Imagine a Business Analyst team handling requirements for a customer portal. Some requests are waiting for clarification, some are being analyzed, some are under review, and some are approved. A Kanban board makes these states visible to the whole team.

Kanban is not just a board with sticky notes. A useful Kanban system also has explicit workflow policies, WIP controls, active management of work and regular improvement.

## 2. Kanban principles and practices

Kanban is commonly introduced through three change-management principles:

1. **Start with what you do now:** Understand the current process instead of immediately replacing it.
2. **Agree to pursue improvement through evolutionary change:** Improve gradually through experiments and feedback.
3. **Encourage leadership at every level:** Anyone who sees an opportunity to improve the workflow can raise it.

The Kanban Method also describes six general practices:

1. **Visualize:** Make work and its movement visible.
2. **Limit WIP:** Avoid starting too much work at once.
3. **Manage flow:** Observe how work moves and where it gets stuck.
4. **Make policies explicit:** Clearly define how work moves between states.
5. **Implement feedback loops:** Review work and workflow regularly.
6. **Improve collaboratively and evolve experimentally:** Make small changes, observe results and learn.

These practices work together. A board without clear policies or active flow management is unlikely to improve delivery by itself.

## 3. Understand a workflow

A **workflow** describes the states that a work item passes through from request to completion.

Example workflow for Business Analysis:

`Requested → Triage → Analysis → Review → Approved → Done`

Each column represents a state or stage. The exact stages depend on the team's actual process.

### 3.1 What is a work item?

A work item is a unit of work that moves through the workflow.

Examples:
- Analyze a request to add a customer address field.
- Clarify refund eligibility rules.
- Document a new user-registration requirement.
- Review acceptance criteria for a payment feature.
- Validate a stakeholder change request.

Each item should have enough information for people to understand what it is and why it matters.

### 3.2 Example Kanban board

| Requested | Analysis | Review | Approved / Done |
|---|---|---|---|
| Add address field | Refund rules | Login story | Email update |
| Export report | Search filters |  |  |
| Mobile number change |  |  |  |

This is only a simple illustration. A real team should use columns that reflect its actual workflow and include WIP limits where appropriate.

### 3.3 Columns versus people

A Kanban board normally visualizes workflow states, not departments or individual employees.

Weak board:
- Karthik
- Developer 1
- Tester
- Manager

Better board:
- Ready
- Analysis
- Review
- Ready for Delivery
- Done

People may be shown as assignees on cards, but the board should help everyone understand the state of work.

## 4. Design a Kanban board

A practical Kanban board has three basic parts:

1. **Columns:** Workflow stages.
2. **Cards:** Individual work items.
3. **Policies and limits:** Rules for moving work and controlling WIP.

### 4.1 Example: Business Analysis workflow

Use this sample workflow:

`Backlog → Ready → In Analysis → Stakeholder Review → Ready for Delivery → Done`

**Backlog:** Requests have been recorded but are not yet selected for active work.

**Ready:** Items have enough information to be started, based on the team's agreed entry policy.

**In Analysis:** The BA is investigating the need, documenting requirements and identifying business rules.

**Stakeholder Review:** The requirement is being checked with relevant stakeholders.

**Ready for Delivery:** Requirements are accepted and sufficiently clear for the delivery team.

**Done:** The agreed completion policy has been met.

A team may use different names or combine stages. Do not create unnecessary columns that do not help manage work.

### 4.2 What should a card contain?

A useful card may include:

| Field | Example |
|---|---|
| ID | BA-014 |
| Title | Clarify refund eligibility |
| Requester | Customer Operations |
| Priority | High |
| Owner | BA team member |
| Created date | 4 November |
| Start date | 5 November |
| Current state | In Analysis |
| Blocked? | No |
| Acceptance / completion condition | Refund rules approved by Operations |
| Notes | Confirm exception for damaged goods |

Avoid putting confidential customer information or unnecessary personal data on broadly visible boards.

### 4.3 Define entry and exit policies

A **policy** explains when an item can enter or leave a workflow stage.

Example:

| Stage | Entry policy | Exit policy |
|---|---|---|
| Ready | Request is understood and has an owner | Someone starts analysis |
| In Analysis | BA has capacity and item is selected | Requirement and key rules are documented |
| Stakeholder Review | Draft is ready for stakeholder feedback | Feedback is resolved or decisions are recorded |
| Ready for Delivery | Required stakeholders have reviewed the requirement | Delivery team accepts it into its workflow |
| Done | Completion conditions are met | No further action in this workflow |

Policies should be visible, understandable and agreed by the people doing the work.

Do not confuse "Done" on a BA workflow with the entire software product being released. Define exactly what completion means for that board.

## 5. Work in Progress (WIP)

**Work in Progress (WIP)** is the number of work items that have started but are not yet finished.

Example:
- 3 items in Analysis.
- 2 items in Stakeholder Review.
- 1 item in Ready for Delivery.

If the team's WIP scope includes these active stages, total WIP is:

`3 + 2 + 1 = 6 items`

Backlog items that have not started are normally not counted as WIP.

### 5.1 Why too much WIP causes problems

Imagine one BA is handling eight requirements simultaneously. Each requirement needs stakeholder clarification, documentation and review.

Possible consequences:
- Frequent context switching.
- More unfinished work.
- Longer waiting time.
- Increased chance of forgetting details.
- Delayed stakeholder feedback.
- More items stuck near completion.

Starting more work does not automatically mean completing more work.

### 5.2 WIP limits

A **WIP limit** is a maximum number of items allowed in a defined workflow stage or group of stages.

Example:

| Column | WIP limit | Current WIP |
|---|---:|---:|
| In Analysis | 3 | 3 |
| Stakeholder Review | 2 | 2 |
| Ready for Delivery | 3 | 1 |

When a stage reaches its WIP limit, the team should generally avoid starting another item in that stage. Instead, team members can:
- Help complete an item already in progress.
- Resolve a blocker.
- Review another person's work.
- Ask a stakeholder for a decision.
- Improve the quality of an existing item.

A WIP limit is a signal to manage flow, not a reason to hide work or move cards artificially.

### 5.3 Choosing an initial WIP limit

There is no universal correct WIP limit. Teams can start with a reasonable limit based on:
- Number of people available.
- Nature and complexity of work.
- Typical review capacity.
- Current bottlenecks.
- Service expectations.

Example: If two people regularly perform analysis, the team might experiment with a WIP limit of 2 or 3 for that stage. It should then observe the impact and adjust collaboratively.

Avoid setting a limit purely by multiplying the number of people by an arbitrary factor.

### 5.4 What if the WIP limit is exceeded?

First, make the situation visible. Then understand why:
- Was an urgent item added?
- Was work moved without following the policy?
- Did a blocker prevent completion?
- Is the limit unrealistic?
- Is there a recurring upstream quality problem?

Agree on how exceptions are handled. Do not silently ignore the limit.

## 6. Manage flow and identify bottlenecks

**Flow** describes how work moves through the system from start to finish.

A bottleneck is a stage that restricts the rate at which work can move through the workflow.

Example:
- Analysis can complete 8 items per week.
- Stakeholder Review can approve only 3 items per week.
- Delivery can accept 6 items per week.

Stakeholder Review is likely to become a bottleneck because work arrives faster than it can be reviewed.

### 6.1 Signs of a bottleneck

Look for:
- A column with many cards.
- Items waiting for a long time.
- WIP limits repeatedly reached.
- Work repeatedly blocked by the same dependency.
- One stage completing work much more slowly than the previous stage.
- Frequent urgent requests interrupting planned work.

A large column may indicate a bottleneck, but investigate before assuming the cause. It may be a temporary spike or a deliberate holding stage.

### 6.2 Practical bottleneck investigation

Ask:
1. Where is work waiting?
2. How long has it been waiting?
3. What prevents the next step?
4. Is the constraint people, policy, information, approval or technology?
5. Can the team help the constrained stage?
6. What small experiment could reduce waiting?

Example improvement:
- Problem: Requirements wait four days for stakeholder approval.
- Cause: Review requests are sent without a clear decision deadline or consolidated questions.
- Experiment: Send a structured review pack with specific questions and a requested response date.
- Measure: Compare review waiting time before and after the experiment.

## 7. Kanban flow metrics

Flow metrics help a team understand delivery behavior. Use multiple measures together; no single metric explains the whole system.

### 7.1 Lead time

**Lead time** measures elapsed time from when a work item is requested or committed to the system until it is completed, according to the team's defined start and end points.

Example:
- Request received: 1 November.
- Work completed: 8 November.

Lead time = 7 calendar days, if elapsed calendar days are used.

Some teams measure from a different commitment point. Always define the start and end points before comparing results.

### 7.2 Cycle time

**Cycle time** measures elapsed time from when work actually starts until it is completed.

Example:
- Work started: 3 November.
- Work completed: 8 November.

Cycle time = 5 calendar days.

### 7.3 Lead time versus cycle time

| Metric | Starts | Ends | What it tells you |
|---|---|---|---|
| Lead time | Request or agreed commitment point | Completion | How long the requester waits |
| Cycle time | Work starts | Completion | How long active work takes to finish |

If a request waits three days before someone starts it, lead time includes those three days while cycle time does not.

The exact definitions vary across organizations and tools. Record your team's definitions and use them consistently.

### 7.4 Throughput

**Throughput** is the number of work items completed in a defined period.

Example:
- Monday to Friday: 12 items completed.
- Weekly throughput = 12 items per week.

Throughput counts completed items, not hours spent or story points earned. If work items vary greatly in size, interpret throughput carefully and consider grouping similar work.

### 7.5 Work item age

**Work item age** is the elapsed time since an item started and is still unfinished.

Example:
- Item started on Monday.
- Today is Thursday.
- It has been in progress for 3 elapsed calendar days if Monday-to-Thursday date difference is used.

An old unfinished item deserves attention, especially when its age exceeds the team's typical cycle time.

### 7.6 Worked metric example

A team completes five requirements with these cycle times:

`2, 3, 4, 4, 7 days`

Average cycle time:

`(2 + 3 + 4 + 4 + 7) / 5 = 4 days`

Median cycle time:
- Ordered values: 2, 3, 4, 4, 7.
- Middle value = 4 days.

The average is influenced by unusually long items. The median gives the middle observation. For operational forecasting, teams often examine a distribution or percentile rather than relying only on the average.

## 8. Cumulative Flow Diagram (CFD)

A **Cumulative Flow Diagram** shows the number of work items in each workflow state over time.

It helps visualize:
- Work entering the system.
- Work being completed.
- WIP in different states.
- Queues growing between stages.
- Potential bottlenecks.

A CFD usually has:
- Horizontal axis: time.
- Vertical axis: cumulative number of work items.
- Colored bands: work items in workflow states.

### 8.1 How to interpret it

- If the band for a stage becomes wider over time, more work may be accumulating in that stage.
- If the gap between started and completed work keeps growing, unfinished WIP may be increasing.
- If the completed-work boundary rises steadily, throughput may be relatively consistent.
- A sudden change may reflect a change in demand, workflow policy or team capacity.

A CFD is a diagnostic view, not proof of a root cause. Ask the team what changed before deciding what action to take.

### 8.2 Small illustrative data set

| Week | Ready | Analysis | Review | Done (cumulative) |
|---|---:|---:|---:|---:|
| 1 | 5 | 3 | 2 | 4 |
| 2 | 6 | 4 | 3 | 6 |
| 3 | 7 | 5 | 5 | 7 |
| 4 | 8 | 5 | 6 | 8 |

In this example, the number of items in Review is growing. The team should investigate whether reviews are waiting for stakeholder availability, unclear questions or insufficient review capacity.

The table is a simplified snapshot for learning. A real CFD normally plots cumulative counts at each workflow state, with consistent definitions and data.

## 9. Kanban and Scrum — how they differ

Kanban and Scrum are not simply competing tools. Teams may use Kanban practices alongside Scrum.

| Area | Scrum | Kanban |
|---|---|---|
| Delivery approach | Work organized into fixed-length Sprints | Continuous flow |
| Work selection | Sprint Planning creates a Sprint Backlog | Work pulled when capacity is available under policies |
| Core focus | Sprint Goal and usable Increment | Managing and improving flow |
| Work limits | Scrum does not prescribe a WIP limit | Explicit WIP limits are a key Kanban practice |
| Roles | Scrum defines Product Owner, Scrum Master and Developers accountabilities | Kanban does not prescribe Scrum accountabilities |
| Change during work | Sprint Goal should remain stable; scope can be clarified and renegotiated | Work can be pulled continuously as capacity becomes available |
| Improvement | Sprint Retrospective and other feedback | Continuous feedback and evolutionary improvement |

Scrum does not prohibit Kanban practices. A Scrum Team can visualize its workflow, limit WIP and use flow metrics while still following Scrum.

## 10. BA responsibilities in a Kanban workflow

A Business Analyst can support flow by:
- Recording incoming requests clearly.
- Helping define entry criteria for analysis.
- Identifying missing information early.
- Making dependencies and blockers visible.
- Keeping acceptance criteria and business rules accessible.
- Helping stakeholders provide timely decisions.
- Reviewing aging items and stalled work.
- Using flow data to identify recurring process delays.
- Suggesting small workflow improvements.

The BA should not move cards merely to make a dashboard look healthy. A card's state must reflect the actual state of the work.

## 11. Worked example: analyze a BA team's workflow

A team receives 10 requirements in one week.

At the end of the week:
- 4 are waiting in Ready.
- 3 are in Analysis.
- 2 are in Stakeholder Review.
- 1 is Done.

Observations:
1. Only one item reached Done.
2. Several items remain unfinished.
3. The team should check whether analysis or stakeholder review is the constraint.
4. It should inspect item age and blockers before deciding what to change.

Possible actions:
- Stop pulling new analysis work when the analysis WIP limit is reached.
- Ask another team member to help with review.
- Clarify stakeholder questions before sending an item for review.
- Make review waiting time visible.
- Check throughput and cycle time over several weeks.

Do not conclude that the team is underperforming from one week's snapshot. Work size, complexity, urgent incidents and the observation window matter.

## 12. Practical mini-project — Kanban Workflow Board

**Estimated time:** 60–90 minutes  
**Scenario:** You are supporting a Business Analyst team that receives requirement requests from Customer Support, Sales and Operations.

### Task A — Design the workflow

Create a board with these suggested columns:

`Backlog → Ready → In Analysis → Stakeholder Review → Ready for Delivery → Done`

For each column, define:
- What the state means.
- Entry policy.
- Exit policy.
- Whether it counts as WIP.
- Initial WIP limit, if applicable.

You may change the workflow if you explain why.

### Task B — Create work item cards

Create at least 12 realistic requirement requests. Example cards:
- Add a customer address field.
- Allow support agents to export a case report.
- Clarify refund eligibility.
- Add a password-reset confirmation.
- Display order status.
- Improve customer search filters.
- Capture a preferred contact method.
- Add a reason code for cancellations.
- Define an approval rule for high-value refunds.
- Add a report for unresolved cases.
- Validate mobile number format.
- Document an account-deactivation process.

Each card should include ID, title, requester, priority, owner, created date, state, acceptance/completion condition and blocker status.

Use fictional names and data. Do not include real customer personal information.

### Task C — Set WIP limits

Choose initial limits for:
- In Analysis.
- Stakeholder Review.
- Ready for Delivery.

Explain why each limit is reasonable for your sample team. Include a policy for handling urgent work and WIP-limit exceptions.

### Task D — Simulate work movement

Move cards through the board over five working days. Record:
- Date moved.
- Previous state.
- New state.
- Blocker or reason for waiting.
- Whether a WIP limit was reached.

Do not move work simply to fill every column. Keep the simulation consistent with the policies.

### Task E — Calculate flow metrics

For at least five completed items, record:
- Request date.
- Start date.
- Completion date.
- Lead time.
- Cycle time.

Also calculate:
- Throughput for the five-day period.
- Average cycle time.
- Median cycle time.
- Age of any unfinished work items.

State whether you use calendar days or working days and apply that convention consistently.

### Task F — Identify one improvement

Write a short improvement report:
1. What is the observed bottleneck?
2. What evidence supports your observation?
3. What is the likely cause?
4. What small experiment will you try?
5. Which metric will tell you whether the experiment helped?

### Suggested project structure

~~~text
Day_30_Kanban_Workflow_Board/
├── README.md
├── workflow_design.md
├── kanban_board.xlsx (or kanban_board.csv)
├── workflow_policies.md
├── work_item_history.csv
├── flow_metrics.xlsx (or flow_metrics.md)
└── improvement_report.md
~~~

### Expected quality checks

- Board columns represent real workflow states.
- Cards represent individual work items.
- Entry and exit policies are explicit.
- WIP limits are defined for active stages.
- WIP counts exclude work that has not started, according to the chosen policy.
- Work movement history is consistent.
- Lead time and cycle time use clearly defined start and end points.
- Throughput counts completed items in a stated period.
- Work item age is calculated for unfinished work.
- The improvement recommendation is supported by evidence.

## 13. Daily quiz

**Q1. What is the main purpose of a Kanban board?**

A. Measure employee attendance  
B. Visualize work and its movement through a workflow  
C. Replace all stakeholder communication  
D. Assign salaries

**Answer: B.** A board makes work state and flow visible.

**Q2. What does WIP mean?**

A. Work in Progress  
B. Work Is Planned  
C. Weekly Internal Process  
D. Work Item Priority

**Answer: A.**

**Q3. What should a team generally do when a stage reaches its WIP limit?**

A. Start unlimited additional work  
B. Hide a card  
C. Help finish, unblock or review existing work before pulling more into that stage  
D. Delete the oldest item

**Answer: C.** The limit encourages the team to manage existing work and improve flow.

**Q4. Which metric counts completed work items in a period?**

A. Cycle time  
B. Throughput  
C. Work item age  
D. Lead time

**Answer: B.**

**Q5. When does cycle time normally start?**

A. When the work item starts  
B. When the customer first thinks of the request  
C. When the product is retired  
D. When the project budget is approved

**Answer: A.** Define the team's exact start point consistently.

**Q6. What does work item age measure?**

A. How long a completed item took  
B. How long an unfinished item has been in progress  
C. The age of the employee  
D. The age of the software

**Answer: B.**

**Q7. A team completes 15 work items in three weeks. What is its average weekly throughput?**

A. 3  
B. 5  
C. 12  
D. 45

**Answer: B.** 15 divided by 3 = 5 completed items per week.

**Q8. What can a growing band in a Cumulative Flow Diagram indicate?**

A. Work may be accumulating in that workflow stage  
B. Every item is complete  
C. The team has no WIP  
D. The product has no users

**Answer: A.** Investigate the cause rather than assuming it from the chart alone.

**Q9. Does Scrum forbid a team from using Kanban practices?**

A. Yes  
B. No

**Answer: B.** Scrum Teams can use Kanban practices to improve flow while retaining Scrum.

**Q10. Is Kanban only a board with columns?**

A. Yes  
B. No

**Answer: B.** A Kanban system also includes WIP control, explicit policies, flow management, feedback and continuous improvement.

## 14. Interview preparation

### Q1. What is Kanban?

**Sample fresher answer:** Kanban is a method for managing and improving the flow of work. It helps teams visualize work, limit work in progress, make workflow policies explicit and continuously improve delivery.

### Q2. What is a WIP limit and why is it useful?

**Answer:** A WIP limit is the maximum number of items allowed in a defined stage or workflow scope. It helps reduce excessive multitasking, exposes bottlenecks and encourages the team to finish existing work before starting more.

### Q3. What is the difference between lead time and cycle time?

**Answer:** Lead time measures elapsed time from the request or agreed commitment point until completion. Cycle time measures elapsed time from when work starts until completion. A team must define the exact start and end points consistently.

### Q4. What is throughput?

**Answer:** Throughput is the number of work items completed in a defined period, such as 10 requirements per week. It is a count of completed items, not the number of hours worked.

### Q5. How do you identify a bottleneck?

**Answer:** I would examine the board for accumulating work, items waiting for a long time, repeated WIP-limit breaches and recurring blockers. I would then investigate the cause with the team instead of assuming that a large column automatically identifies the root cause.

### Q6. What is a Cumulative Flow Diagram?

**Answer:** A Cumulative Flow Diagram shows how many work items are in each workflow state over time. It can help reveal growing queues, changes in WIP and potential bottlenecks.

### Q7. Can Scrum and Kanban be used together?

**Answer:** Yes. A Scrum Team can use Kanban practices such as visualizing workflow, limiting WIP and tracking flow metrics while continuing to follow Scrum.

### Q8. How can a BA help improve Kanban flow?

**Answer:** A BA can make incoming requests clearer, identify missing information early, document workflow policies, highlight blockers and dependencies, obtain stakeholder decisions and use flow metrics to recommend process improvements.

## 15. Revision sheet

| Term | Remember |
|---|---|
| Kanban | Method for managing and improving flow |
| Workflow | States work passes through |
| Work item | Individual unit of work |
| Kanban board | Visual representation of work and workflow |
| WIP | Started but unfinished work |
| WIP limit | Maximum allowed WIP in a defined scope |
| Flow | Movement of work through the system |
| Bottleneck | Constraint that slows overall flow |
| Lead time | Request / commitment to completion |
| Cycle time | Work start to completion |
| Throughput | Items completed per period |
| Work item age | Time an unfinished item has been in progress |
| CFD | Cumulative Flow Diagram |
| Explicit policy | Agreed rule for moving work |
| Continuous improvement | Small experiments and learning |

### Important formulas

Average cycle time:

`Sum of cycle times ÷ Number of completed items`

Throughput:

`Completed work items ÷ Time period`

Lead time (using elapsed days):

`Completion date − Request date`

Cycle time (using elapsed days):

`Completion date − Start date`

Work item age:

`Today’s date − Start date` for an unfinished item.

Always define whether you are using calendar days or working days.

## 16. Daily completion checklist

- [ ] I can explain Kanban and its six general practices.
- [ ] I can design workflow columns that reflect real work states.
- [ ] I can explain a work item card and explicit policies.
- [ ] I understand WIP and why WIP limits matter.
- [ ] I can identify possible bottlenecks.
- [ ] I can distinguish lead time and cycle time.
- [ ] I can calculate throughput and work item age.
- [ ] I can explain a Cumulative Flow Diagram.
- [ ] I understand how Kanban practices can complement Scrum.
- [ ] I completed the Kanban Workflow Board mini-project.
- [ ] I reviewed the quiz and interview answers.

**Day 30 is complete when** you can create a Kanban workflow, define WIP limits and policies, calculate basic flow metrics, identify a likely bottleneck and recommend an evidence-based improvement.

## 17. References and further learning

1. [The Kanban Guide](https://kanbanguides.org/) — foundational guidance for the Kanban Method.
2. [Kanban University — The Official Guide to the Kanban Method](https://kanban.university/kanban-guide/) — principles and practices.
3. [Atlassian — What is Kanban?](https://www.atlassian.com/agile/kanban) — practical introduction and board examples.
4. [Atlassian — WIP Limits](https://www.atlassian.com/agile/kanban/wip-limits) — why and how teams limit work in progress.
5. [Actionable Agile Metrics](https://actionableagile.com/) — flow metrics and forecasting concepts.

**Study note:** Kanban is not defined by a fixed set of mandatory columns or a universal WIP limit. Design the workflow around the team's real service and improve it using observed evidence.
