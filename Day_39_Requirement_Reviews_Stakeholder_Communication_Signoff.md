# Day 39: Requirement Reviews, Stakeholder Communication and Sign-Off

## Learning outcomes

By the end of this lesson, you should be able to:

- Explain why requirements need formal and informal reviews.
- Prepare requirements for stakeholder review.
- Plan and facilitate a requirement walkthrough.
- Identify ambiguity, gaps, conflicts, assumptions and dependencies.
- Communicate with different stakeholder groups effectively.
- Record decisions, actions, risks and open questions.
- Manage feedback and requirement changes without losing traceability.
- Understand approval, baseline and sign-off.
- Prepare a Requirement Review Meeting Pack.

## 1. Why requirement reviews matter

A requirement may look clear to the person who wrote it but mean something different to a developer, tester, customer or operations team.

A requirement review is a structured activity in which relevant stakeholders examine requirements to check whether they are accurate, complete, clear, consistent, feasible, testable and aligned with business needs.

Reviews help find problems before they become expensive design, development or testing changes.

### Example

Draft requirement:

"The system should send alerts quickly when an order changes."

Questions a reviewer may ask:
- Which order changes trigger an alert?
- Who receives it: customer, support team or both?
- Which channel is used: email, SMS, push notification or in-app?
- What does "quickly" mean?
- What information should the alert contain?
- What happens if notification delivery fails?
- Can a user opt out?
- Are there privacy or consent rules?

The review turns a vague statement into requirements that can be designed, built and tested.

## 2. Types of requirement reviews

| Review type | Purpose | Example participants |
|---|---|---|
| Peer review | Another analyst checks clarity and completeness | Business Analysts |
| Stakeholder review | Confirm business need and expected outcome | Business owner, users, BA |
| Requirement walkthrough | Analyst explains requirements step by step | BA, product owner, developers, testers |
| Technical review | Assess feasibility, integration and constraints | Architects, developers, security |
| Testability review | Check whether requirements can be validated | QA, UAT representatives, BA |
| Compliance review | Check regulatory, policy and audit needs | Compliance, legal, risk |
| Formal approval review | Obtain authorized decision and baseline | Sponsor, product owner, delegated approver |

A review does not always require a large meeting. A short document review, workshop, comment round or one-to-one clarification may be more effective.

## 3. What should be reviewed?

A requirement review should examine more than grammar.

### 3.1 Business alignment
- Does the requirement support an agreed business objective?
- Is the business problem understood?
- Is the expected outcome valuable?
- Is the scope clear?

### 3.2 Clarity and precision
- Does the statement have one clear interpretation?
- Are words such as fast, easy, flexible and user-friendly defined?
- Are roles, events, data and outcomes identified?
- Are terms used consistently?

### 3.3 Completeness
- Are normal and exception flows included?
- Are required fields and business rules defined?
- Are permissions, notifications and error conditions covered?
- Are dependencies and assumptions recorded?

### 3.4 Consistency
- Does the requirement conflict with another requirement?
- Are business terms and status names consistent?
- Do process diagrams and written requirements agree?
- Are data definitions consistent across systems?

### 3.5 Feasibility and constraints
- Can the proposed solution be delivered with available systems?
- Are performance, security and privacy needs considered?
- Are external dependencies identified?
- Are time, budget or policy constraints documented?

### 3.6 Testability and traceability
- Can a tester verify the expected result?
- Are acceptance criteria measurable?
- Is the requirement uniquely identified?
- Is it linked to its source, process, design and test cases?

## 4. Requirement quality checklist

Use this checklist to review each requirement.

| Quality attribute | Review question |
|---|---|
| Necessary | Does it address a real business need? |
| Clear | Can different readers interpret it consistently? |
| Complete | Is enough information present to understand it? |
| Consistent | Does it conflict with other approved requirements? |
| Feasible | Can it be delivered within known constraints? |
| Testable | Can evidence show whether it is satisfied? |
| Traceable | Is its source and related work identifiable? |
| Prioritized | Is its business importance understood? |
| Atomic | Does it express one main requirement? |
| Verifiable | Is there a practical way to validate it? |

### Weak and improved requirements

