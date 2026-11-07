# TechPhile.ai — Business Analyst Career Pathway

# Day 28: Product Backlog, Sprint Planning and Estimation

**Phase:** 5 — Agile, Scrum and project management  
**Estimated time:** 2–3 hours  
**Difficulty:** Beginner to Intermediate  
**Prerequisites:** Day 27 — Agile principles, Scrum framework and product mindset.

## Learning objectives

By the end of this lesson, you should be able to:
1. Explain the purpose and structure of a Product Backlog.
2. Distinguish Product Goal, Product Backlog item, Sprint Goal and Sprint Backlog.
3. Write clear, valuable backlog items and testable acceptance criteria.
4. Prioritize items using value, urgency, risk and dependencies.
5. Explain backlog refinement.
6. Participate in Sprint Planning: why, what and how.
7. Understand relative estimation, story points, Planning Poker and capacity.
8. Create an ordered backlog and a realistic Sprint plan.

## 1. What is a Product Backlog?

A **Product Backlog** is an emergent, ordered list of what is needed to improve a product. It is the single source of work undertaken by the Scrum Team.

It can contain:
- New features.
- Improvements.
- Defects and technical work.
- Research or discovery tasks.
- Security, compliance and performance needs.

**Example:** A clinic building an online appointment system may have backlog items for searching doctors, viewing available slots, booking, cancellation and confirmation.

The backlog changes as the team learns from users, stakeholders, technical discovery and product results. It is not simply a list of tasks assigned to individual developers.

## 2. Product Goal, Product Backlog, Sprint Goal and Sprint Backlog

### 2.1 Product Goal

The Product Goal describes a future state of the product. It gives the Scrum Team a longer-term target.

Example: "Enable patients to independently find and book suitable clinic appointments online."

A Product Goal describes an outcome, not a list of implementation tasks.

### 2.2 Product Backlog items (PBIs)

A Product Backlog item is an individual piece of work in the backlog. It may be a feature, improvement, defect, technical task or research item.

Examples:
- Search doctors by specialty.
- View available appointment slots.
- Prevent booking a slot that has already been taken.
- Send a booking confirmation.
- Improve page loading time.

Scrum does not require every PBI to use a user-story format.

### 2.3 Sprint Goal

The Sprint Goal is the single objective for a Sprint. It explains why the Sprint is valuable and gives Developers flexibility in how they achieve it.

Example: "Patients can find available appointment slots for a selected clinic service and date."

### 2.4 Sprint Backlog

The Sprint Backlog contains:
1. Sprint Goal — why.
2. Product Backlog items selected for the Sprint — what.
3. An actionable plan for delivering the Increment — how.

Developers create and adapt the Sprint Backlog during the Sprint.

| Term | Main question | Example |
|---|---|---|
| Product Goal | What future state are we aiming for? | Patients can book clinic appointments online |
| Product Backlog | What work may improve the product? | Search, slots, booking, cancellation |
| Sprint Goal | What objective will this Sprint achieve? | Patients can find available slots |
| Sprint Backlog | What selected work and plan help achieve it? | Slot search, no-results message, availability checks |

## 3. Anatomy of a useful backlog item

A practical template:

~~~text
ID:
Title:
User / stakeholder:
Problem or need:
Expected value:
Description:
Acceptance criteria:
Business rules:
Dependencies:
Assumptions / open questions:
Priority or order:
Estimate:
~~~

Not every item needs every field immediately. Information should grow as the item approaches implementation.

### 3.1 Example user story

**Title:** Search available appointments

As a patient,  
I want to search available appointment slots by service and date,  
so that I can find a suitable time without calling the clinic.

A user story is a short reminder for a conversation. It is not a complete requirement specification by itself.

### 3.2 Acceptance criteria

Acceptance criteria describe conditions that must be satisfied for the requirement to be acceptable.

1. Given a patient selects a clinic service and a future date, when they search, then the system displays matching available slots.
2. Given no slots match the selected criteria, when the search completes, then the system displays a clear no-availability message.
3. Given a slot is no longer available, when the patient attempts to select it, then the system prevents selection and refreshes availability.

Good acceptance criteria are specific, testable and understandable by business and delivery stakeholders.

### 3.3 INVEST quality check

Use INVEST as a practical checklist:
- **Independent:** Can the story be delivered with minimal dependency on other stories?
- **Negotiable:** Is there room for discussion about the solution?
- **Valuable:** Does it provide value to a user or stakeholder?
- **Estimable:** Does the team understand it well enough to estimate?
- **Small:** Can it be completed within a reasonable delivery window?
- **Testable:** Can the team verify whether it works?

