# Day 33: Change Requests, Risks, Dependencies and Issue Management

**Phase:** 5 — Agile, Scrum and Project Management  
**Approved topic:** Change requests, risks, dependencies and issue management  
**Approved independent mini-project:** Project Risk Register  
**Estimated time:** 2–3 hours  
**Difficulty:** Intermediate  
**Prerequisites:** Days 27–32 — Agile, Scrum, backlog management, Jira, sprint tracking and delivery reporting.

---

## 1. Why this matters

A team is building an online customer portal. During development:

- A business stakeholder requests an additional payment method.
- The payment provider has not confirmed when its sandbox will be available.
- A developer discovers that the existing customer database cannot store a newly required field.
- A security review identifies a possible exposure of customer information.

These are different kinds of project information. A Business Analyst must help the team distinguish a requested change from a risk, dependency, issue or defect. If everything is simply called a “blocker”, the team cannot make good decisions.

This lesson teaches you to record, assess, communicate and follow up on these items in a structured way.

## 2. Learning objectives

By the end of this lesson, you should be able to:

1. Explain change requests and assess their impact on scope, time, cost, quality and risk.
2. Distinguish risks, issues, assumptions, dependencies and defects.
3. Identify and prioritize project risks using probability and impact.
4. Build a risk register with owners, responses and review dates.
5. Track dependencies and issues through resolution.
6. Describe a controlled change process in an Agile or plan-driven project.
7. Communicate decisions and escalation needs clearly.

## 3. Words you need

| Term | Plain-English meaning | Example |
|---|---|---|
| Change request | A formal or recorded request to change an agreed requirement, scope, product or plan | Add UPI as a payment option |
| Risk | An uncertain event that may affect an objective | Payment provider sandbox may be delayed |
| Issue | A problem that has already happened and needs action | Sandbox access is unavailable today |
| Dependency | Work, information or a decision that relies on another person, team or system | Integration testing depends on provider credentials |
| Assumption | Something treated as true for planning until verified | Provider will support test credentials this week |
| Constraint | A fixed limit the project must work within | Launch must happen before 30 June |
| Defect | A product or deliverable does not meet an expected requirement or quality standard | Checkout total is calculated incorrectly |
| Impact | The consequence if an event occurs or a problem continues | Testing delayed by three days |
| Probability | How likely a risk is to occur | Possible, likely or rare |
| Mitigation | Action to reduce the probability or impact of a risk | Request sandbox access early |
| Contingency | Planned action if the risk occurs | Use a mock service for internal testing |
| Avoidance | Change the plan to remove a threat | Use an already-approved payment provider |
| Transfer / sharing | Allocate or share some risk exposure with another party | Contractual service commitment or insurance, where appropriate |
| Acceptance | Acknowledge a risk and monitor it, with or without a contingency | Accept a low-impact delay risk |
| Owner | Person accountable for monitoring or taking action on an item | Integration lead |
| Escalation | Taking an item to someone with authority to resolve it | Ask the sponsor to resolve a cross-team priority conflict |
| Change authority | Person or group authorized to approve a particular change | Product Owner for backlog ordering; sponsor for a baseline change under project governance |
| Traceability | Ability to connect a change to its source, decision, requirements and tests | CR-014 links to US-122 and UAT-031 |

**Quick distinction:**

- A risk might happen.
- An issue has happened.
- A dependency is something that must be provided or completed for other work to proceed.
- A change request asks to alter an agreed item.
- A defect is a failure to meet an expected result.

One event can move through categories. For example, “provider access may be late” is a risk. Once the promised date passes and access is still unavailable, it becomes an issue.

## 4. Change requests

### 4.1 What is a change request?

A change request (CR) records a proposal to modify an agreed part of a project or product. It may relate to:

- A new or changed business requirement.
- A feature addition or removal.
- A change to scope, schedule or budget.
- A business rule.
- A technical design or integration.
- A compliance or security requirement.
- A release or acceptance condition.

A request is not automatically approved just because a stakeholder asks for it. The team needs to understand its value, urgency, impact and authority.

### 4.2 Change request lifecycle

A practical controlled flow:

1. **Raise:** Record who requested the change, when and why.
2. **Clarify:** Understand the problem or opportunity, not just the proposed solution.
3. **Analyze:** Identify affected requirements, users, processes, systems, data, tests and dependencies.
4. **Estimate:** Ask the relevant delivery specialists to estimate effort and schedule impact.
5. **Decide:** Obtain approval, rejection, deferral or a request for more information from the appropriate authority.
6. **Update:** Update requirements, backlog, scope baseline or plans as appropriate.
7. **Implement:** Deliver the approved change.
8. **Verify:** Test the change and check that it meets the agreed acceptance criteria.
9. **Close:** Record the outcome and communicate it to affected stakeholders.