| Weak statement | Problem | Improved example |
|---|---|---|
| The page should load fast | No measurable target | Under the agreed load conditions, the page should load within the approved response-time target |
| Users should access reports | User roles and permissions unclear | Users with the Finance Analyst role can view monthly finance reports for their assigned business unit |
| The system should be secure | Too broad | Only authenticated users with the approved role can view customer application details |
| Send alerts when needed | Trigger and recipient unclear | When an order status changes to Dispatched, send an email to the registered customer address |
| Search should be easy | Not testable | Search results should be filterable by order ID, date range and status |

The improved examples still need stakeholder confirmation of exact targets, roles, rules and exception handling. Do not invent a measurable target and treat it as approved.

## 5. Preparing for a requirement walkthrough

A walkthrough is a collaborative review in which the BA explains requirements and gathers feedback.

### Before the meeting

1. Confirm the purpose and expected decision.
2. Identify the requirements in scope.
3. Identify decision-makers and subject-matter experts.
4. Share the document early enough for preparation.
5. Include process flows, wireframes, data definitions or examples where useful.
6. Highlight open questions and assumptions.
7. Prepare a clear agenda and time allocation.
8. Check that the latest version is being reviewed.
9. Explain how feedback and decisions will be recorded.

### During the meeting

1. Restate the business objective.
2. Confirm scope and exclusions.
3. Walk through the current process and proposed future process.
4. Review requirements in logical groups.
5. Ask stakeholders to explain exceptions and real-world cases.
6. Check roles, data, permissions and integrations.
7. Confirm acceptance criteria and priority.
8. Record decisions, disagreements and action owners.
9. Summarize unresolved questions.
10. Confirm the next step and approval route.

### After the meeting

1. Update the requirements and related artifacts.
2. Maintain a change history or version record.
3. Share meeting minutes and decisions.
4. Assign open actions with owners and due dates.
5. Resolve conflicts with the appropriate decision-maker.
6. Circulate the revised version for review.
7. Obtain approval through the agreed process.
8. Update traceability and communicate the approved baseline.

## 6. Planning a useful review meeting

A sample 60-minute agenda:

| Time | Activity |
|---|---|
| 0–5 min | Introductions, purpose and desired outcome |
| 5–10 min | Business objective, scope and assumptions |
| 10–25 min | Process and functional requirements |
| 25–35 min | Data, integrations and business rules |
| 35–45 min | Exceptions, security and non-functional needs |
| 45–53 min | Acceptance criteria, priorities and open issues |
| 53–60 min | Decisions, actions, owners and next steps |

Adapt the agenda to the size and complexity of the requirements. Do not rush critical security, compliance or operational topics merely to fit a meeting template.

### Who should attend?

Invite people who can provide necessary information or make a decision:
- Business sponsor or product owner.
- Business process owner.
- Representative end users.
- Business Analyst.
- Solution architect or technical lead.
- Developers or integration specialists where relevant.
- QA or UAT representative.
- Security, privacy, compliance or operations representatives when applicable.

Avoid inviting people without a clear role in the review. Share the outcome with wider audiences when needed.

## 7. Stakeholder communication

Stakeholders have different interests and different levels of technical knowledge. A BA adapts the message without changing the facts.

| Stakeholder | Usually needs to understand | Useful communication |
|---|---|---|
| Sponsor | Business value, scope, cost, risk and decisions | Executive summary and decision paper |
| Product owner | Priority, outcomes and backlog | Refinement session and backlog |
| End user | Workflow, usability and exceptions | Interview, prototype and walkthrough |
| Developer | Rules, data, interfaces and edge cases | Requirement details and technical discussion |
| Tester | Acceptance criteria, scenarios and expected results | Testability review and traceability |
| Operations | Support, monitoring, ownership and handover | Operational readiness review |
| Compliance | Controls, evidence, retention and policy | Control mapping and formal review |

### 7.1 Choose the right communication method

- **Interview:** Explore an individual's knowledge or experience.
- **Workshop:** Resolve a topic collaboratively with multiple people.
- **Walkthrough:** Explain and review a requirement or process.
- **Email:** Share a concise update, request a response or document a decision.
- **Meeting minutes:** Record what was discussed, decided and assigned.
- **Dashboard:** Show progress, open issues, risks and decisions.
- **Prototype:** Help users react to a proposed interaction or workflow.
- **Decision log:** Preserve important decisions and their rationale.

Use synchronous discussion for complex or disputed topics. Use written records for decisions and traceability.

## 8. Asking effective clarification questions

