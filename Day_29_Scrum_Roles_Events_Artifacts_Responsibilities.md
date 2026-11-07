# TechPhile.ai — Business Analyst Career Pathway

# Day 29: Scrum Roles, Events, Artifacts and Responsibilities

**Phase:** 5 — Agile, Scrum and Project Management  
**Estimated time:** 2–3 hours  
**Difficulty:** Beginner to Intermediate  
**Prerequisites:** Day 27 — Agile principles and Scrum framework; Day 28 — product backlog, sprint planning and estimation.

## Learning objectives

By the end of this lesson, you should be able to:

1. Explain the three Scrum accountabilities.
2. Describe the five Scrum events and their purpose.
3. Explain the three Scrum artifacts and their commitments.
4. Distinguish Product Owner, Scrum Master, Developers and a Business Analyst's contributions.
5. Explain how a Sprint produces an Increment.
6. Participate effectively in Scrum events.
7. Recognize common Scrum anti-patterns.
8. Complete a small Scrum Sprint simulation.

## 1. Why Scrum responsibilities matter

Imagine a team building an online appointment-booking system for a clinic. The clinic manager wants fewer phone calls, patients want to find available appointments, and the delivery team needs to decide what to build first and how to inspect progress.

Scrum provides a framework for this work. It defines accountabilities, events, artifacts and commitments. It does not prescribe every job title, meeting script, document template or engineering practice.

A Business Analyst may clarify stakeholder needs, analyze business rules, refine requirements and make acceptance criteria testable. However, **Business Analyst is not one of the three formal Scrum accountabilities**.

## 2. Scrum in plain English

Scrum is a lightweight framework that helps people and teams generate value through adaptive solutions for complex problems.

A Scrum Team works in short cycles called **Sprints**. During a Sprint, the team creates a usable **Increment** that moves the product toward its goals.

Scrum is based on three pillars of empiricism:

- **Transparency:** important work and progress are visible and understood.
- **Inspection:** people regularly examine the product and progress toward goals.
- **Adaptation:** the team changes its approach when inspection reveals a problem or new information.

### 2.1 Simplified Scrum flow

~~~text
Product Goal
    |
    v
Product Backlog
    |
    v
Sprint Planning
    |
    v
Sprint Backlog + Sprint Goal
    |
    v
Daily Scrum and delivery work
    |
    v
Usable Increment (meets Definition of Done)
    |
    +------> Sprint Review: inspect outcome and adapt future work
    |
    +------> Sprint Retrospective: improve how the team works
    |
    v
Next Sprint
~~~

This is a learning diagram, not a rigid handoff process.

## 3. The Scrum Team

A Scrum Team consists of:
1. One Product Owner.
2. One Scrum Master.
3. Developers.

The team is cross-functional and self-managing. It has no sub-teams or hierarchies within the Scrum Team. It is typically small enough to remain nimble and large enough to complete meaningful work within a Sprint.

The Scrum Guide defines accountabilities, not mandatory job titles. A Developer can be a programmer, tester, designer, analyst or another person who contributes to creating a usable Increment.

### 3.1 Product Owner

The Product Owner is accountable for maximizing the value of the product resulting from the work of the Scrum Team.

Responsibilities:
- Develop and communicate the Product Goal.
- Create and clearly communicate Product Backlog items.
- Order Product Backlog items.
- Ensure the Product Backlog is transparent, visible and understood.

The Product Owner may delegate work but remains accountable for effective Product Backlog management.

**Clinic example:** The Product Owner decides that reliable appointment booking is more valuable for the next release than low-priority profile customization. They communicate the Product Goal and order the backlog accordingly.

The Product Owner is not simply a person who collects requests and forwards them to Developers. They make product-value decisions and ensure the backlog supports the Product Goal.

### 3.2 Scrum Master

The Scrum Master is accountable for establishing Scrum as defined in the Scrum Guide and for the Scrum Team's effectiveness.