<escape>Requester → Log → Clarify → Impact analysis → Decision → Update records → Implement → Verify → Close</escape>

### 4.3 Change request form

| Field | What to record |
|---|---|
| Change ID | Unique reference, e.g. CR-014 |
| Title | Short, clear description |
| Requester | Person or role requesting the change |
| Date raised | Date received |
| Business reason | Problem, opportunity or regulation behind the request |
| Current state | What happens today |
| Proposed change | What should change |
| Expected benefit | Value expected for users or the business |
| Affected requirements | Requirement or story IDs |
| Impact analysis | Scope, time, cost, quality, security, data and operations |
| Dependencies | Other teams, vendors, systems or decisions involved |
| Risks | New or changed uncertainties |
| Priority | Urgency and business importance |
| Decision | Approved, rejected, deferred or more information required |
| Decision authority | Person or group who made the decision |
| Decision date | When the decision was made |
| Implementation reference | Epic, story, task or release |
| Verification evidence | Test results, UAT or sign-off |
| Status | Current lifecycle state |

### 4.4 Impact analysis

Never estimate a change by looking only at development effort. Consider the wider effect.

| Impact area | Questions |
|---|---|
| Scope | What new work is added? What existing work changes? |
| Schedule | Does the release date or sequence change? |
| Cost | Are extra people, licenses, vendor services or infrastructure needed? |
| Quality | Does the change introduce new test cases or quality risks? |
| Security and privacy | Does it change access, personal data, retention or exposure? |
| Data | Are fields, migration, validation or reporting affected? |
| Integration | Do APIs, vendors or connected systems change? |
| Operations | Are support, training, monitoring or procedures affected? |
| Compliance | Does legal, regulatory or policy review become necessary? |
| Benefits | Does the expected business value change? |

Example: Adding UPI payment may require a provider integration, new user-interface choices, transaction-status handling, reconciliation changes, security review, error messages, test cases and customer-support guidance. It is not simply “one extra button”.

### 4.5 Change control in Agile and plan-driven work

**Plan-driven project:** Changes to an approved scope or baseline may need a formal change-control process and approval from a designated authority.

**Agile product development:** Product needs can evolve. The Product Owner orders the Product Backlog, and new information can be discussed and reflected in backlog items. The Sprint Goal and Sprint Backlog are handled according to Scrum; a change should not endanger the Sprint Goal. The Developers and Product Owner collaborate on scope adjustments during the Sprint as appropriate.

Do not apply a heavy approval form to every backlog clarification. Use governance proportionate to the change:
- A wording clarification may need a quick confirmation.
- A new feature may need refinement and prioritization.
- A regulatory change may need documented analysis, specialist review and formal approval.
- A change to a contractual or approved project baseline may require the defined change authority.

The Scrum Guide does not prescribe a separate “change request board” or a formal change-control committee. Organizations may use these as governance practices, but do not describe them as Scrum events or artifacts.

## 5. Risk management

### 5.1 What is a project risk?

A risk is an uncertain event or condition that, if it occurs, affects one or more objectives. Effects may be negative (threats) or positive (opportunities).

Examples:
- Threat: A vendor API may not be ready before integration testing.
- Opportunity: A reusable component may reduce implementation time.

A useful risk statement includes:
- **Cause:** Why the uncertainty exists.
- **Event:** What might happen.
- **Effect:** What objective may be affected.

Example:

“Because the payment provider has not confirmed sandbox availability (cause), test credentials may arrive late (event), delaying integration testing and putting the release date at risk (effect).”

Avoid vague entries such as “API risk” or “testing problem”.

### 5.2 Risk identification techniques

A BA can help identify risks through:

- Stakeholder interviews.
- Workshops and brainstorming.
- Process walkthroughs.
- Assumption analysis.
- Dependency mapping.
- Review of previous project lessons.
- Vendor and contract review.
- Technical and security reviews.
- Data-quality checks.
- Examination of project plans and delivery reports.

Ask questions such as:
- What must be true for this plan to work?
- What external decision or system are we waiting for?
- What could prevent users from adopting the solution?
- What happens if a key person is unavailable?
- What data or security assumption has not been verified?
- Which requirement is unclear or likely to change?

### 5.3 Probability and impact