A BA should ask neutral, specific questions rather than leading stakeholders toward a preferred solution.

### Examples

**Vague requirement:** "Managers can approve applications."

Ask:
- Which manager role is authorized?
- Can a manager approve their own application?
- What conditions must be met before approval?
- Can an application be rejected?
- Is a rejection reason mandatory?
- Can an approved application be changed?

**Vague requirement:** "Keep customer data for the required period."

Ask:
- Which data categories are covered?
- What retention period applies to each category?
- Which policy or regulation defines the period?
- Who can authorize deletion?
- What happens when a legal hold applies?
- Is deletion required in connected systems and backups?

Do not provide legal interpretations as fact. Refer policy and regulatory questions to authorized specialists.

### 8.1 Open-ended and closed questions

| Question type | Example | Use |
|---|---|---|
| Open-ended | How do you handle an incomplete application today? | Discover processes and pain points |
| Closed | Is email the approved notification channel? | Confirm a specific point |
| Probing | What happens if the customer does not respond? | Explore exceptions |
| Clarifying | By "manager", do you mean the branch manager role? | Remove ambiguity |
| Hypothetical | What should happen if the payment service is unavailable? | Explore scenarios |
| Prioritization | Which outcome is essential for the first release? | Understand relative value |

A useful interview often combines all these question types.

## 9. Managing feedback and conflicting opinions

Stakeholders may disagree because they have different goals, responsibilities or information.

### Example conflict

- Sales wants customers to edit submitted applications.
- Compliance wants submitted information locked for audit reasons.
- Operations wants corrections to be possible without creating a new application.

The BA should not simply choose one opinion.

A structured approach:

1. Restate the underlying business needs.
2. Identify the impact and risk of each option.
3. Check policy, regulatory and contractual constraints with the relevant owners.
4. Explore alternatives.
5. Define decision criteria.
6. Identify who has decision authority.
7. Record the decision and rationale.
8. Update affected requirements, process flows and acceptance criteria.
9. Communicate the outcome to impacted stakeholders.

Possible solution for discussion: permit a controlled correction workflow with reason, authorization and audit history. This is only a proposed option until approved.

### Feedback classification

| Feedback type | Example | BA action |
|---|---|---|
| Clarification | What does "active customer" mean? | Define the term with the owner |
| Missing requirement | Include an export option | Assess scope and value |
| Defect in requirement | Two sections define different approval limits | Resolve inconsistency |
| Design suggestion | Put the filter above the table | Assess with users and design team |
| New scope | Add a mobile application | Raise change or backlog item |
| Constraint | Existing service cannot provide real-time data | Record dependency and assess options |
| Objection | This process will increase manual work | Investigate impact and alternatives |

Do not treat every comment as an approved change. Record it, assess it and follow the agreed decision process.

## 10. Recording meeting minutes

Meeting minutes are a concise record of the meeting, not a word-for-word transcript.

Include:
- Meeting title and purpose.
- Date, time and participants.
- Requirements or version reviewed.
- Key discussion points.
- Decisions and rationale.
- Open questions.
- Actions, owners and due dates.
- Approval status and next review date.

### Sample minutes

**Meeting:** Customer Portal Requirement Walkthrough  
**Purpose:** Review order tracking and notification requirements  
**Reviewed version:** Requirements v0.8  
**Participants:** Product Owner, Operations Lead, BA, Developer, QA representative

**Discussion**
- Customer needs to view current order status.
- Operations requires a clear status history.
- Notification timing needs confirmation.
- Support staff need controlled access to customer order details.

**Decisions**
- Order status history is in scope for the first release.
- Only authorized support roles may view customer details.
- Notification trigger and delivery timing remain open.

**Actions**

| Action ID | Action | Owner | Due date |
|---|---|---|---|
| ACT-01 | Confirm notification trigger and timing | Product Owner | To be agreed |
| ACT-02 | Confirm support-role permissions | Security/Operations | To be agreed |
| ACT-03 | Update acceptance criteria | BA | After decisions |

**Status:** Review completed; not yet approved for baseline.

This example demonstrates why a completed meeting is not automatically a signed-off requirement set.

## 11. Action log, decision log and issue log

These records serve different purposes.

### Action log
Tracks work someone must complete.