They do this by:
- Coaching team members in self-management and cross-functionality.
- Helping the team focus on creating valuable Increments.
- Ensuring Scrum events take place and are productive and timeboxed.
- Helping remove impediments to the team's progress.
- Coaching the organization in adopting Scrum.

**Clinic example:** Developers are delayed because clinic policy decisions arrive late. The Scrum Master helps make the impediment visible and facilitates a conversation with the right decision-makers.

The Scrum Master is not simply a meeting scheduler or manager who assigns tasks to each Developer.

### 3.3 Developers

Developers are the people in the Scrum Team who are committed to creating any aspect of a usable Increment each Sprint.

Responsibilities:
- Create a plan for the Sprint: the Sprint Backlog.
- Instill quality by adhering to the Definition of Done.
- Adapt their plan each day toward the Sprint Goal.
- Hold each other accountable as professionals.

**Clinic example:** Developers clarify the technical approach, implement appointment slot selection, test booking rules and integrate the work into a usable product Increment.

In Scrum, Developers is not limited to software programmers. It refers to all people who do the work of creating the Increment.

## 4. Where does a Business Analyst fit?

A Business Analyst is a common role in organizations, but it is not a separate formal Scrum accountability.

A BA may:
- Interview patients, clinic staff and managers.
- Analyze the current appointment process.
- Identify business rules and exceptions.
- Clarify functional and non-functional requirements.
- Help the Product Owner understand stakeholder needs.
- Refine backlog items with the team.
- Write or improve user stories and acceptance criteria.
- Identify dependencies, assumptions and open questions.
- Support testers with expected business behavior.
- Help prepare stakeholder communication and Sprint Review feedback.

### 4.1 Compare responsibilities

| Area | Product Owner | Scrum Master | Developers | BA contribution |
|---|---|---|---|---|
| Product value | Accountable for maximizing value | Coaches focus on value | Help create valuable Increment | Analyze needs and provide evidence |
| Product Goal | Develops and communicates it | Helps team understand goals | Work toward it | Clarifies business outcomes |
| Product Backlog | Accountable for management and ordering | Coaches effective backlog practices | Provide sizing and implementation insight | Elicit, analyze and refine requirements |
| Sprint plan | Collaborates on goal and selected work | Coaches Scrum practices | Create Sprint plan | Clarify scope and business rules |
| Daily work | Available for product decisions | Coaches self-management | Adapt plan and coordinate work | Answer requirement questions when involved |
| Quality | Ensures value and backlog clarity | Coaches Scrum practices | Adhere to Definition of Done | Help make expected behavior testable |
| Improvement | Participates | Helps team improve effectiveness | Identify improvements | Share process and stakeholder insights |

This table describes common collaboration, not a mandatory division of labor. A BA must not assume they own Product Backlog ordering unless explicitly assigned the Product Owner accountability.

### 4.2 Example: a requirement question

A Developer asks: "Can a patient cancel an appointment five minutes before the scheduled time?"

A useful BA response is not to guess. The BA should:
1. Find the approved cancellation policy.
2. Check whether it covers this situation.
3. Ask the decision owner if the rule is missing or unclear.
4. Record the agreed decision.
5. Update the relevant story, business rule and acceptance criteria.
6. Communicate the clarification to the team.

The Product Owner remains accountable for Product Backlog management. The team decides how to incorporate the clarified work.

## 5. The five Scrum events

Scrum defines five events: the Sprint, Sprint Planning, Daily Scrum, Sprint Review and Sprint Retrospective. The Sprint is the container for all the other events.

### 5.1 Sprint

A Sprint is a fixed-length event of one month or less. A new Sprint starts immediately after the previous Sprint concludes.

During a Sprint:
- No changes are made that would endanger the Sprint Goal.
- Quality does not decrease.
- The Product Backlog is refined as needed.
- Scope may be clarified and renegotiated with the Product Owner as more is learned.

A Sprint is not simply a deadline for finishing a list of tickets. It is a short cycle for achieving a valuable goal and inspecting progress.

