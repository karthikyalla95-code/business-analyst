# TechPhile.ai — Business Analyst Career Pathway

# Day 28: Jira for Business Analysts — Projects, Issues, Backlogs and Workflows

**Phase:** Agile Delivery and Product Collaboration  
**Estimated time:** 2–3 hours  
**Difficulty:** Beginner to Intermediate  
**Prerequisites:** Day 27 — Agile principles, Scrum, product backlog, user stories and acceptance criteria.

## Learning objectives

By the end of this lesson, you should be able to:

1. Explain what Jira is and how Business Analysts use it.
2. Distinguish projects, issues, issue types, boards, backlogs and workflows.
3. Understand Epics, Stories, Tasks, Bugs and Sub-tasks.
4. Create a clear user story with testable acceptance criteria.
5. Organize work in a backlog and understand sprint planning.
6. Read a Scrum or Kanban board and identify blocked work.
7. Use basic filters and Jira Query Language (JQL).
8. Track dependencies, requirement changes and delivery progress.
9. Build a small Jira-style workspace for an appointment-booking product.

> Jira's interface and terminology can vary by Jira Cloud edition, project template and organization configuration. This lesson teaches the underlying concepts; menu labels and available features may differ in your account.

## 1. What is Jira?

**Jira** is a work management and issue-tracking platform made by Atlassian. Software teams commonly use it to plan work, record requirements, track defects, organize delivery and make progress visible.

A Business Analyst may use Jira to:

- Record business requirements as backlog items.
- Write user stories and acceptance criteria.
- Link stories to Epics, tasks, defects and related work.
- Clarify requirements with developers and testers.
- Track questions, decisions, dependencies and blockers.
- Review work status and prepare stakeholder updates.
- Connect requirements with test evidence or delivery outcomes.

Jira does not replace understanding the business problem. A perfectly maintained board can still contain the wrong requirements. The BA must ensure that the work being tracked is valuable, clear and connected to the intended outcome.

### 1.1 Example: clinic appointment booking

A clinic wants to replace phone-based appointment booking with an online service.

A team creates a Jira project called **Clinic Appointment Booking**. Within it, the team tracks an Epic called **Patient Appointment Booking**, stories such as **View available slots** and **Book an appointment**, and bugs such as **Booking confirmation is not displayed**.

Each issue records the work, its status, priority, description, acceptance criteria and relevant links.

## 2. Jira building blocks

| Jira concept | Meaning | Example |
|---|---|---|
| Project | Place to organize related work | Clinic Appointment Booking |
| Issue / work item | One tracked unit of work | Book an appointment |
| Issue type | Category of work | Story, Bug, Task |
| Epic | Larger body of related work | Patient Appointment Booking |
| Story | User-focused capability | View available slots |
| Task | Supporting work | Review booking policy |
| Bug | Defect against expected behavior | Duplicate booking is accepted |
| Sub-task | Smaller piece of a parent issue | Validate slot conflict |
| Backlog | Ordered work awaiting selection | Stories not yet selected |
| Board | Visual view of work status | To Do → In Progress → Done |
| Sprint | Fixed-length Scrum event | One-week Sprint |
| Workflow | Statuses and transitions an issue follows | Open → In Progress → Review → Done |
| Label | Classification for filtering | booking, notifications |
| Component | Product or system area, if configured | Scheduling |
| Version / release | A planned product release marker | First clinic release |

Organizations can customize issue types, workflows, fields and permissions. Do not assume every Jira project looks identical.

## 3. Projects and project approaches

A Jira project groups related work. Teams may choose a project approach based on how work arrives and is delivered.

- **Scrum:** Work is planned in fixed-length Sprints using a backlog.
- **Kanban:** Work moves continuously through a visual workflow.
- **Business or work management:** Teams track operational tasks, approvals and processes.

A product team that plans work in Sprints may choose a Scrum project. A support team handling requests continuously may prefer Kanban.

Before creating a project, clarify:

1. What product, service or process will it support?
2. Who needs access?
3. Is the team using Scrum, Kanban or another approach?
4. What issue types are needed?
5. Which statuses and approval steps are necessary?
6. What information must be captured?
7. Who can create, edit, assign and close work?

Use the simplest structure that supports the real process. Too many issue types, custom fields and workflow stages create unnecessary administration.

## 4. Issue types in detail

### 4.1 Epic

An Epic represents a larger body of work that can be broken into smaller issues.

**Epic:** Patient Appointment Booking