| ID | Action | Owner | Due date | Status |
|---|---|---|---|---|
| ACT-01 | Confirm notification timing | Product Owner | 15 Nov | Open |
| ACT-02 | Review access permissions | Security Lead | 16 Nov | In Progress |

### Decision log
Records a decision and why it was made.

| ID | Decision | Rationale | Decision owner | Date |
|---|---|---|---|---|
| DEC-01 | Order history included in release one | Required for customer support and visibility | Product Owner | 10 Nov |

### Issue/open-question log
Tracks unresolved matters that may affect scope, design or delivery.

| ID | Question/issue | Impact | Owner | Status |
|---|---|---|---|---|
| OQ-01 | What is the notification delivery target? | Acceptance criteria incomplete | Product Owner | Open |
| OQ-02 | Which support roles can view order details? | Access design cannot be finalized | Security Lead | Open |

Use separate records or a combined tool if it preserves clear categories, ownership and status.

## 12. Requirement versions, baseline and change control

A requirement document changes as stakeholders clarify needs. Teams need to know which version is current and which version was approved.

### 12.1 Versioning example

| Version | Date | Change | Status |
|---|---|---|---|
| 0.1 | 01 Nov | Initial draft | Draft |
| 0.2 | 04 Nov | Added customer search rules | In Review |
| 0.3 | 08 Nov | Updated approval workflow | In Review |
| 1.0 | 12 Nov | Reviewed and approved scope | Baseline |

These dates and versions are illustrative.

### 12.2 What is a baseline?

A requirements baseline is the agreed, controlled set of requirements used as a reference for design, development, testing and change management.

A baseline:
- Has a known version.
- Has an approval record.
- Defines the agreed scope at a point in time.
- Can be changed through an agreed change process.
- Provides traceability to later versions.

A baseline does not mean requirements can never change. It means changes are visible, assessed and approved appropriately.

### 12.3 Handling a change after sign-off

1. Record the change request.
2. Identify the reason and expected benefit.
3. Identify affected requirements and stakeholders.
4. Assess impact on scope, schedule, cost, design, data, integrations, security and testing.
5. Identify risks and dependencies.
6. Obtain a decision from the authorized owner or change authority.
7. Update requirements and related artifacts if approved.
8. Update version and baseline records.
9. Communicate the outcome.
10. Update traceability and test coverage.

Do not quietly edit an approved requirement and leave downstream teams using an old version.

## 13. Requirement sign-off

Sign-off is a formal acknowledgement or approval by an authorized stakeholder that a defined requirement set, scope or deliverable has been reviewed and accepted for the stated purpose.

Sign-off may be recorded through:
- An approved requirements document.
- A workflow in a requirements management tool.
- An approval email, if permitted by organizational policy.
- Meeting minutes with explicit approval.
- An electronic signature or governance record.

### 13.1 What sign-off should identify

A useful sign-off record contains:

| Field | Example |
|---|---|
| Project | Customer Portal |
| Artifact | Business and Functional Requirements |
| Version | 1.0 |
| Scope | Customer registration and order tracking |
| Exclusions | Payment processing in this release |
| Approver | Authorized Product Owner |
| Approval date | Date approval was given |
| Decision | Approved / Rejected / Approved with conditions |
| Conditions | Open items or limitations |
| Evidence | Approval record or workflow reference |

### 13.2 Before requesting sign-off

Check that:
- Business objectives and scope are clear.
- Requirements have unique IDs.
- Important terms are defined.
- Functional and non-functional requirements are covered.
- Business rules and exception flows are documented.
- Assumptions, constraints and dependencies are visible.
- Acceptance criteria are testable.
- Conflicts and high-impact open questions are resolved or explicitly accepted.
- Relevant stakeholders have reviewed the document.
- Comments and changes are incorporated.
- Traceability is maintained.
- The correct version and approver are identified.

### 13.3 Approved with conditions

Sometimes a stakeholder approves a requirement set while accepting a limited number of documented outstanding items.

Record:
- The exact condition.
- Why it remains open.
- Its business or delivery impact.
- The accountable owner.
- The target resolution date.
- Whether it blocks development, testing or release.

Never present conditional approval as unconditional approval.

## 14. The Business Analyst's role in review and sign-off

The BA is responsible for facilitating understanding and maintaining requirement quality, not for making every business decision.