A simple qualitative scale is often enough for an entry-level project risk register.

**Probability scale**

| Score | Label | Example interpretation |
|---:|---|---|
| 1 | Rare | Unlikely under current conditions |
| 2 | Unlikely | Could happen, but not expected |
| 3 | Possible | Plausible during the project |
| 4 | Likely | Expected unless action is taken |
| 5 | Almost certain | Very likely or already emerging |

**Impact scale**

| Score | Label | Example interpretation |
|---:|---|---|
| 1 | Very low | Negligible effect; handled within normal work |
| 2 | Low | Small rework or limited delay |
| 3 | Moderate | Noticeable effect on a milestone, cost or quality |
| 4 | High | Major milestone, customer or operational impact |
| 5 | Critical | Threatens a key objective, compliance or major service |

Organizations should define what each scale means for their context. A 5-point scale is a simple prioritization aid, not a universal standard.

### 5.4 Calculate a simple risk score

A common qualitative method is:

**Risk score = Probability × Impact**

Example:
- Probability = 4 (Likely)
- Impact = 5 (Critical)
- Risk score = 4 × 5 = **20**

For this lesson, use the following illustrative bands:

| Score | Priority |
|---:|---|
| 1–4 | Low |
| 5–9 | Moderate |
| 10–16 | High |
| 17–25 | Critical |

These bands are an example for learning. A real organization should agree its own thresholds and escalation rules.

**Important limitation:** Multiplication can hide different situations. A 5 × 2 risk and a 2 × 5 risk both score 10, but one may be frequent and minor while the other is rare and severe. Read the description and impact, not only the number.

### 5.5 Risk response strategies

For threats:
- **Avoid:** Change the plan so the threat no longer applies.
- **Mitigate:** Reduce probability or impact.
- **Transfer/share:** Allocate or share some exposure with another party, while recognizing that accountability may remain.
- **Accept:** Monitor the risk and take no proactive action beyond an agreed contingency if appropriate.

For opportunities:
- **Exploit:** Make the opportunity happen.
- **Enhance:** Increase its probability or benefit.
- **Share:** Work with another party to realize it.
- **Accept:** Take advantage if it occurs without actively pursuing it.

Example: For possible vendor delay:
- Mitigation: Request test access early and confirm a named vendor contact.
- Contingency: Use a mock service for internal tests if approved.
- Trigger: Sandbox credentials are not received by the agreed date.
- Owner: Integration lead.

A response should be an action, not a vague phrase such as “monitor closely”.

## 6. The Project Risk Register

A risk register is a working record of identified risks and their management.

### 6.1 Recommended fields

| Field | Purpose |
|---|---|
| Risk ID | Unique reference such as R-001 |
| Date identified | When the risk was recorded |
| Risk statement | Cause, uncertain event and effect |
| Category | Vendor, technical, schedule, data, security, people, operational, etc. |
| Probability | Agreed probability score |
| Impact | Agreed impact score |
| Score / priority | Calculated rating |
| Response strategy | Avoid, mitigate, transfer/share or accept |
| Mitigation action | Work to reduce exposure |
| Contingency | What to do if the risk occurs |
| Trigger | Observable sign that action is needed |
| Owner | Person accountable for monitoring and response |
| Due date | Date for the next action |
| Status | Open, monitoring, occurring, closed or accepted |
| Last reviewed | Most recent review date |
| Residual risk | Exposure remaining after response |

### 6.2 Sample risk register

| ID | Risk | P | I | Score | Response / next action | Owner | Status |
|---|---|---:|---:|---:|---|---|---|
| R-001 | Provider sandbox may be delayed, affecting integration tests | 4 | 4 | 16 | Confirm access date; prepare approved mock-service plan | Integration lead | Open |
| R-002 | Customer data fields may be incomplete, causing migration rework | 3 | 4 | 12 | Profile sample data and agree mandatory-field rules | Data analyst | Monitoring |
| R-003 | Key approver may be unavailable during UAT | 3 | 3 | 9 | Identify backup approver and reserve review time | Project manager | Open |
| R-004 | Reusable UI component may reduce implementation effort | 3 | 2 | 6 | Validate reuse opportunity during design review | Tech lead | Opportunity |

### 6.3 Risk ownership and review

A risk owner:
- Understands the risk.
- Checks whether probability or impact has changed.
- Coordinates the agreed response.
- Watches for triggers.
- Escalates when thresholds are crossed.
- Updates the register and communicates status.

The owner does not necessarily perform every action. For example, a project manager may own a vendor risk while a technical lead performs the technical mitigation.