Possible child stories:
- View available appointment slots.
- Book an available appointment.
- Receive booking confirmation.
- Cancel an appointment.
- Reschedule an appointment.

An Epic should represent a coherent capability or outcome, not become a bucket for unrelated work.

### 4.2 Story

A Story describes a capability from a user's perspective.

**Summary:** View available appointment slots

**User story:**

As a patient, I want to view available appointment slots so that I can choose a suitable appointment time.

**Acceptance criteria:**

1. Given a service and date are selected, when available slots exist, then the system displays those slots.
2. Given no slots are available, when the patient searches, then the system displays a clear no-availability message.
3. Given a slot is no longer available, when the patient attempts to select it, then the system prevents selection and refreshes availability.

### 4.3 Task

A Task records work that needs to be completed but may not be a user-facing capability.

Examples:
- Document the clinic's appointment cancellation policy.
- Confirm the time zone used by the scheduling service.
- Review access permissions for reception staff.

### 4.4 Bug

A Bug records a difference between actual and expected behavior.

**Summary:** System allows two patients to book the same slot

- Environment: Test environment.
- Steps to reproduce: Open the same slot in two sessions and confirm a booking in each.
- Expected result: Only one booking is confirmed.
- Actual result: Both bookings are confirmed.
- Impact: Staff may need to resolve conflicting appointments.
- Evidence: Attach approved screenshots, logs or test references. Never attach real patient information to a practice project.

### 4.5 Sub-task

A Sub-task breaks a parent issue into smaller pieces.

Example under **Book an appointment**:
- Confirm booking rules.
- Implement slot reservation.
- Test duplicate-booking prevention.

Do not split every tiny action into a separate issue. Create separate work items only when tracking them adds useful visibility.

## 5. Create a useful Jira story

A good issue should let another team member understand the work without repeatedly asking what it means.

### 5.1 Common story fields

| Field | What to enter | Example |
|---|---|---|
| Summary | Short, action-oriented title | View available appointment slots |
| Description | User story and business context | As a patient... |
| Acceptance criteria | Testable expected behavior | Given–When–Then cases |
| Issue type | Correct work category | Story |
| Parent / Epic | Related larger capability | Patient Appointment Booking |
| Priority | Relative importance or urgency | High |
| Assignee | Person progressing the issue | Agreed team member |
| Reporter | Person who created the issue | BA |
| Labels | Search classifications | booking, patient |
| Components | Product area, if configured | Scheduling |
| Due date | Date only when genuinely needed | Agreed target |
| Attachments | Supporting evidence | Approved process screenshot |
| Links | Related or blocking work | Slot rules issue |

Field names and availability vary by Jira configuration. Understand each field's purpose rather than memorizing one screen layout.

### 5.2 Reusable description template

~~~markdown
## Business context
Why is this capability needed?

## User story
As a [user],
I want [capability],
so that [benefit].

## Acceptance criteria
1. Given ...
   When ...
   Then ...

2. Given ...
   When ...
   Then ...

## Business rules
- Rule 1:
- Rule 2:

## Dependencies
- Related issue or decision:

## Open questions
- Question:
- Decision owner:

## Notes
Relevant constraints and supporting references.
~~~

Do not invent answers to fill every heading. Record unknown information as an open question with an owner where possible.

## 6. Backlog management and refinement

A backlog is an ordered list of work that may be selected for delivery. In Scrum, the Product Owner is accountable for effective Product Backlog management and ordering. A BA can support refinement by clarifying requirements, adding acceptance criteria, identifying dependencies and explaining business value.

### 6.1 Example product backlog

| Order | Type | Summary | Priority | Reason |
|---:|---|---|---|---|
| 1 | Story | View available slots | Highest | Entry point to booking |
| 2 | Story | Book an available appointment | Highest | Core user outcome |
| 3 | Story | Prevent duplicate booking | Highest | Booking integrity |
| 4 | Story | Receive confirmation | High | Reassures the patient |
| 5 | Story | Cancel appointment | High | Supports appointment changes |
| 6 | Story | Reschedule appointment | Medium | Useful follow-up capability |
| 7 | Task | Document staff booking rules | High | Clarifies operating policy |
| 8 | Story | View appointment history | Low | Can follow the core journey |

This is an illustrative ordering. The Product Owner should confirm priorities using stakeholder value, risk, dependencies, effort and release goals.

### 6.2 Refinement checklist

Before an issue is ready for planning, ask:

- Is the user or business need clear?
- Is the expected value understood?
- Are acceptance criteria testable?
- Are business rules and exceptions included?
- Are dependencies visible?
- Are open questions assigned to decision owners?
- Is the item small enough for the team's delivery approach?
- Can the team understand what evidence will show it is complete?

Some teams use a **Definition of Ready** as a local working agreement. It is not a required Scrum artifact or official Scrum event. Do not confuse it with the Definition of Done.

## 7. Scrum and Kanban boards

A board helps the team visualize work. A simple workflow might be:

**To Do → In Progress → Code Review → Testing → Done**

The exact statuses depend on the team's workflow. A board column may represent one or more workflow statuses.

A BA should look for:
- Issues moving through the workflow.
- Items blocked or waiting for decisions.
- Stories repeatedly returned from testing.
- Unclear acceptance criteria.
- Dependencies delaying work.
- Work marked Done before the agreed quality standard is met.

A board is not a productivity scorecard for individuals. Use it to understand flow, identify impediments and support collaboration.

### 7.1 Kanban and work in progress

A Kanban board shows work moving through stages continuously. Teams may set Work In Progress (WIP) limits to prevent too many items being worked on simultaneously.

Example:

| Backlog | To Do | In Progress | Review | Done |
|---|---|---|---|---|
| Appointment history | Cancel booking | Confirm rules | Validate reminder | View slots |
| Reports | Reschedule booking |  |  |  |

If the Review column has a WIP limit of 2 and already contains two items, the team should help clear review work before pulling another item into that stage.

## 8. Workflows, statuses and transitions

A **status** tells you the current state of an issue. A **transition** is an allowed movement from one status to another.

| Status | Meaning | Typical next step |
|---|---|---|
| To Do | Work has not started | Start work |
| In Progress | Someone is actively working | Submit for review |
| In Review | Work is being checked | Approve or return |
| Testing | Behavior is being verified | Pass or report defect |
| Done | Agreed completion criteria are met | Close or release as configured |

A real workflow may include Selected for Development, Blocked, Ready for QA or Awaiting Approval.

### 8.1 Recording a blocker

Suppose a story cannot proceed because the clinic has not confirmed cancellation rules.

Useful blocker note:

> Blocked: cancellation cutoff policy is not approved. Decision owner: Clinic Operations Manager. The booking flow cannot finalize cancellation behavior until the policy is confirmed.

Do not leave an issue sitting in In Progress without explaining the blocker, owner and next action.

## 9. Issue links, dependencies and traceability

Jira issues can be linked to show relationships. Common link types include:

- **blocks / is blocked by:** one issue prevents another from progressing.
- **relates to:** issues are connected but neither necessarily blocks the other.
- **duplicates / is duplicated by:** two issues describe the same work.
- **causes / is caused by:** a relationship available in some workflows.

Example:
- Story A: Define appointment slot rules.
- Story B: Book an appointment.
- Relationship: Story A blocks Story B until the rules are confirmed.

Link issues instead of copying the same requirement into multiple places. This reduces inconsistent updates.

Traceability can connect:

Business objective → Epic → Story → Acceptance criteria → Test case or evidence → Defect or release.

Jira alone does not guarantee complete traceability. The team must agree how links, test records, documents and approvals are maintained.

## 10. Search and filters

Jira search helps users find work by project, issue type, status, assignee, priority, label and dates. Depending on the interface and permissions, users may have basic search and advanced JQL.

### 10.1 What is JQL?

**Jira Query Language (JQL)** searches Jira issues using conditions. It is not SQL and does not query your business database.

Find open stories in an example project:

~~~jql
project = CLINIC
AND issuetype = Story
AND statusCategory != Done
ORDER BY priority DESC
~~~

Find issues assigned to the current user:

~~~jql
assignee = currentUser()
AND statusCategory != Done
ORDER BY updated DESC
~~~

Find high-priority unresolved bugs:

~~~jql
project = CLINIC
AND issuetype = Bug
AND priority in (Highest, High)
AND resolution is EMPTY
~~~

Find issues with a particular label:

~~~jql
project = CLINIC
AND labels = booking
ORDER BY created DESC
~~~

The project key CLINIC and priority names are examples. Replace them with the values configured in your Jira site. Some fields or operators depend on configuration and permissions.

### 10.2 JQL vs SQL

| JQL | SQL |
|---|---|
| Searches Jira issues | Queries relational database tables |
| Uses fields such as status, assignee and project | Uses columns such as order_date and customer_id |
| Filters work in Jira | Analyzes stored business data |
| Example: issuetype = Bug | Example: SELECT * FROM orders |