Typical BA responsibilities:
- Prepare and maintain requirement artifacts.
- Identify the right stakeholders.
- Plan and facilitate reviews.
- Ask clarification questions.
- Capture feedback without losing its source.
- Identify conflicts, assumptions and gaps.
- Maintain action, decision and open-question logs.
- Update requirements and traceability.
- Explain change impact.
- Circulate the correct version.
- Track approval status.
- Communicate approved decisions.

The BA should not:
- Approve business scope without delegated authority.
- Hide unresolved questions to obtain a signature.
- Treat silence as approval unless a documented governance process explicitly says so.
- Change an approved requirement without change control.
- Promise technical feasibility without consulting the responsible specialists.
- Record a stakeholder as an approver when they only attended the meeting.

## 15. Measuring review effectiveness

Useful indicators include:

| Measure | What it tells you |
|---|---|
| Requirements reviewed | Progress through the review scope |
| Review comments by category | Common quality problems |
| Open questions | Remaining uncertainty |
| Conflicting requirements | Areas needing resolution |
| Rework caused by misunderstood requirements | Cost of unclear communication |
| Approval cycle time | Time taken to reach an approval decision |
| Requirements changed after baseline | Amount of post-baseline change |
| Requirements with acceptance criteria | Testability readiness |

Use metrics to improve the process, not to pressure stakeholders into approving incomplete work. A high approval rate is not proof of requirement quality.

## 16. Mini-project: Requirement Review Meeting Pack

<badge color="success">Day 39 practical project</badge>

### Project brief

Continue the Customer Portal project. Prepare a professional meeting pack to review the requirements with stakeholders, capture feedback, resolve open questions and obtain a documented sign-off decision.

### Deliverable A: Review-ready requirements

Prepare a small sample requirements set containing:
- Business objective and problem statement.
- Scope and exclusions.
- At least 10 uniquely identified requirements.
- Functional and non-functional requirements.
- Business rules.
- Acceptance criteria.
- Assumptions, constraints and dependencies.
- Requirement source and priority.

Ensure the requirements are clear and testable. Mark unconfirmed details as open questions rather than inventing approved rules.

### Deliverable B: Review meeting agenda

Include:
- Meeting purpose and expected outcome.
- Participants and their roles.
- Document version being reviewed.
- Topics and time allocation.
- Decisions required.
- Preparation material.
- Review rules and feedback process.

### Deliverable C: Review checklist

Review each requirement for:
- Business relevance.
- Clarity.
- Completeness.
- Consistency.
- Feasibility.
- Testability.
- Traceability.
- Priority.
- Dependencies and constraints.

Record the result and any action needed.

### Deliverable D: Feedback register

Create at least eight sample comments. Include examples of:
- Ambiguous wording.
- Missing business rule.
- Conflicting requirement.
- New scope request.
- Technical dependency.
- Security or permission question.
- Suggested usability improvement.
- Acceptance criterion clarification.

For each comment record:
- Comment ID.
- Requirement ID.
- Stakeholder and role.
- Feedback.
- Category.
- BA assessment.
- Decision or next action.
- Owner and status.

### Deliverable E: Meeting minutes and logs

Prepare:
- Meeting minutes.
- Action log with owner and due date.
- Decision log with rationale and approver.
- Open-question or issue log.

Make clear which items are decided and which remain unresolved.

### Deliverable F: Sign-off record

Create a sign-off sheet with:
- Project and artifact name.
- Requirement version.
- Scope and exclusions.
- Approver and authority.
- Approval decision.
- Conditions or exceptions.
- Date and evidence reference.

Use a fictional approver in the learning exercise and label it as a sample. Do not imply that a real stakeholder has approved the project.

### Deliverable G: Version and change history

Show an illustrative progression from draft to reviewed version to approved baseline. Include one example of a change request raised after baseline and demonstrate its impact assessment and decision.

### Suggested folder structure

~~~text
Requirement_Review_Meeting_Pack/
|
+-- 01_Requirements_v0.1.md
+-- 02_Review_Agenda.md
+-- 03_Requirement_Review_Checklist.xlsx
+-- 04_Feedback_Register.xlsx
+-- 05_Meeting_Minutes.md
+-- 06_Action_Log.xlsx
+-- 07_Decision_Log.xlsx
+-- 08_Open_Questions_Log.xlsx
+-- 09_Signoff_Record.md
+-- 10_Version_and_Change_History.md
~~~

### Sample sign-off template