Review risks at an agreed cadence, such as a weekly project review, and whenever a significant trigger occurs. Do not leave the register untouched until the final week.

## 7. Dependencies

### 7.1 What is a dependency?

A dependency exists when an activity, decision or deliverable relies on another item.

Examples:
- API development depends on receiving a confirmed API contract.
- UAT depends on a test environment and representative test data.
- A wireframe depends on approved business rules.
- Release depends on security approval.
- A report depends on a reliable data extract.

### 7.2 Types of dependencies

| Type | Meaning | Example |
|---|---|---|
| Finish-to-Start (FS) | Successor starts after predecessor finishes | Testing starts after build is ready |
| Start-to-Start (SS) | Successor starts after predecessor starts | Documentation begins once development starts |
| Finish-to-Finish (FF) | Successor finishes after predecessor finishes | Final review completes after implementation completes |
| Start-to-Finish (SF) | Successor cannot finish until predecessor starts | A rare shift-handover arrangement |

Most simple project plans use Finish-to-Start dependencies. Do not force every relationship into a dependency type if the team has not defined it.

Dependencies can also be:
- **Internal:** Between activities or teams within the project.
- **External:** On a vendor, regulator, customer or outside team.
- **Technical:** Between systems, components or environments.
- **Business:** On an approval, policy, decision or business operation.

### 7.3 Dependency log

| ID | Required item | Needed by | Provider / owner | Dependent work | Status | Action |
|---|---|---|---|---|---|---|
| D-001 | Payment API contract | 12 May | Vendor contact | Integration design | Pending | Confirm delivery date |
| D-002 | Approved checkout rules | 14 May | Product Owner | User stories and tests | In review | Resolve tax/refund rules |
| D-003 | UAT test data | 20 May | Data team | UAT execution | Not started | Prepare masked test data |

Track the date needed, not just the date requested. An item delivered late may still be on time if the dependent activity does not need it yet.

### 7.4 Dependency analysis questions

- What exactly is needed?
- Who provides it?
- Who is accountable for obtaining it?
- When is it needed?
- Which work is blocked if it is late?
- Is there an alternative?
- What is the escalation route?
- How will completion be verified?

## 8. Issue and defect management

### 8.1 Issue lifecycle

A simple issue lifecycle:

1. Identify the issue.
2. Record a clear description and evidence.
3. Assess impact and urgency.
4. Assign an owner.
5. Agree the next action and target date.
6. Escalate if the issue exceeds authority or threatens an objective.
7. Verify the resolution.
8. Close with evidence and record any learning.

### 8.2 Issue log fields

| Field | Purpose |
|---|---|
| Issue ID | Unique reference |
| Summary | Short description |
| Date raised | When it was found |
| Description / evidence | What happened and how it was observed |
| Impact | Effect on user, scope, time, cost or quality |
| Priority | Relative urgency |
| Owner | Person responsible for coordinating resolution |
| Action | Next step |
| Due date | Target date |
| Status | New, assigned, in progress, blocked, resolved, closed |
| Resolution evidence | How the fix was verified |

### 8.3 Priority vs severity

- **Severity** describes how serious the effect is.
- **Priority** describes how soon the team should address it, considering urgency and business context.

A serious security defect may have both high severity and high priority. A low-severity wording defect on a page used in a regulatory submission may still have high priority because of the deadline.

Do not use severity and priority as interchangeable labels.

### 8.4 Defect report essentials

A useful defect report includes:
- Defect ID and concise title.
- Environment and build/version.
- Preconditions.
- Steps to reproduce.
- Expected result.
- Actual result.
- Evidence such as screenshot, log or response (without exposing secrets or personal data).
- Severity and priority.
- Reporter and assigned owner.
- Current status and verification result.

Example:

**Title:** Checkout displays the wrong total after applying a discount.

- Preconditions: Cart contains eligible items; discount code is valid.
- Steps: Add two items, apply code SAVE10, open order summary.
- Expected: Discount is applied according to the agreed business rule.
- Actual: Discount is subtracted twice.
- Impact: Customer may be charged an incorrect amount.
- Evidence: Synthetic test order ID and sanitized screenshot.
- Next action: Assign to checkout team and verify against the approved pricing rule.

## 9. How the records connect

A change, risk, dependency, issue and defect should not live in disconnected spreadsheets.

Example chain:

- CR-014 requests UPI payment.
- Impact analysis identifies a dependency on vendor API credentials (D-006).
- The credentials may arrive late, creating risk R-008.
- The delivery date passes without access, so the risk becomes issue I-012.
- Integration testing later finds a failed payment-status mapping, recorded as defect BUG-031.
- The defect links to the affected requirement and test case.