Use JQL for Jira work items and SQL for business data stored in databases.

## 11. Managing requirement changes in Jira

A stakeholder may request a new feature after a story has been estimated or selected for a Sprint.

A BA should:

1. Record the request and its business reason.
2. Identify affected Epics, stories, rules and users.
3. Clarify urgency, expected value and deadline.
4. Analyze dependencies, effort, risk and side effects with the team.
5. Update the relevant issue or create a new backlog item.
6. Keep the change history and decision rationale clear.
7. Ask the Product Owner to consider backlog ordering.
8. Communicate the agreed decision to stakeholders.
9. Update related acceptance criteria, process models and test evidence where required.

Do not silently edit acceptance criteria after development or testing has started. Discuss the change and make its impact visible.

## 12. Jira reports and dashboards

Reports and dashboards help teams understand delivery and work status. Availability depends on project type, configuration and plan.

| Report / view | What it helps answer |
|---|---|
| Sprint report | What was completed or not completed in a Sprint? |
| Burndown chart | How much estimated work remains over the Sprint? |
| Velocity chart | How much work did this Scrum team complete across Sprints? |
| Cumulative flow diagram | Where is work accumulating in the workflow? |
| Control chart | How long do issues take to move through the workflow? |
| Created vs resolved | Are incoming issues outpacing resolved issues? |
| Dashboard | What project information should be visible together? |

### 12.1 Interpret metrics carefully

- Velocity is a planning aid for a team, not a comparison score between individuals or teams.
- A burndown chart can be affected by scope changes and estimation updates.
- A high number of closed tickets does not prove business value.
- A cumulative flow diagram can reveal a growing queue, but the team must investigate why.
- Cycle time is elapsed time between defined start and finish points; confirm the team's definitions.

Connect delivery measures to outcomes such as reduced booking errors, faster processing or improved customer experience.

## 13. Practical mini-project — Create a Jira-style project

**Estimated time:** 60–90 minutes

**Scenario:** Use the clinic appointment-booking product from Day 27. If you have Jira Cloud access, create a practice project using an available Scrum or Kanban template. If you do not have access, complete the same exercise in a spreadsheet. Do not purchase a subscription solely for this lesson.

### 13.1 Project structure

Project name: **Clinic Appointment Booking**  
Suggested project key: **CLINIC** (the system may require another available key).

Create:
- One Epic: Patient Appointment Booking.
- At least 6 Stories.
- At least 2 Tasks.
- At least 2 sample Bugs.
- At least 2 linked dependencies.
- A simple board with statuses agreed by the team.

### 13.2 Starter issues

| Type | Summary | Priority |
|---|---|---|
| Epic | Patient Appointment Booking | Highest |
| Story | View available appointment slots | Highest |
| Story | Book an available appointment | Highest |
| Story | Prevent duplicate booking | Highest |
| Story | Receive booking confirmation | High |
| Story | Cancel appointment | High |
| Story | Reschedule appointment | Medium |
| Task | Confirm clinic scheduling rules | High |
| Task | Document cancellation policy | High |
| Bug | Booking confirmation is not displayed | High |
| Bug | Unavailable slot can still be selected | Highest |

The Bugs are sample records for practice. Do not represent them as real defects in a live product.

### 13.3 Create one story

For **View available appointment slots**, enter:

**Summary:** View available appointment slots

**Description:**

~~~markdown
## Business context
Patients currently call the clinic to ask which appointment times are available.

## User story
As a patient,
I want to view available appointment slots,
so that I can choose a suitable time.

## Acceptance criteria
1. Given a service and date are selected, when available slots exist, then the system displays those slots.
2. Given no slots are available, when the patient searches, then a clear no-availability message is displayed.
3. Given a slot is no longer available, when the patient attempts to select it, then the system prevents selection.

## Business rules
- Only slots published by the clinic can be displayed.
- Past appointment slots must not be offered.

## Open questions
- How often should availability refresh?
- Can a patient book multiple appointments?
~~~

Set the issue type to Story, link it to the Epic and apply a suitable priority. Assign it only if the team has agreed who owns the work.

### 13.4 Spreadsheet alternative

If Jira access is unavailable, create a CSV with these columns:

~~~csv
Issue_Key,Issue_Type,Summary,Description,Acceptance_Criteria,Priority,Status,Parent_Epic,Assignee,Labels,Blocked_By
~~~