~~~text
REQUIREMENT SIGN-OFF

Project:
Artifact:
Version:
Review date:
Scope:
Exclusions:

APPROVER
Name:
Role:
Approval authority:

DECISION
[ ] Approved
[ ] Approved with conditions
[ ] Rejected
[ ] Deferred

CONDITIONS / COMMENTS:

OPEN ITEMS AND OWNERS:

APPROVAL DATE:
APPROVAL EVIDENCE / REFERENCE:

Note: This is a training template. Use the organization's actual approval and records policy in a live project.
~~~

### Evaluation rubric

| Assessment area | Weight |
|---|---:|
| Requirement quality and testability | 20% |
| Review preparation and stakeholder mapping | 15% |
| Feedback capture and classification | 15% |
| Meeting minutes and action ownership | 15% |
| Decision and open-question tracking | 10% |
| Sign-off completeness and authority | 15% |
| Versioning and change control | 10% |
| **Total** | **100%** |

## 17. Common mistakes to avoid

1. Sending a document without explaining what feedback or decision is needed.
2. Inviting stakeholders without identifying their role.
3. Reviewing only wording and ignoring business rules or exceptions.
4. Using vague words without measurable definitions.
5. Treating every comment as an approved requirement.
6. Failing to record who made a decision.
7. Mixing actions, decisions and unresolved questions.
8. Sharing meeting minutes without owners or due dates.
9. Assuming meeting attendance means approval.
10. Treating silence as sign-off without an agreed policy.
11. Editing an approved baseline without change control.
12. Hiding unresolved risks or dependencies.
13. Requesting approval from someone without authority.
14. Failing to communicate the approved version to delivery teams.

## 18. Knowledge check

**Q1. What is the main purpose of a requirement review?**

A. To approve every idea immediately  
B. To check requirement quality, shared understanding and alignment  
C. To replace testing  
D. To assign developer salaries

**Answer: B.** Reviews identify ambiguity, gaps, conflicts and feasibility or testability concerns before delivery.

**Q2. Which is the most testable requirement?**

A. The application should be very fast  
B. The screen should look nice  
C. A successful submission displays a unique application reference  
D. Users should be happy

**Answer: C.** It describes an observable outcome. Any additional timing or format rule should be agreed separately.

**Q3. What should a BA do when stakeholders disagree?**

A. Choose a preferred stakeholder  
B. Hide the disagreement  
C. Clarify needs, assess impact, identify decision authority and record the decision  
D. Delete the requirement

**Answer: C.** The BA facilitates a transparent, evidence-based decision.

**Q4. What is the purpose of meeting minutes?**

A. To reproduce every spoken word  
B. To record key discussions, decisions, actions and open questions  
C. To replace the requirements document  
D. To guarantee approval

**Answer: B.** Minutes provide a concise and traceable record.

**Q5. What is a requirements baseline?**

A. An informal idea list  
B. An approved, controlled set of requirements used as a reference  
C. A list of developer names  
D. A test environment

**Answer: B.** A baseline is controlled but can change through an agreed process.

**Q6. What should happen when a stakeholder requests a new feature after sign-off?**

A. Quietly edit the approved document  
B. Ignore the stakeholder  
C. Record the change and assess its impact through change control  
D. Mark all existing tests as passed

**Answer: C.** Post-baseline changes need impact assessment and an authorized decision.

**Q7. Does attendance at a review meeting automatically mean sign-off?**

A. Yes  
B. No  
C. Only for developers  
D. Only if the meeting lasts one hour

**Answer: B.** Attendance and approval are different; approval must be explicit and authorized.

**Q8. Who should approve business requirements?**

A. Anyone who receives the email  
B. The authorized business owner or delegate  
C. Only the BA  
D. Any tester

**Answer: B.** Approval authority should be defined by project governance.

**Q9. What is the difference between an action log and a decision log?**

A. An action log tracks work to be done; a decision log records agreed choices and rationale  
B. They are identical  
C. An action log stores passwords  
D. A decision log stores test screenshots only

**Answer: A.** Both support traceability but serve different purposes.

**Q10. Why should requirement versions be controlled?**

A. To make documents longer  
B. To ensure teams know which version is current and approved  
C. To prevent all future changes  
D. To avoid stakeholder communication

**Answer: B.** Version control prevents teams from working from conflicting or outdated requirements.