INVEST is a useful story-quality heuristic, not a mandatory Scrum artifact.

## 4. Backlog ordering and prioritization

The Product Backlog is ordered, not randomly stored. The Product Owner is accountable for ordering it, using input from stakeholders and the Scrum Team.

Consider:
- User and business value.
- Urgency and deadlines.
- Risk reduction.
- Dependencies.
- Cost of delay.
- Regulatory or operational necessity.
- Learning value and uncertainty.

Do not prioritize solely by the loudest stakeholder or by the smallest development estimate.

### 4.1 MoSCoW

MoSCoW groups requirements into:
- **Must have:** essential for the intended release or outcome.
- **Should have:** important, but a workable alternative or later delivery may exist.
- **Could have:** desirable if capacity permits.
- **Won't have this time:** explicitly excluded from the current scope.

| Requirement | Category | Reason |
|---|---|---|
| View available slots | Must | Core booking journey |
| Prevent double booking | Must | Essential correctness |
| Booking confirmation | Should | Important reassurance |
| Filter by doctor | Could | Helpful improvement |
| Animated page transitions | Won't this time | Not needed for initial outcome |

MoSCoW is a prioritization technique, not a Scrum rule. Define the release or time period to which the categories apply.

### 4.2 Value, effort and risk

Illustrative discussion scores:

| Item | Value (1–5) | Effort (1–5) | Risk reduction (1–5) |
|---|---:|---:|---:|
| View available slots | 5 | 3 | 4 |
| Prevent double booking | 5 | 4 | 5 |
| Profile photo upload | 1 | 2 | 1 |
| Booking confirmation | 4 | 2 | 2 |

A homemade score should support transparent discussion, not automatically determine priority. Consider dependencies and product strategy too.

### 4.3 Dependencies

A dependency exists when an item needs another item, decision or external service.

Example:
- Booking confirmation depends on successful booking.
- Booking depends on reliable slot availability.
- Slot availability may depend on integration with the clinic scheduling system.

Record dependencies early. A high-value item may be difficult to deliver until a dependency is resolved.

## 5. Product Backlog refinement

**Product Backlog refinement** is the ongoing activity of breaking down and further defining backlog items, adding details such as description, order and size.

It is not a formal Scrum event and has no prescribed timebox. It may happen throughout the Sprint.

Typical activities:
1. Review upcoming items.
2. Clarify user and business needs.
3. Identify missing business rules.
4. Split oversized items.
5. Add or improve acceptance criteria.
6. Identify dependencies and risks.
7. Discuss estimates.
8. Reorder items when new information changes their relative value.

### 5.1 Splitting a large item

Large item: "Build complete appointment booking."

Possible smaller items:
- Search appointments by service and date.
- View available appointment slots.
- Select a slot.
- Enter patient details.
- Confirm a booking.
- View booking confirmation.

Split around meaningful user value and manageable delivery, not only technical layers that do not independently provide a useful outcome.

### 5.2 Definition of Ready — use carefully

Some teams use a **Definition of Ready (DoR)** checklist to decide whether an item is sufficiently understood for Sprint selection.

Possible checks:
- User or business need is clear.
- Expected value is understood.
- Acceptance criteria are testable.
- Important business rules are known.
- Major dependencies are visible.
- The item is small enough for the team's delivery approach.
- Open questions have owners.

Definition of Ready is not a formal Scrum artifact or required Scrum rule. Avoid using it as a rigid gate that prevents collaboration or delays learning.

## 6. Sprint Planning: why, what and how

Sprint Planning initiates the Sprint. The whole Scrum Team collaborates.

### 6.1 Why is this Sprint valuable?

The Product Owner proposes how the product could increase value. The Scrum Team collaborates to define a Sprint Goal.

Weak goal: "Complete PB-01, PB-02 and PB-03."

Better goal: "Patients can find available appointments for a selected service and date."

The better goal communicates an outcome rather than simply naming tickets.

### 6.2 What can be Done this Sprint?

Developers discuss and select Product Backlog items. They consider:
- Sprint Goal.
- Team capacity and availability.
- Past performance and experience.
- Definition of Done.
- Dependencies and uncertainty.
- Size and complexity of selected work.

The Product Owner helps clarify value and trade-offs. Developers are responsible for the Sprint plan and collaborate on selection.

### 6.3 How will the chosen work get done?

Developers create an actionable plan. They may break selected items into smaller tasks, identify integration needs and agree on coordination.

The result is the Sprint Backlog: Sprint Goal, selected items and delivery plan.