**Example:** A one-week Sprint has the goal: "Allow patients to find available appointment slots." The team selects work that supports this goal.

### 5.2 Sprint Planning

Sprint Planning initiates the Sprint by laying out the work to be performed. The whole Scrum Team collaborates.

It addresses three topics:

**Why is this Sprint valuable?**
- The Product Owner proposes how the product could increase value.
- The Scrum Team collaborates to define a Sprint Goal.

**What can be Done this Sprint?**
- Developers discuss and select Product Backlog items.
- Selection considers past performance, capacity and the Definition of Done.

**How will the chosen work get done?**
- Developers plan the work needed to create an Increment.
- The resulting plan is the Sprint Backlog.

For a one-month Sprint, Sprint Planning is timeboxed to a maximum of eight hours. Shorter Sprints usually have shorter planning sessions.

**Output:** Sprint Goal and Sprint Backlog.

### 5.3 Daily Scrum

The Daily Scrum is a 15-minute event for Developers to inspect progress toward the Sprint Goal and adapt the Sprint Backlog as necessary.

- It happens every working day of the Sprint.
- It is for Developers.
- It improves communication, identifies impediments and supports quick decisions.
- Developers can choose any structure that helps them inspect progress and plan the next day.

The familiar three questions — "What did I do yesterday? What will I do today? What is blocking me?" — are one possible format, not a required Scrum rule.

**Example:**
- Progress: slot search is implemented.
- Next: connect search to live availability.
- Impediment: clinic opening hours are not confirmed.

A Daily Scrum is not a status report to a manager. Developers use it to adapt their plan.

### 5.4 Sprint Review

The Sprint Review inspects the outcome of the Sprint and determines future adaptations.

The Scrum Team presents results to key stakeholders. Participants discuss:
- What was accomplished.
- Changes in the environment or business.
- Progress toward the Product Goal.
- What should be done next.

The Product Backlog may be adjusted based on feedback and new opportunities.

For a one-month Sprint, the Sprint Review is timeboxed to a maximum of four hours. Shorter Sprints usually have shorter reviews.

**Example:** Clinic staff try the appointment slot search. They report that patients need to filter by doctor as well as date. The Product Owner considers this feedback when adapting the backlog.

Sprint Review is not just a slide presentation or formal sign-off meeting. It is a working session to inspect the outcome and adapt.

### 5.5 Sprint Retrospective

The Sprint Retrospective is an opportunity for the Scrum Team to inspect how the last Sprint went and plan ways to increase quality and effectiveness.

The team may examine:
- People and interactions.
- Processes and tools.
- Definition of Done.
- Quality problems.
- Collaboration and impediments.

The team identifies the most helpful improvements and may address them in the next Sprint.

For a one-month Sprint, the Retrospective is timeboxed to a maximum of three hours. Shorter Sprints usually have shorter retrospectives.

**Example:** The team discovers that requirements questions are answered late because there is no agreed decision owner. An improvement could be to record a decision owner and response target for each unresolved business rule.

A Retrospective is not a blame session. Focus on learning and improving the system of work.

## 6. Scrum artifacts and their commitments

Scrum has three artifacts. Each artifact contains a commitment that helps provide focus and transparency.

| Artifact | What it represents | Commitment |
|---|---|---|
| Product Backlog | Emergent, ordered list of what is needed to improve the product | Product Goal |
| Sprint Backlog | Sprint Goal, selected Product Backlog items and actionable delivery plan | Sprint Goal |
| Increment | Concrete stepping stone toward Product Goal | Definition of Done |

### 6.1 Product Backlog and Product Goal

The Product Backlog is an emergent, ordered list of what is needed to improve the product. It is the single source of work undertaken by the Scrum Team.

The **Product Goal** describes a future state of the product that can serve as a target for the Scrum Team to plan against.

Example:

"Enable patients to independently find and book suitable clinic appointments online."

A Product Backlog item may be a feature, improvement, defect or research task. Items become more refined as the team learns more.

### 6.2 Sprint Backlog and Sprint Goal