Add the starter issues. Use consistent values for Issue_Type, Priority and Status.

### 13.5 Required deliverables

~~~text
Day_28_Jira_Practice/
├── README.md
├── jira_practice_backlog.csv
├── workflow.md
├── jql_queries.md
└── findings.md
~~~

- **jira_practice_backlog.csv:** issues and their fields.
- **workflow.md:** statuses, transitions and blocker-handling rules.
- **jql_queries.md:** at least four searches and a sentence explaining each.
- **findings.md:** what the backlog shows, key dependencies and the next recommended action.
- **README.md:** project purpose and how to review the practice files.

If you use Jira, include screenshots only after removing personal data, email addresses, tokens and confidential information.

### 13.6 Expected quality checks

- One Epic groups related stories.
- At least six Stories are written from a user perspective.
- Tasks are used for supporting work that is not a user story.
- Bugs include reproducible steps and expected vs actual behavior.
- Acceptance criteria are specific and testable.
- Dependencies are linked or clearly recorded.
- Statuses reflect the team's actual workflow.
- No story is marked Done merely because someone started it.
- JQL examples use the correct project key and fields.
- The report separates delivery activity from business outcomes.

## 14. Common Jira mistakes

| Mistake | Why it is a problem | Better approach |
|---|---|---|
| Creating a ticket without a clear summary | Team members cannot scan the backlog | Use a concise, action-oriented title |
| Writing vague acceptance criteria | Testing becomes subjective | Use observable, testable conditions |
| Putting everything in one Epic | Work becomes difficult to organize | Group by coherent capability or outcome |
| Creating an issue for every tiny action | Administrative overhead increases | Split only when separate tracking adds value |
| Assigning all work to the BA | Ownership becomes unclear | Agree responsibility with the team |
| Treating priority as a substitute for ordering | Different items may share a priority | Make backlog order explicit |
| Leaving blockers undocumented | Delays are hard to investigate | Record blocker, owner and next action |
| Using Done to mean development started | Progress becomes misleading | Apply agreed completion criteria |
| Duplicating requirements in tickets | Copies become inconsistent | Link related issues and maintain one source |
| Editing requirements without discussion | Team impact is hidden | Record and assess changes transparently |
| Comparing team velocity | Estimation differs between teams | Use velocity only for that team's planning |
| Treating JQL as SQL | Queries use different data and syntax | Use JQL for Jira and SQL for databases |

## 15. Daily quiz

**Q1. What is Jira mainly used for in a software delivery team?**

A. Replacing all stakeholder discussions  
B. Tracking and organizing work such as stories, tasks and bugs  
C. Automatically deciding business priorities  
D. Replacing the product itself

**Answer: B.** Jira helps organize and track work. It does not replace business analysis or stakeholder decisions.

**Q2. Which issue type is most suitable for a user-facing capability?**

A. Story  
B. Bug  
C. Sub-task  
D. Release

**Answer: A.** A Story describes a capability from a user's perspective.

**Q3. What does a Jira workflow define?**

A. The database schema of the product  
B. The statuses and allowed transitions for work items  
C. The company's annual budget  
D. The programming language used by Developers

**Answer: B.** A workflow describes how an issue moves through statuses and transitions.

**Q4. What does this JQL filter search for?**

~~~jql
issuetype = Bug AND statusCategory != Done
~~~

A. Completed stories  
B. Bugs that are not in the Done status category  
C. All projects owned by a user  
D. Database records with errors

**Answer: B.** It finds Bug issues that are not categorized as Done.

**Q5. Who is accountable for ordering the Product Backlog in Scrum?**

A. Business Analyst  
B. Scrum Master  
C. Product Owner  
D. Tester

**Answer: C.** The Product Owner is accountable for effective Product Backlog management, including ordering. A BA may support refinement and analysis.

## 16. Interview preparation

### Q1. How would you use Jira as a Business Analyst?

**Sample fresher answer:** I understand Jira as a work-tracking tool used to organize requirements, user stories, tasks and defects. In a BA workflow, I would create clear stories, add acceptance criteria, link related work, identify dependencies and monitor issue status. I would also use filters or JQL to find open stories and unresolved defects. I would be transparent about whether my experience is from hands-on practice or a live project.

**Follow-up:** What information should a good user story contain?

**Answer:** A clear summary, user story, business context, testable acceptance criteria, dependencies, open questions and relevant links. The exact fields depend on the team's working agreement.