For a one-month Sprint, Sprint Planning has a maximum timebox of eight hours. Shorter Sprints usually have shorter planning sessions.

## 7. Estimation fundamentals

Estimation is a forecast based on current understanding, not a guarantee.

Teams estimate to:
- Understand relative complexity.
- Identify uncertainty.
- Discuss hidden work.
- Plan a realistic Sprint.
- Compare item size within the team's own context.

### 7.1 Story points

Story points are a relative estimation approach used by some Agile teams. They may represent a combination of effort, complexity, uncertainty and risk.

They are not standardized units. One team's 5 points do not necessarily equal another team's 5 points.

| Story | Relative estimate | Reason |
|---|---:|---|
| Show a no-results message | 1 | Simple behavior |
| Search slots by date | 3 | Several rules and data handling |
| Prevent double booking | 5 | Concurrency and integration risks |
| Build a full booking journey | 13 | Too broad; likely needs splitting |

These values are illustrative, not universal.

### 7.2 Fibonacci-style scale

Some teams use a modified Fibonacci sequence:

~~~text
1, 2, 3, 5, 8, 13, 21
~~~

The gaps grow because uncertainty becomes harder to distinguish precisely for larger items. A 13-point story may be too large or unclear for a Sprint; the team can split it or do discovery first.

### 7.3 Planning Poker

Planning Poker is a collaborative estimation technique.

1. The team agrees on a reference story.
2. The Product Owner or BA explains the next item and answers questions.
3. Each estimator privately chooses a card.
4. Everyone reveals estimates simultaneously.
5. People with high and low estimates explain their reasoning.
6. The team discusses missing assumptions, complexity and risk.
7. The team estimates again if useful.

The purpose is shared understanding, not forcing everyone to agree with the loudest person.

**Example:** A Developer estimates preventing double booking as 3 points because an existing service can be reused. Another estimates 8 because simultaneous requests may not be handled safely. The tester estimates 5 because concurrency scenarios are needed. The difference reveals an assumption that should be investigated.

## 8. Capacity and forecasting

**Capacity** is the amount of time or availability a team has for a Sprint. It is affected by holidays, leave, part-time availability, training, support duties, meetings and unplanned work.

Example:
- Four Developers.
- Five working days each.
- One Developer is on leave for two days.

Available person-days:

~~~text
(4 × 5) − 2 = 18 person-days
~~~

This is a rough availability calculation. It does not mean the team should commit to a fixed number of story points based on person-days.

### 8.1 Velocity

Some teams use **velocity** as a historical measure of estimated work completed in a Sprint.

Example:
- Sprint 1: 18 points.
- Sprint 2: 20 points.
- Sprint 3: 16 points.

Average historical velocity:

~~~text
(18 + 20 + 16) / 3 = 18 points
~~~

This may help the same team forecast, but velocity:
- Is not a productivity score.
- Should not be compared across teams.
- Is not a target to pressure Developers.
- Is not a guarantee of future delivery.
- Is meaningful only within the team's own estimation context.

New teams should use discussion, capacity and uncertainty rather than inventing a velocity.

## 9. BA responsibilities in backlog and Sprint Planning

A Business Analyst can help the team understand the business need and reduce ambiguity.

**Before refinement:**
- Review stakeholder feedback and business objectives.
- Gather relevant policies and process information.
- Identify missing decisions and assumptions.

**During refinement:**
- Explain the problem and user context.
- Help write or improve stories.
- Add business rules and testable acceptance criteria.
- Identify alternate and exception flows.
- Highlight dependencies and stakeholder decisions.
- Help split large requirements into smaller valuable items.

**During Sprint Planning:**
- Clarify business context.
- Answer requirement questions.
- Explain priority rationale and dependencies.
- Help the Product Owner understand trade-offs.

**During the Sprint:**
- Respond to questions and record decisions.
- Keep requirement information transparent.
- Support validation of expected business behavior.

The BA does not automatically own backlog ordering, Sprint commitment or task assignment. Accountabilities must be clear.

## 10. Worked example: clinic backlog and Sprint plan

**Product Goal:** Enable patients to find and book suitable clinic appointments online.

| ID | Product Backlog item | Value | Dependency / risk | Estimate |
|---|---|---|---|---:|
| PB-01 | Search by service and date | High | Scheduling data needed | 3 |
| PB-02 | View available slots | High | PB-01 and availability data | 3 |
| PB-03 | Prevent double booking | Critical | Booking service behavior | 5 |
| PB-04 | Confirm booking | High | Successful booking | 2 |
| PB-05 | Display no-availability message | Medium | Search result handling | 1 |
| PB-06 | Filter by doctor | Medium | Doctor data quality | 3 |
| PB-07 | View appointment history | Medium | Patient identity and booking data | 5 |
| PB-08 | Upload profile photo | Low | File storage | 3 |