The Sprint Backlog consists of:
- The Sprint Goal (why).
- The Product Backlog items selected for the Sprint (what).
- An actionable plan for delivering the Increment (how).

The **Sprint Goal** is the single objective for the Sprint. It provides flexibility: Developers may adapt the exact work while staying focused on the goal.

Example Sprint Goal:

"Patients can find available appointment slots for a selected clinic service."

Possible selected work:
- Display available slots by date.
- Show a message when no slots are available.
- Prevent selection of a slot that is no longer available.

### 6.3 Increment and Definition of Done

An Increment is a concrete stepping stone toward the Product Goal. Each Increment is additive to prior Increments and thoroughly verified so that they work together.

The **Definition of Done (DoD)** is a formal description of the state of the Increment when it meets the quality measures required for the product.

Example team Definition of Done:
- Code is integrated into the shared product.
- Acceptance criteria are verified.
- Relevant automated tests pass.
- No known critical defect remains in the delivered scope.
- Required documentation is updated.
- The Increment meets applicable security and accessibility standards.

This is an illustrative team agreement. The actual Definition of Done must reflect product and organizational quality requirements.

If a Product Backlog item does not meet the Definition of Done, it is not part of the Increment and cannot be presented as completed. It returns to the Product Backlog for future consideration.

## 7. Timeboxes and participation

The Scrum Guide sets maximum durations for a one-month Sprint. For shorter Sprints, events are usually shorter.

| Event | Purpose | Maximum for a one-month Sprint | Participants |
|---|---|---:|---|
| Sprint | Container for events and work | One month or less | Scrum Team |
| Sprint Planning | Define why, what and how | 8 hours | Entire Scrum Team |
| Daily Scrum | Inspect progress and adapt plan | 15 minutes | Developers |
| Sprint Review | Inspect outcome and adapt future work | 4 hours | Scrum Team and key stakeholders |
| Sprint Retrospective | Plan quality and effectiveness improvements | 3 hours | Scrum Team |

The Scrum Guide does not prescribe a universal duration for every shorter Sprint. Teams adapt event duration while respecting purpose and timebox guidance.

## 8. Worked example: one Sprint from start to finish

**Product:** Clinic appointment booking  
**Product Goal:** Enable patients to find and book appointments online.

**Before Sprint Planning:** The Product Owner orders the Product Backlog. The team has refined items for viewing available slots, displaying a no-availability message, preventing selection of a taken slot and sending booking confirmation.

**Sprint Planning:** The team agrees on this Sprint Goal: "Patients can find available appointment slots for a selected service and date." Developers select items and create an actionable plan.

**During the Sprint:** At Daily Scrum, Developers inspect progress and adapt their plan. The BA clarifies the clinic's slot availability rule. The Scrum Master helps address an impediment when a required policy decision is delayed.

**Increment:** The team integrates and verifies the slot-search capability against its Definition of Done.

**Sprint Review:** Clinic staff inspect the working capability and suggest that the date selector should default to the next available date. The Product Owner considers the feedback and adapts the Product Backlog.

**Sprint Retrospective:** The team agrees to identify decision owners for unresolved business rules before the next Sprint begins.

The cycle repeats with an updated Product Backlog and a new Sprint Goal.

## 9. Common Scrum anti-patterns

| Anti-pattern | Why it is harmful | Better behavior |
|---|---|---|
| Product Owner only forwards requests | Product value and ordering are unclear | Make product decisions and communicate the Product Goal |
| Scrum Master acts as task manager | Team self-management is weakened | Coach the team and help remove impediments |
| Daily Scrum becomes a manager status meeting | Developers do not inspect and adapt | Focus on progress toward the Sprint Goal |
| Sprint Review is only a slide deck | Stakeholders cannot inspect the outcome | Demonstrate the Increment and discuss feedback |
| Retrospective becomes blame | People hide problems | Discuss systems, learning and improvement |
| Sprint Goal is "finish all tickets" | No coherent objective is communicated | State the outcome the Sprint should achieve |
| Work is marked Done before DoD is met | Quality and transparency decline | Apply the agreed Definition of Done |
| BA is assumed to be Product Owner | Accountabilities become confused | Clarify who holds each accountability |
| Every request enters the active Sprint | Focus and Sprint Goal are endangered | Discuss changes with Product Owner and Developers |
| Teams compare velocity | Estimates and contexts differ | Use metrics for local learning and planning |