### Q2. What is the difference between an Epic, Story, Task and Bug?

**Answer:** An Epic groups a larger capability or body of work. A Story describes a user need and benefit. A Task tracks supporting work that may not be user-facing. A Bug records behavior that differs from the expected result.

**Follow-up:** Can a Bug be linked to a Story?

**Answer:** Yes. Linking a defect to the affected story helps preserve traceability and shows which capability is impacted.

### Q3. How do you ensure a requirement is ready for development?

**Answer:** I check whether the business need and user are clear, acceptance criteria are testable, business rules and alternate scenarios are captured, dependencies are visible and open questions have owners. I then discuss uncertainty with the Product Owner and Developers. I follow the team's agreed refinement or readiness practices.

**Follow-up:** Is Definition of Ready a formal Scrum artifact?

**Answer:** No. Some teams use it as a local working agreement, but it is not one of the Scrum Guide's defined artifacts or commitments.

### Q4. What is JQL? How is it different from SQL?

**Answer:** JQL is Jira Query Language, used to search and filter Jira issues using fields such as project, status, assignee and issue type. SQL is used to query relational databases. They have different purposes and syntax.

**Follow-up:** Give an example of a JQL query.

~~~jql
project = CLINIC
AND issuetype = Bug
AND statusCategory != Done
ORDER BY priority DESC
~~~

This finds unresolved Bugs in the example project and sorts them by priority.

### Q5. How would you handle a requirement change after a story enters a Sprint?

**Answer:** I would record the reason for the change, assess its business value and impact, identify affected stories and dependencies, and discuss it with the Product Owner and Developers. The team would agree whether it can be handled without endangering the Sprint Goal or should be ordered in the Product Backlog. I would update the issue and communicate the decision.

**Follow-up:** Should a BA silently change acceptance criteria?

**Answer:** No. Changes should be discussed with the relevant people and recorded so development, testing and stakeholders share the same understanding.

## 17. Revision sheet

| Concept | Remember |
|---|---|
| Jira | Work and issue tracking platform |
| Project | Groups related work |
| Issue | One tracked unit of work |
| Epic | Larger body of related work |
| Story | User-focused capability |
| Task | Supporting work item |
| Bug | Defect against expected behavior |
| Sub-task | Smaller piece of parent work |
| Backlog | Ordered work awaiting selection |
| Board | Visualizes work status |
| Workflow | Statuses and transitions |
| Sprint | Fixed-length Scrum event |
| Acceptance criteria | Testable conditions for an issue |
| Issue link | Relationship or dependency between work items |
| JQL | Searches Jira issues |
| SQL | Queries relational database data |
| Dashboard | Brings selected project information together |
| Product Owner | Accountable for Product Backlog ordering |
| BA contribution | Clarify requirements, rules, dependencies and business value |

## 18. Daily completion checklist

- [ ] I can explain what Jira is used for.
- [ ] I can distinguish projects, issues, boards and workflows.
- [ ] I can explain Epic, Story, Task, Bug and Sub-task.
- [ ] I can write a story with clear acceptance criteria.
- [ ] I understand backlog refinement and issue ordering.
- [ ] I can explain Scrum and Kanban board use.
- [ ] I can identify a blocker and record its owner and next action.
- [ ] I understand issue links and requirement traceability.
- [ ] I understand basic JQL and how it differs from SQL.
- [ ] I completed the Jira-style project mini-project.
- [ ] I attempted the quiz and reviewed the explanations.
- [ ] I can answer interview questions honestly, distinguishing practice from professional experience.

**Day 28 is complete when** you can organize a small product backlog, write actionable Jira issues, explain a workflow, find work with basic JQL and show how issue tracking supports delivery without replacing sound business analysis.

## 19. References and further learning

1. [Atlassian Support — Jira Software documentation](https://support.atlassian.com/jira-software-cloud/) — project, backlog, board and issue guidance.
2. [Atlassian — What is Jira?](https://www.atlassian.com/software/jira/guides/getting-started/overview) — product overview and common terminology.
3. [Atlassian Support — JQL](https://support.atlassian.com/jira-software-cloud/docs/what-is-advanced-search-in-jira-cloud/) — advanced search and Jira Query Language.
4. [The Scrum Guide](https://scrumguides.org/scrum-guide.html) — official Scrum accountabilities, events, artifacts and commitments.

**Practice note:** Jira configuration varies between organizations. Learn the concepts and confirm the team's own issue types, field meanings, permissions and workflow before using Jira on a real project.