A possible initial order:
1. PB-01 — Search by service and date.
2. PB-02 — View available slots.
3. PB-03 — Prevent double booking.
4. PB-05 — Display no-availability message.
5. PB-04 — Confirm booking.
6. PB-06 — Filter by doctor.
7. PB-07 — View appointment history.
8. PB-08 — Upload profile photo.

This is an example order, not a universal answer. The Product Owner considers dependencies, risk and actual product strategy.

**Example Sprint Goal:** "Patients can search and view available appointment slots for a selected service and date."

Selected items:
- PB-01: Search by service and date.
- PB-02: View available slots.
- PB-05: Display no-availability message.

Initial delivery plan:
- Confirm scheduling data and search rules.
- Implement search behavior.
- Display matching slots.
- Handle no-results response.
- Verify normal and exception scenarios.
- Integrate the work and check it against the Definition of Done.

Developers decide the actionable plan and adapt it as they learn. The BA helps clarify rules and expected behavior.

## 11. Practical mini-project — Product Backlog Design

**Estimated time:** 60–90 minutes  
**Scenario:** Design a Product Backlog for a clinic appointment-booking product.

### Task A — Define the Product Goal

Write one sentence describing the future state of the product. Avoid vague goals such as "Build a good application." Describe a meaningful user or business outcome.

### Task B — Identify backlog items

Create at least 12 backlog items across:
- Core search and discovery.
- Booking and cancellation.
- Notifications.
- Patient account and history.
- Security, accessibility or performance.
- Reporting or operational needs.

For each item, include ID and title, user or stakeholder, problem or need, expected value, acceptance criteria, dependencies and assumptions.

### Task C — Prioritize

Use MoSCoW or a value/risk/dependency discussion to order the items. Explain why the first five items are ahead of the rest. Do not simply label everything Must Have.

### Task D — Refine three stories

For three high-priority items:
- Write the user story.
- Add at least three testable acceptance criteria.
- Identify business rules.
- List open questions and their owners.
- Check each story against INVEST.

### Task E — Plan a Sprint

Choose a realistic subset of work. Document:
- Sprint Goal.
- Selected Product Backlog items.
- Capacity assumptions.
- Dependencies and risks.
- Initial delivery plan.
- Why the selected items support the Sprint Goal.

Do not convert estimates into a promise. Explain what could change the forecast.

### Required project files

~~~text
Day_28_Product_Backlog_Design/
├── README.md
├── product_goal.md
├── product_backlog.xlsx (or product_backlog.csv)
├── prioritized_backlog.md
├── refined_user_stories.md
└── sprint_plan.md
~~~

### Expected quality checks

- Product Goal describes a future product outcome.
- At least 12 useful backlog items exist.
- Items are ordered with reasons.
- Three refined stories have testable acceptance criteria.
- Dependencies and open questions are visible.
- Sprint Goal describes one coherent objective.
- Sprint Backlog includes selected work and an actionable plan.
- Estimates are relative forecasts, not guaranteed hours.
- BA contribution is clear without confusing Scrum accountabilities.

## 12. Daily quiz

**Q1. What is the Product Backlog?**

A. Personal tasks for each Developer  
B. An emergent, ordered list of what is needed to improve the product  
C. A list of completed work only  
D. A project budget

**Answer: B.** It is the evolving, ordered source of product work.

**Q2. Who is accountable for effective Product Backlog management?**

A. Product Owner  
B. Scrum Master  
C. Individual Developer  
D. Project sponsor

**Answer: A.** The Product Owner is accountable, though work may be delegated.

**Q3. What does the Sprint Goal communicate?**

A. Every technical task  
B. The single objective that makes the Sprint valuable  
C. Individual performance targets  
D. The final project budget

**Answer: B.**

**Q4. Which three elements make up the Sprint Backlog?**

A. Product Goal, release plan and budget  
B. Sprint Goal, selected Product Backlog items and actionable delivery plan  
C. User stories, contracts and invoices  
D. Defects, meeting notes and timesheets

**Answer: B.**

**Q5. What does INVEST help evaluate?**

A. User-story quality  
B. Employee performance  
C. Project cost  
D. Database normalization

**Answer: A.** It is a heuristic for useful user stories.

**Q6. Are story points standardized units of time?**

A. Yes, one point always equals one hour  
B. No, they are relative estimates used within a team's context  
C. Yes, one point always equals one day  
D. They are mandatory in Scrum