## 10. Practical mini-project — Scrum Sprint Simulation

**Estimated time:** 60–90 minutes  
**Scenario:** Simulate a one-week Sprint for the clinic appointment-booking product.

You do not need a Jira account. Use a spreadsheet or Markdown files. This exercise focuses on Scrum responsibilities and events, not Jira configuration.

### 10.1 Scenario and goal

**Product Goal:** Enable patients to independently find and book suitable clinic appointments online.

For this simulation:
- Product Owner: accountable for product value and Product Backlog management.
- Scrum Master: helps the team establish Scrum and improve effectiveness.
- Developers: create the usable Increment.
- Business Analyst: supports requirement clarity and stakeholder understanding; not a separate Scrum accountability.

### 10.2 Starter Product Backlog

| ID | Backlog item | Value / reason | Size (illustrative points) |
|---|---|---|---:|
| PB-01 | View available slots | Core discovery journey | 5 |
| PB-02 | Display no-availability message | Clear failure handling | 2 |
| PB-03 | Prevent selection of unavailable slot | Avoid booking conflicts | 5 |
| PB-04 | Send booking confirmation | Reassure patient | 3 |
| PB-05 | Cancel appointment | Allow patient to change plans | 5 |
| PB-06 | View appointment history | Useful follow-up | 3 |
| PB-07 | Filter slots by doctor | Improve search experience | 3 |

These point values are illustrative. Story points are relative estimates, not hours, days or a universal productivity measure.

### 10.3 Task A — Define responsibilities

Create a file named roles_and_responsibilities.md.

For each role, record:
- Accountability.
- Decisions they make or support.
- What they need from other team members.
- One example action in this scenario.

Include the BA as a supporting role and explicitly note that BA is not a formal Scrum accountability.

### 10.4 Task B — Prepare Sprint Planning

Choose a realistic set of backlog items for a one-week Sprint.

Write:
- Sprint Goal (one clear outcome).
- Selected Product Backlog items.
- Why these items support the goal.
- Dependencies and assumptions.
- An initial delivery plan.

Do not simply select the largest number of items. The Sprint Goal should guide selection.

### 10.5 Task C — Simulate Daily Scrum

Create five short Daily Scrum records, one for each working day.

Use a structure that helps Developers inspect progress toward the Sprint Goal. Include:
- Progress toward the goal.
- What the team plans to adapt or do next.
- Any impediment and the action or owner.

Daily Scrum is for Developers. It is not a daily report to a manager.

### 10.6 Task D — Record the Increment

Create a file named increment_and_definition_of_done.md.

Document:
- What usable capability was created?
- Which selected items meet the Definition of Done?
- What verification was completed?
- What is not Done and why?
- What work returns to the Product Backlog?

Do not claim an item is Done if it fails the team's Definition of Done.

### 10.7 Task E — Simulate Sprint Review

Create a file named sprint_review.md.

Include:
- Sprint Goal.
- Outcome achieved.
- Working functionality demonstrated.
- Stakeholder feedback.
- New information or changed conditions.
- Suggested Product Backlog adaptations.

Feedback is not automatically a commitment to add scope. The Product Owner considers its value and orders the backlog.

### 10.8 Task F — Simulate Sprint Retrospective

Create a file named sprint_retrospective.md.

Use these prompts:
- What helped the team?
- What made work difficult?
- What did the team learn?
- What one or two improvements should be tried next Sprint?
- How will the team know whether the improvement helped?

Avoid blaming individuals. Describe observable working conditions and improvement actions.

### 10.9 Required project files