Use IDs and cross-references so a reviewer can follow the history.

## 10. Follow along: create a risk register in Excel or Google Sheets

Create a workbook named **Project_Risk_Register.xlsx** and a sheet called **Risks**.

Enter these columns in row 1:

~~~text
Risk_ID | Risk_Statement | Probability | Impact | Score | Priority | Response | Owner | Trigger | Due_Date | Status
~~~

Add these sample rows:

| Risk_ID | Risk_Statement | Probability | Impact | Response | Owner | Trigger | Due_Date | Status |
|---|---|---:|---:|---|---|---|---|---|
| R-001 | Vendor sandbox may be delayed | 4 | 4 | Mitigate | Integration lead | Credentials not received by agreed date | 15-May | Open |
| R-002 | Customer data may contain missing mandatory fields | 3 | 4 | Mitigate | Data analyst | Validation failure exceeds agreed threshold | 17-May | Monitoring |
| R-003 | UAT approver may be unavailable | 3 | 3 | Mitigate | BA | No confirmation by booking deadline | 18-May | Open |
| R-004 | Reusable component may reduce build effort | 3 | 2 | Enhance | Tech lead | Design review confirms reuse | 19-May | Open |

### Step 1 — Calculate score

If Probability is in column C and Impact is in column D, enter in E2:

~~~excel
=C2*D2
~~~

Fill the formula down.

Expected scores: **16, 12, 9, 6**.

### Step 2 — Assign an illustrative priority

Enter in F2:

~~~excel
=IF(E2>=17,"Critical",IF(E2>=10,"High",IF(E2>=5,"Moderate","Low")))
~~~

Fill down.

Expected priorities: **High, High, Moderate, Moderate**.

The fourth row is an opportunity. In a real register, do not blindly interpret an opportunity's score as threat severity; label opportunity type and define a suitable response.

### Step 3 — Filter open risks

Turn on filters and select Status = Open. Review the risks that require follow-up.

### Step 4 — Sort by score

Sort the score column from largest to smallest. Check whether any high-impact item needs escalation even if its score is not the largest.

### Step 5 — Add a review field

Add a column named Last_Reviewed. Enter the review date whenever the risk is reassessed. A register without review dates can become stale.

## 11. Industry scenario: customer portal delivery

A company is launching a customer portal with account registration, order tracking and online payment.

At the planning workshop, the BA records:
- A request to add UPI payment.
- A dependency on a vendor API contract.
- A risk that customer records may be missing required contact fields.
- An issue: the test environment is unavailable.
- A defect: order status is displayed incorrectly for cancelled orders.

The BA should:
1. Record the UPI request as a change or backlog proposal, then clarify value and analyze impact.
2. Add the API contract to the dependency log with provider, needed-by date and affected work.
3. Write the data-quality risk with cause, event, effect, score, owner and response.
4. Record the unavailable environment as an issue because it has already happened.
5. Log the incorrect order status as a defect with reproducible steps and expected/actual results.
6. Link each record to affected requirements, stories and tests.

Do not assume the UPI change is approved, that the vendor will be late, or that the data problem will occur. Keep facts and uncertainty separate.

## 12. Independent mini-project: Project Risk Register

### 12.1 Problem statement

You are supporting a project to launch a customer onboarding portal. The project team needs a consistent record of threats, opportunities, dependencies and current issues so it can decide what needs action.

**Objective:** Create a Project Risk Register with at least six well-written risk entries, a dependency log and an issue log. Prioritize the risks and recommend practical responses.

### 12.2 Skills practiced

- Risk identification and clear risk statements.
- Probability and impact assessment.
- Risk response planning and ownership.
- Dependency tracking.
- Issue and defect recording.
- Change impact analysis.
- Spreadsheet validation and stakeholder communication.

### 12.3 Project scenario and constraints

The onboarding portal must support:
- Customer registration.
- Identity verification through an external provider.
- Profile creation.
- Email confirmation.
- Customer-support handoff.

Constraints:
- The target release date is fixed for planning purposes.
- The external identity provider controls its API and test environment.
- Customer information must be protected.
- Business rules require approval from the Product Owner.
- UAT needs business representatives.

Do not invent a real company's private information. Use synthetic project records.

### 12.4 Files and workspace

Create:

~~~text
Day_33_Project_Risk_Register/
├── README.md
├── scenario_inputs.md
├── risk_register.xlsx
├── dependency_log.csv
├── issue_log.csv
└── risk_summary.md
~~~