**Answer: B.**

**Q7. Is Definition of Ready a formal Scrum artifact?**

A. Yes  
B. No

**Answer: B.** Some teams use it as a working agreement, but Scrum does not require it.

**Q8. What is the purpose of backlog refinement?**

A. Assign every item to a Developer  
B. Break down and further define backlog items  
C. Close the Product Backlog  
D. Replace Sprint Planning

**Answer: B.**

## 13. Interview preparation

### Q1. What is a Product Backlog?

**Sample fresher answer:** A Product Backlog is an emergent, ordered list of work needed to improve a product. It can contain features, improvements, defects and research items. The Product Owner is accountable for its effective management, including communicating items and ordering them based on value and other considerations.

### Q2. What is the difference between Product Backlog and Sprint Backlog?

**Answer:** The Product Backlog contains evolving product work. The Sprint Backlog contains the Sprint Goal, items selected for the Sprint and the Developers' actionable plan to deliver the Increment.

### Q3. What happens during Sprint Planning?

**Answer:** The Scrum Team collaborates on why the Sprint is valuable, what can be Done during the Sprint and how the work will get done. The team defines a Sprint Goal, and Developers create the Sprint Backlog.

### Q4. What are story points?

**Answer:** Story points are a relative estimation technique used by some Agile teams. They help compare complexity, effort and uncertainty. They are not standardized hours, and estimates should not be used to compare team productivity.

### Q5. How does a BA help with backlog refinement?

**Answer:** A BA helps clarify stakeholder needs, write or improve user stories, add business rules and acceptance criteria, identify dependencies and open questions, and split large requirements into smaller valuable items. The BA supports the Product Owner and Developers but does not automatically own backlog ordering.

### Q6. What is the difference between MoSCoW and story points?

**Answer:** MoSCoW helps discuss requirement priority or scope. Story points are a relative estimate of size, complexity and uncertainty. Priority and effort are different dimensions.

## 14. Revision sheet

| Term | Remember |
|---|---|
| Product Backlog | Emergent, ordered product work |
| Product Goal | Future state of the product |
| PBI | Individual product work item |
| User story | Short description of a user need |
| Acceptance criteria | Testable conditions for expected behavior |
| Sprint Goal | Single objective for the Sprint |
| Sprint Backlog | Goal, selected items and actionable plan |
| Backlog refinement | Ongoing activity to clarify and size items |
| MoSCoW | Must, Should, Could, Won't this time |
| INVEST | Independent, Negotiable, Valuable, Estimable, Small, Testable |
| Story points | Relative estimate, not hours |
| Planning Poker | Collaborative estimation technique |
| Capacity | Team availability for a Sprint |
| Velocity | Team-specific historical forecast aid |
| Definition of Ready | Optional team convention, not a Scrum requirement |

## 15. Daily completion checklist

- [ ] I can explain what a Product Backlog is.
- [ ] I can distinguish Product Goal, Sprint Goal and Sprint Backlog.
- [ ] I can write a user story with testable acceptance criteria.
- [ ] I can use INVEST to review a story.
- [ ] I understand backlog ordering and MoSCoW.
- [ ] I can explain backlog refinement.
- [ ] I understand the three topics in Sprint Planning.
- [ ] I can explain story points and Planning Poker.
- [ ] I understand capacity and the limitations of velocity.
- [ ] I completed the Product Backlog Design mini-project.
- [ ] I reviewed the quiz and interview answers.

**Day 28 is complete when** you can create an ordered Product Backlog, refine user stories, explain estimation and produce a Sprint plan connected to a clear Sprint Goal.

## 16. References and further learning

1. [The Scrum Guide](https://scrumguides.org/scrum-guide.html) — Product Backlog, Sprint Planning, Sprint Backlog and Scrum accountabilities.
2. [Atlassian — Product Backlog](https://www.atlassian.com/agile/scrum/backlogs) — practical backlog guidance.
3. [Atlassian — User Stories](https://www.atlassian.com/agile/project-management/user-stories) — user-story format and examples.
4. [Scrum.org — Product Backlog Refinement](https://www.scrum.org/resources/what-is-product-backlog-refinement) — refinement concepts.
5. [Mountain Goat Software — Planning Poker](https://www.mountaingoatsoftware.com/agile/planning-poker) — collaborative estimation.

**Study note:** Scrum defines the Product Backlog and Sprint Backlog, but does not mandate story points, Planning Poker, MoSCoW, INVEST or Definition of Ready. These are optional techniques teams may find useful.