~~~text
Day_29_Scrum_Sprint_Simulation/
├── README.md
├── roles_and_responsibilities.md
├── sprint_plan.md
├── daily_scrum_log.md
├── increment_and_definition_of_done.md
├── sprint_review.md
└── sprint_retrospective.md
~~~

### 10.10 Expected quality checks

- One Product Owner, one Scrum Master and Developers are identified.
- BA activities are shown without inventing a fourth Scrum accountability.
- Product Goal describes a meaningful future product state.
- Sprint Goal expresses one coherent objective.
- Sprint Backlog contains the goal, selected items and delivery plan.
- Daily Scrum records inspect progress toward the Sprint Goal.
- Increment evidence respects the Definition of Done.
- Sprint Review includes stakeholder inspection and feedback.
- Retrospective identifies practical improvement actions.
- Remaining or incomplete work is not falsely marked Done.

## 11. Daily quiz

**Q1. How many formal accountabilities are defined for the Scrum Team?**

A. Two  
B. Three  
C. Four  
D. Five

**Answer: B — Three.** Product Owner, Scrum Master and Developers.

**Q2. Who is accountable for maximizing the value of the product?**

A. Scrum Master  
B. Business Analyst  
C. Product Owner  
D. Tester

**Answer: C — Product Owner.**

**Q3. What is the primary purpose of the Daily Scrum?**

A. Report individual hours to a manager  
B. Inspect progress toward the Sprint Goal and adapt the Sprint Backlog  
C. Approve the project budget  
D. Sign off all requirements

**Answer: B.** Developers use it to inspect progress and adapt their plan.

**Q4. Which artifact has the Product Goal as its commitment?**

A. Product Backlog  
B. Sprint Backlog  
C. Increment  
D. Sprint Review

**Answer: A — Product Backlog.**

**Q5. Which commitment is associated with the Increment?**

A. Sprint Goal  
B. Product Goal  
C. Definition of Done  
D. Definition of Ready

**Answer: C — Definition of Done.**

**Q6. Is Business Analyst a formal Scrum accountability?**

A. Yes  
B. No

**Answer: B — No.** A BA may contribute valuable analysis, but BA is not one of the three formal accountabilities.

**Q7. What is the purpose of the Sprint Retrospective?**

A. Rank individual performance  
B. Inspect how the Sprint went and plan improvements  
C. Approve every new stakeholder request  
D. Estimate next year's budget

**Answer: B.** The Scrum Team identifies ways to improve quality and effectiveness.

## 12. Interview preparation

### Q1. Explain the three Scrum accountabilities.

**Sample fresher answer:** Scrum defines three accountabilities. The Product Owner is accountable for maximizing product value and effective Product Backlog management. The Scrum Master is accountable for establishing Scrum and improving the team's effectiveness. Developers are accountable for creating a usable Increment each Sprint and managing the work needed to achieve the Sprint Goal.

**Follow-up:** Is a Scrum Master the manager of Developers?

**Answer:** No. The Scrum Master serves the Scrum Team and organization by coaching, facilitating and helping remove impediments. Scrum Teams are self-managing.

### Q2. What are the five Scrum events?

**Sample answer:** The Sprint is the container event. Sprint Planning defines why the Sprint is valuable, what can be done and how the work will be completed. The Daily Scrum lets Developers inspect progress toward the Sprint Goal and adapt their plan. Sprint Review inspects the outcome with stakeholders and adapts future work. Sprint Retrospective helps the Scrum Team plan improvements to quality and effectiveness.

**Follow-up:** Is the Daily Scrum a status meeting for the manager?

**Answer:** No. It is an event for Developers to inspect progress and adapt their plan.

### Q3. What are the three Scrum artifacts and their commitments?

**Sample answer:** The Product Backlog has the Product Goal as its commitment. The Sprint Backlog has the Sprint Goal. The Increment has the Definition of Done. These commitments provide focus and transparency for the artifacts.

**Follow-up:** What happens if a Product Backlog item does not meet the Definition of Done?