| File | Purpose | Your action |
|---|---|---|
| README.md | Instructions and submission checklist | Read and complete |
| scenario_inputs.md | Project context and sample events | Read-only input |
| risk_register.xlsx | Risk register and scoring | Create and edit |
| dependency_log.csv | External and internal dependencies | Create and edit |
| issue_log.csv | Already-occurring problems | Create and edit |
| risk_summary.md | Stakeholder-facing summary | Create and edit |

### 12.5 Scenario inputs

Save as **scenario_inputs.md**:

~~~markdown
# Customer Onboarding Portal — Scenario Inputs

1. The identity provider has not confirmed the test-environment access date.
2. Some sample customer records are missing a mandatory contact field.
3. The business approver has not confirmed UAT availability.
4. The email service provider has announced planned maintenance near the test window.
5. The support team has not received the new handoff procedure.
6. A reusable registration component may be available from another internal project.
7. The test environment is currently unavailable.
8. A test reveals that a failed identity check is incorrectly shown as successful.

Use these events to classify information carefully:
- Some are uncertain future events (risks).
- Some are dependencies.
- Some have already happened (issues).
- One is a product defect.
- One may be a positive opportunity.

Do not record every line as a risk. Classify each item and explain your reasoning.
~~~

### 12.6 Tasks

1. Create at least six risk entries, including at least one opportunity.
2. Write each threat as cause → uncertain event → effect.
3. Give probability and impact scores using the lesson's 1–5 scales.
4. Calculate score and assign the illustrative priority band.
5. Select a response strategy and write a specific action.
6. Add a trigger, owner, due date, status and last-reviewed date.
7. Create a dependency log with at least three entries.
8. Create an issue log for the unavailable test environment.
9. Record the failed identity-check behavior as a defect with expected and actual results.
10. Write a one-page risk summary identifying the three most important items and decisions required.

### 12.7 Dependency log template

Save as **dependency_log.csv**:

~~~csv
dependency_id,required_item,provider,needed_by,dependent_work,status,next_action,owner
D-001,Identity provider test credentials,External identity provider,2026-05-12,Identity integration testing,Pending,Confirm access date,Integration lead
D-002,Approved identity-check business rules,Product Owner,2026-05-13,Requirements and UAT cases,In review,Resolve rejection and retry rules,Business Analyst
D-003,UAT business representative availability,Operations manager,2026-05-18,UAT execution,Pending,Confirm primary and backup approver,BA
~~~

### 12.8 Issue log template

Save as **issue_log.csv**:

~~~csv
issue_id,type,summary,impact,priority,owner,next_action,status
I-001,Issue,Test environment unavailable,Integration and UAT preparation delayed,High,Environment owner,Restore service and notify team,Open
BUG-001,Defect,Failed identity check shown as successful,Incorrect onboarding outcome and potential control failure,Critical,Application team,Reproduce and correct status mapping,Open
~~~

### 12.9 Risk register template

Create a sheet with these columns:

~~~text
Risk_ID,Date_Identified,Risk_Statement,Category,Probability,Impact,Score,Priority,Response_Strategy,Mitigation_Action,Contingency,Trigger,Owner,Due_Date,Status,Last_Reviewed,Residual_Risk
~~~

### 12.10 Risk summary template

Save as **risk_summary.md**:

~~~markdown
# Project Risk Summary — Customer Onboarding Portal

## Overall view
- Reporting date:
- Overall risk status:
- Main reason:

## Top risks
| Risk ID | Risk statement | Score | Response | Owner | Next action |
|---|---|---:|---|---|---|

## Dependencies requiring attention
| Dependency ID | Needed item | Needed by | Owner | Current status |
|---|---|---|---|---|

## Current issues and defects
| ID | Description | Impact | Priority | Next action |
|---|---|---|---|---|

## Decisions or escalation required
1.
2.

## Assumptions and limitations
-
~~~

### 12.11 Expected classification

Use this as a guide after attempting the classification:

| Scenario input | Suitable classification | Reason |
|---|---|---|
| Provider has not confirmed future access date | Risk and dependency | Future uncertainty plus required external input |
| Missing mandatory fields in sample records | Data-quality issue or observed condition; may create further risks | The missing data is already observed |
| Approver availability not confirmed | Risk and dependency | Future availability is uncertain |
| Planned email maintenance near testing | Risk and dependency | External event may affect the test window |
| Support team has not received procedure | Issue or readiness gap, depending on agreed due date | Current preparation is incomplete |
| Reusable component may be available | Opportunity | Potential positive effect, not yet verified |
| Test environment currently unavailable | Issue | It has already happened |
| Failed identity check shown as successful | Defect | Actual behavior violates expected control |