## 19. Business Analyst interview questions and sample answers

### 1. How do you conduct a requirement review?
I first confirm the objective, scope, participants and document version. I check each requirement for clarity, completeness, consistency, feasibility, testability and traceability. During the walkthrough I capture feedback, decisions and open questions. Afterward I update the artifacts, circulate minutes and track approval.

### 2. What do you do when a requirement is ambiguous?
I identify the ambiguous term and ask neutral clarification questions. I use examples and exception scenarios to understand the intended business behaviour. I record the agreed definition, update the requirement and acceptance criteria, and confirm the revision with relevant stakeholders.

### 3. How do you handle conflicting stakeholder requirements?
I understand the business objective behind each position, identify impacts and constraints, and explore options with the stakeholders. If a decision cannot be reached collaboratively, I take the issue to the authorized decision-maker. I record the decision and rationale and update affected requirements.

### 4. What is a requirement walkthrough?
It is a collaborative review where the BA explains requirements step by step so stakeholders can validate their meaning, identify gaps and agree on open points. The BA records feedback, decisions and actions.

### 5. What is the difference between a review and sign-off?
A review checks quality and gathers feedback. Sign-off is an explicit approval by an authorized person for a defined artifact or scope. A reviewed document is not necessarily approved.

### 6. What is a requirements baseline?
A baseline is the controlled, approved set of requirements used as a reference for delivery. Changes after baseline are recorded, assessed and approved through change control.

### 7. What do you include in meeting minutes?
I include the purpose, date, participants, version reviewed, key discussion points, decisions, action owners, due dates and unresolved questions. I distinguish confirmed decisions from items still under discussion.

### 8. What is your role in requirement sign-off?
I prepare the correct version, confirm that review feedback is addressed, identify unresolved conditions, maintain traceability and route the artifact to the authorized approver. I record the approval evidence and communicate the approved baseline. I do not claim approval authority unless it has been delegated.

## 20. Quick revision sheet

| Term | Remember |
|---|---|
| Requirement review | Check quality and shared understanding |
| Walkthrough | Collaborative step-by-step review |
| Peer review | Review by another analyst or colleague |
| Stakeholder | Person or group affected by or influencing the work |
| Ambiguity | More than one possible interpretation |
| Action log | Work, owner and due date |
| Decision log | Agreed choice and rationale |
| Open-question log | Unresolved issue requiring an answer |
| Meeting minutes | Concise record of discussion and outcomes |
| Baseline | Approved, controlled requirement set |
| Version control | Identify and track artifact revisions |
| Change request | Proposed change to agreed scope or requirements |
| Sign-off | Explicit approval by an authorized person |
| Conditional approval | Approval with documented conditions |
| Traceability | Link requirements to sources and downstream artifacts |

## 21. Day 39 completion checklist

- [ ] I can explain why requirements need reviews.
- [ ] I can assess clarity, completeness, consistency and testability.
- [ ] I can prepare a requirement walkthrough.
- [ ] I can identify the right stakeholders.
- [ ] I can ask useful clarification questions.
- [ ] I can adapt communication to different stakeholder groups.
- [ ] I can manage feedback and conflicting opinions.
- [ ] I can prepare meeting minutes.
- [ ] I can maintain action, decision and open-question logs.
- [ ] I understand requirement versions and baselines.
- [ ] I can explain change control after sign-off.
- [ ] I understand approval authority and conditional sign-off.
- [ ] I have prepared the Requirement Review Meeting Pack mini-project.

## 22. Official learning references

- IIBA — Business Analysis resources and standards: https://www.iiba.org/
- IIBA — BABOK Guide overview: https://www.iiba.org/business-analysis-standards-and-resources/babok/
- Atlassian — Requirements management: https://www.atlassian.com/agile/product-management/requirements
- Atlassian — Stakeholder management: https://www.atlassian.com/work-management/project-management/stakeholder-management
- Microsoft Learn — Requirements and project documentation resources: https://learn.microsoft.com/
- PMI — Stakeholder engagement resources: https://www.pmi.org/

Use these as further reading. Follow the project's approved governance, document control and approval policies.

---

**Day 39 outcome:** You can prepare and facilitate requirement reviews, communicate with stakeholders, manage feedback and decisions, maintain requirement versions, and obtain explicit approval from the correct authority. Day 40 begins the end-to-end Business Analyst capstone.