**Answer:** It is not part of the Increment. It returns to the Product Backlog for future consideration.

### Q4. What does a Business Analyst do in a Scrum Team?

**Sample fresher answer:** A BA helps understand stakeholder needs, analyze processes and business rules, clarify requirements, refine backlog items and make acceptance criteria testable. The BA collaborates with the Product Owner and Developers. BA is not a separate formal Scrum accountability, so the team should clarify responsibilities rather than assume the BA owns Product Backlog ordering.

**Follow-up:** Can a BA facilitate a workshop or help during Sprint Planning?

**Answer:** Yes, if it helps the team. The BA can clarify business context and answer requirement questions, while the Scrum Team retains its defined accountabilities and responsibilities.

### Q5. What is the difference between Sprint Review and Sprint Retrospective?

**Answer:** Sprint Review inspects the product outcome with stakeholders and considers what to do next. Sprint Retrospective inspects how the Scrum Team worked and identifies improvements to quality and effectiveness.

**Follow-up:** Does Sprint Review mean the work is formally accepted by a customer?

**Answer:** Not necessarily. It is an inspection and adaptation event. Acceptance or contractual sign-off may be handled through additional organizational practices.

## 13. Revision sheet

| Term | Remember |
|---|---|
| Scrum Team | Product Owner, Scrum Master and Developers |
| Product Owner | Accountable for maximizing product value |
| Scrum Master | Accountable for establishing Scrum and team effectiveness |
| Developers | Create a usable Increment each Sprint |
| Business Analyst | Common supporting role, not a formal Scrum accountability |
| Sprint | Fixed-length event of one month or less |
| Sprint Planning | Defines why, what and how |
| Daily Scrum | Developers inspect progress and adapt plan |
| Sprint Review | Inspect outcome and adapt future work |
| Sprint Retrospective | Improve quality and effectiveness |
| Product Backlog | Ordered work needed to improve product |
| Product Goal | Future state of the product |
| Sprint Backlog | Sprint Goal, selected items and delivery plan |
| Sprint Goal | Single objective for the Sprint |
| Increment | Usable, verified step toward Product Goal |
| Definition of Done | Formal quality description for the Increment |
| Empiricism | Transparency, inspection and adaptation |

## 14. Daily completion checklist

- [ ] I can explain the three Scrum accountabilities.
- [ ] I can distinguish Product Owner, Scrum Master and Developers.
- [ ] I understand how a BA contributes without becoming a fourth accountability.
- [ ] I can explain the Sprint and the four events inside it.
- [ ] I know the purpose and participant focus of the Daily Scrum.
- [ ] I can distinguish Sprint Review from Sprint Retrospective.
- [ ] I can name the three artifacts and their commitments.
- [ ] I understand Product Goal, Sprint Goal and Definition of Done.
- [ ] I completed the Scrum Sprint Simulation.
- [ ] I reviewed the quiz explanations and practiced the interview answers.

**Day 29 is complete when** you can explain who is accountable for what in Scrum, describe how the events and artifacts connect, and simulate a Sprint without confusing the BA role with formal Scrum accountabilities.

## 15. References and further learning

1. [The Scrum Guide — 2020](https://scrumguides.org/scrum-guide.html) — authoritative source for Scrum accountabilities, events, artifacts and commitments.
2. [Scrum.org — What is Scrum?](https://www.scrum.org/resources/what-scrum-module) — introductory learning material.
3. [Scrum.org — Product Owner](https://www.scrum.org/resources/what-is-a-product-owner) — Product Owner accountability.
4. [Scrum.org — Scrum Master](https://www.scrum.org/resources/what-is-a-scrum-master) — Scrum Master accountability.
5. [Atlassian — Scrum](https://www.atlassian.com/agile/scrum) — practical Scrum overview and examples.

**Study note:** If a company uses additional roles, ceremonies or documents, learn how they fit the organization's process. Do not confuse local practices with the accountabilities, events and artifacts defined by the Scrum Guide.