### 12.12 Validation checklist

- [ ] At least six risks/opportunities are recorded.
- [ ] Risk statements contain cause, event and effect.
- [ ] Probability and impact scores are within 1–5.
- [ ] Score formulas are correct.
- [ ] Priority bands follow the stated example.
- [ ] Every open risk has an owner and next action.
- [ ] Triggers and due dates are specific.
- [ ] Opportunity is identified separately from threats.
- [ ] Dependency log identifies provider, needed-by date and dependent work.
- [ ] Existing issue is not incorrectly recorded only as a future risk.
- [ ] Defect includes expected and actual behavior.
- [ ] Risk summary identifies decisions and escalation needs.

### 12.13 Common errors and fixes

| Error | Why it is wrong | Fix |
|---|---|---|
| “API risk” with no detail | No event or effect is clear | Write cause, uncertain event and consequence |
| Giving every risk a score of 5 | No meaningful prioritization | Use evidence and the agreed scale |
| No risk owner | No one is accountable for follow-up | Assign a role or named project owner |
| “Monitor” as the only response | No action or trigger exists | Define what to monitor, who checks and when |
| Treating an existing outage as a risk only | The problem has already occurred | Record it as an issue and assess any future related risks separately |
| Recording a defect as a change request | A failure against an existing requirement is not automatically a new feature | Log defect and link the requirement |
| Closing a risk when mitigation starts | Exposure may remain | Close only when no longer relevant or formally accepted under governance |
| No cross-references | Change, risk and issue history cannot be followed | Link IDs across the records |

### 12.14 Stuck ladder

1. Re-read Sections 3–9 and classify each item before writing a register entry.
2. Hint: ask “Has it happened yet?” and “Is it an uncertain event or a required input?”
3. Compare your risk statement with the provider-delay example in Section 5.
4. Review the common-errors table.
5. After a genuine attempt, compare your classification with the expected table and document why any alternative classification is reasonable.

### 12.15 Submission evidence

Submit:
- Completed risk_register.xlsx.
- dependency_log.csv.
- issue_log.csv.
- risk_summary.md.
- Screenshot of the prioritized risk register (remove personal account details).
- A short explanation of one risk that became an issue, and what changed in the record.

Optional extension: add a change request CR-001 for a new identity-verification method. Complete its impact analysis and link it to the relevant dependencies and risks.

## 13. Common professional mistakes

1. **Confusing a request with approval:** A stakeholder request is not authorization to change an agreed baseline.
2. **Recording symptoms instead of risks:** “Testing delayed” may be an issue; “vendor may delay credentials, which could delay testing” is a risk.
3. **No ownership:** A register without accountable owners becomes a passive list.
4. **No trigger:** Without a trigger, the team may react too late.
5. **No residual risk:** A mitigation action may reduce but not remove exposure.
6. **Ignoring positive risks:** Opportunities can also be managed.
7. **Using scores mechanically:** Scores support judgment; they do not replace it.
8. **Failing to link records:** A decision should be traceable to requirements, implementation and tests.
9. **Escalating without a proposed action:** State what decision is needed and by when.
10. **Treating every change as bad:** A controlled change can improve business value or address a mandatory need.

## 14. Daily quiz

Choose one answer for each question. Answers and explanations follow.

**Q1. A vendor may deliver API credentials late next month. What is this today?**

A. A defect  
B. A risk  
C. A closed issue  
D. A completed dependency  

**Q2. The vendor's agreed delivery date has passed and the credentials have not arrived. What should be recorded?**

A. Only an opportunity  
B. A completed change request  
C. An issue, while retaining any relevant ongoing risk information  
D. A user story marked Done  

**Q3. A risk has probability 3 and impact 4. What is its score using the lesson's simple formula?**

A. 7  
B. 12  
C. 34  
D. 1  

**Q4. Which is the strongest risk statement?**

A. “Testing”  
B. “Vendor problem”  
C. “Because the vendor API contract is unconfirmed, the integration interface may change, causing rework in the test plan.”  
D. “The project is bad.”  

**Q5. A tester observes that a valid customer is rejected even though the approved rule says the customer should pass. What should be logged?**

A. A defect with steps, expected result and actual result  
B. A velocity target  
C. A new Sprint Goal  
D. A completed risk  

### Answers and explanations

1. **B — A risk.** The delay is uncertain and has not yet happened.
2. **C — An issue.** The missed date is now a current problem. A related future consequence may still be tracked as a risk.
3. **B — 12.** Probability × impact = 3 × 4 = 12.
4. **C — The complete cause-event-effect statement.** It explains uncertainty and consequence.
5. **A — A defect.** The observed product behavior does not meet the approved expected result.

## 15. Interview preparation

### Question 1: What is the difference between a risk and an issue?

**Answer:** A risk is an uncertain future event that may affect a project objective. An issue is a problem that has already occurred and needs action. For example, a vendor may delay API credentials: that is a risk. If the delivery date passes and the credentials are still missing, it is an issue.

**Follow-up:** Can a risk become an issue?

**Answer:** Yes. When the uncertain event occurs, the team should update the records and manage the resulting issue. The team may also track any further risks caused by that issue.

### Question 2: How do you assess a change request?

**Answer:** First I clarify the business reason and expected value. Then I identify affected requirements, processes, users, systems, data, integrations, tests and dependencies. I ask the relevant specialists to assess effort, schedule, cost, quality, security and operational impact. I record the decision from the correct authority and update the relevant backlog, requirements and traceability records.

**Follow-up:** What if the requester says the change is very small?

**Answer:** I would still clarify the impact. A small interface change can affect accessibility, security, data or testing. The amount of analysis should be proportionate to the actual risk and governance rules.

### Question 3: What should a good risk register contain?

**Answer:** It should contain a unique ID, clear risk statement, category, probability, impact, priority, response, mitigation action, contingency, trigger, owner, due date, status and review date. It should be updated as the project learns more.

**Follow-up:** Is a high risk score always the first item to address?

**Answer:** It is a useful signal, but not the only factor. Regulatory exposure, customer harm, timing, dependencies and the cost of delay may justify different ordering. The team should use its agreed escalation rules and judgment.

## 16. Revision sheet

- **Change request:** Proposal to alter an agreed requirement, scope or plan.
- **Risk:** Uncertain future event that may affect an objective.
- **Issue:** Problem that has already occurred.
- **Dependency:** Required input, action or decision on which other work relies.
- **Defect:** Product behavior that fails an expected requirement or quality standard.
- **Risk score:** Probability × impact, using an agreed scale.
- **Risk statement:** Cause → uncertain event → effect.
- **Risk response:** Avoid, mitigate, transfer/share or accept (for threats).
- **Dependency log:** What is needed, from whom, by when and for which work.
- **Good issue record:** Evidence, impact, priority, owner, action and resolution verification.
- **Change control:** Clarify, analyze, decide, update, implement and verify.
- **Key habit:** Keep facts, assumptions and uncertainty separate.

## 17. Daily assessment and completion checklist

### Concept completion
- [ ] I can distinguish a change request, risk, issue, dependency, assumption and defect.
- [ ] I can explain the change request lifecycle.
- [ ] I can write a cause-event-effect risk statement.
- [ ] I can calculate and interpret a simple risk score.
- [ ] I can explain risk response strategies.
- [ ] I can describe how dependencies and issues are tracked.

### Practical completion
- [ ] I created the Project Risk Register.
- [ ] I recorded at least six risks/opportunities.
- [ ] Each open risk has an owner, action, trigger and due date.
- [ ] I created a dependency log.
- [ ] I created an issue log and defect record.
- [ ] I wrote the risk summary and identified decisions needed.

### Validation and communication
- [ ] Formulas and priority bands are correct.
- [ ] Risk and issue classifications are defensible.
- [ ] Records are linked where appropriate.
- [ ] Assumptions and limitations are visible.
- [ ] I completed the quiz and reviewed incorrect answers.
- [ ] I can answer at least two interview questions without reading.

**Day 33 is complete when your risk register, dependency log, issue log and summary are understandable, traceable and supported by evidence.**

## 18. References

- Project Management Institute — Risk management overview: https://www.pmi.org/learning/library
- Scrum Guide (2020): https://scrumguides.org/scrum-guide.html
- Atlassian — Project management and risk concepts: https://www.atlassian.com/work-management/project-management
- Atlassian Jira documentation: https://support.atlassian.com/jira-software-cloud/
- IIBA — Business Analysis resources: https://www.iiba.org/business-analysis-blogs/

---

**Roadmap alignment:** Day 33 follows the approved syllabus topic “Change requests, risks, dependencies and issue management” and uses the exact approved mini-project title “Project Risk Register”.
