# Day 41: Capstone — Elicitation, User Stories and Functional Requirements

**Phase:** 7 — End-to-End Business Analysis Capstone  
**Estimated time:** 2–3 hours  
**Difficulty:** Intermediate  
**Approved mini-project:** Requirements specification  
**Scenario:** Customer Support Request Management, continued from Day 40

## 1. Why this matters

Day 40 established the business problem, stakeholders and scope. A delivery team still needs to know exactly what the proposed solution must do. "Make support faster" is not enough to design or test a system. The BA must discover what users need, clarify rules and exceptions, document requirements, and agree how completion will be verified.

Today you will create a draft Requirements Specification that continues the same fictional online retailer scenario. Do not design screens or create AS-IS/TO-BE process models yet; those are later capstone activities.

## 2. Words you need

| Term | Meaning | Example |
|---|---|---|
| Elicitation | Discovering needs through conversations, observation and evidence | Interviewing an agent about request assignment |
| Requirement | A capability or condition needed by a stakeholder or solution | The solution records the received date |
| Functional requirement (FR) | What the solution must do | An authorized agent can assign a request |
| Non-functional requirement (NFR) | A quality or operating condition | A page meets an agreed response-time target |
| User story | A short capability statement from a user's viewpoint | As an agent, I want to assign a request so ownership is clear |
| Acceptance criteria | Conditions that prove a story is acceptable | A valid assignment displays the selected owner |
| Epic | A large work area split into smaller stories | Request management |
| Business rule | A policy that governs behaviour | Only a supervisor may reopen a closed request |
| Assumption | Something treated as true until confirmed | Agents will have individual accounts |
| Constraint | A fixed limit | Existing company sign-in must be used |
| Dependency | Something another activity relies on | Customer records must be available |
| Priority | Relative importance | Must have for the first release |
| Traceability | Linking a requirement to its source and tests | FR-03 links to US-02 and TC-05 |
| Baseline | An approved reference version | Requirements Specification v1.0 |
| Open question | An unresolved point needing a decision | Can customers check status online? |

## 3. Capstone scenario and discovery context

A fictional mid-sized online retailer receives customer questions and complaints through email, telephone and a website contact form. Support agents use separate inboxes and spreadsheets. Managers have difficulty seeing overall workload and overdue requests. Customers sometimes contact the company more than once because they do not know whether a request has been received.

These are learning assumptions, not verified facts about a real organization. In a real project, validate them with stakeholders and evidence.

| Area | Initial information | BA action |
|---|---|---|
| Channels | Email, telephone and website form | Confirm how each channel enters the process |
| Tracking | Separate inboxes and spreadsheets | Observe actual work and confirm records |
| Ownership | Managers have limited visibility | Ask how ownership is decided |
| Customer updates | Acknowledgement may be inconsistent | Confirm expected communication |
| Repeat contacts | Some customers contact support again | Request data and define measurement |
| Solution | No product selected | Document needs before choosing technology |

### Elicitation-to-specification flow

~~~text
Prepare
  -> Identify stakeholders and sources
  -> Ask, observe and examine evidence
  -> Record raw statements and questions
  -> Analyze and resolve ambiguity
  -> Write requirements and user stories
  -> Add acceptance criteria and priority
  -> Review, trace and baseline
~~~

A stakeholder request is an input to analysis, not automatically an approved requirement.

## 4. Prepare elicitation

### 4.1 Identify stakeholders and what to learn

| Stakeholder | Information they can provide | Useful questions |
|---|---|---|
| Support agent | Daily work, exceptions and pain points | How do you record a new request? What happens when information is missing? |
| Team lead | Assignment, workload and escalation | How are requests assigned? When is a request overdue? |
| Operations manager | Objectives and reporting | Which measures help you manage the service? |
| Customer representative | Customer expectations | What confirmation reassures a customer that a request was received? |
| IT/security representative | Identity, access and constraints | What sign-in and access rules apply? |
| Compliance/privacy representative | Retention and data handling | Which approved policies govern customer data? |

One person may represent a group, but do not assume their preferences represent every user.

### 4.2 Select an elicitation technique

| Technique | Best use | Example | Limitation |
|---|---|---|---|
| Interview | Detailed individual experience | Ask an agent to explain a difficult case | May reflect one person's experience |
| Workshop | Resolve shared questions | Agree request status definitions | Dominant participants may influence discussion |
| Observation | See actual work | Watch an agent record a phone request | Rare exceptions may not occur during observation |
| Document analysis | Understand existing rules and records | Review request spreadsheets | Documents may be outdated |
| Questionnaire | Gather comparable responses at scale | Ask agents which fields are often missing | Limited ability to probe |
| System/interface analysis | Understand existing fields and behaviour | Inspect the contact form | Access or technical help may be needed |
| Data analysis | Quantify patterns | Calculate request volume by channel | Data definitions and quality must be checked |

Use multiple sources for important needs. Compare what people say with observed work and available records.

### 4.3 Plan a 30-minute interview

| Time | Activity | Output |
|---:|---|---|
| 0–3 min | Explain purpose and role | Shared context |
| 3–8 min | Ask about current workflow | Process overview |
| 8–18 min | Explore normal and exception cases | Detailed needs |
| 18–24 min | Discuss pain points and desired outcomes | Candidate requirements |
| 24–27 min | Read back key findings | Corrections |
| 27–30 min | Confirm questions and next steps | Action list |

### 4.4 Ask neutral, useful questions

Open questions:
- Walk me through what happens when a customer contacts support.
- What information do you need before acting?
- Where do delays or hand-offs occur?
- How do you know a request has been resolved?

Probing questions:
- Can you give me a recent example?
- What happens if the customer has no order number?
- Who may change this status?
- Is this always true, or are there exceptions?
- How would we verify that the requirement works?

Avoid leading questions. Instead of "Would automatic assignment solve this?", ask "How is assignment handled today, and what outcome would improve it?"

### 4.5 Keep raw statements separate from interpretation

| ID | Source | Raw statement | BA interpretation | Status |
|---|---|---|---|---|
| DISC-01 | Agent | "I need to know who is handling this request." | Need for visible ownership | Candidate |
| DISC-02 | Team lead | "I cannot see all open work in one place." | Need for consolidated workload visibility | Candidate |
| DISC-03 | Customer representative | "I want confirmation my message was received." | Need for acknowledgement | Candidate |
| DISC-04 | IT representative | "Use the company sign-in." | Possible authentication constraint | To confirm |

Do not turn a raw statement into a detailed technical design without clarification.

## 5. Analyze and refine requirements

### 5.1 Separate need, requirement and solution

| Level | Example |
|---|---|
| Business need | Improve visibility of customer support work |
| Stakeholder requirement | A team lead needs to see requests assigned to the support team |
| Functional requirement | The solution shall provide an authorized team lead with a filterable list of requests |
| Design choice | Use a particular database, framework or cloud service |

The BA documents what is needed. Technical design choices belong with the appropriate design and engineering roles, informed by business constraints.

### 5.2 Requirement quality checklist

A good requirement is:

- Necessary: supports a real business or stakeholder need.
- Clear: has one reasonable interpretation.
- Complete: enough information exists to understand the expected behaviour.
- Consistent: does not conflict with another approved requirement.
- Feasible: can reasonably be delivered within known constraints.
- Testable: someone can determine whether it has been met.
- Traceable: its source and related tests can be identified.
- Prioritized: its relative importance is known.
- Atomic: describes one principal behaviour or condition.
- Unambiguous: avoids undefined words such as fast, easy and user-friendly.

### 5.3 Improve weak statements

| Weak statement | Problem | Better candidate |
|---|---|---|
| The system should be user-friendly | No measurable meaning | An agent can create a request using defined mandatory fields and receives field-level validation |
| Requests should be handled quickly | No agreed target or start event | The business owner shall define the target response time and the event that starts the clock |
| The system must be secure | Too broad | Access to request records shall follow the approved role-permission matrix |
| Managers need reports | Missing detail | An authorized manager can view open request counts grouped by status for a selected date range |
| Customers should get updates | Missing trigger and channel | After successful website submission, the solution displays a confirmation reference and sends an acknowledgement to the submitted email address, subject to confirmed policy |

These are candidate statements. Confirm exact rules, targets and policy with stakeholders.

### 5.4 Functional and non-functional requirements

**Functional requirements describe what the solution does.** Examples:
- Create a support request.
- Generate a unique request reference.
- Record request channel and received date.
- Assign a request to an authorized agent.
- Update request status.
- Search using agreed filters.
- Record resolution details.
- Display acknowledgement to a customer.

**Non-functional requirements describe quality or operating conditions.** Examples:
- Security: users access only records permitted by their role.
- Performance: a specified action meets an agreed response-time target under defined load.
- Availability: the service meets an agreed availability target.
- Usability: key tasks meet a defined usability criterion.
- Accessibility: interfaces conform to the organization's selected standard.
- Auditability: specified changes record who changed what and when.
- Retention: records follow approved retention and disposal policy.

Do not invent numeric targets. If no target exists, record an open question and assign an owner.

### 5.5 Business rules

Business rules express policies or decisions, not screen behaviour.

| ID | Candidate rule | Clarification needed |
|---|---|---|
| BR-01 | Every saved request receives a unique reference | Confirm format and uniqueness scope |
| BR-02 | A request has a recorded channel | Confirm permitted channel values |
| BR-03 | Only authorized users may reassign requests | Confirm roles and permissions |
| BR-04 | Closed requests cannot be edited by ordinary agents | Confirm reopening exceptions |
| BR-05 | A request cannot be resolved without resolution details | Confirm mandatory fields |

Label unconfirmed rules as candidates, not approved policy.

### 5.6 Scope boundaries

Use the Day 40 initiation pack as the boundary. Candidate first-release capabilities:
- Record requests received by support.
- Store core request details and channel.
- Assign requests to an authorized owner.
- Track status and resolution.
- Search and view requests.
- Provide basic operational visibility.

Candidate exclusions unless approved through change control:
- Replacing the e-commerce platform.
- Changing payment processing.
- Building a full CRM suite.
- Automating every email and telephone conversation.
- Adding AI-based classification.

Record inclusions and exclusions in the scope register. Seek approval before expanding the boundary.

## 6. Write user stories

A user story describes a capability from the perspective of the person who benefits.

~~~text
As a [type of user],
I want [capability],
so that [benefit or outcome].
~~~

Example: "As a support agent, I want to assign a request to an owner so that responsibility for the next action is clear."

A story is not a full specification. Add acceptance criteria, business rules, priority and relevant data needs.

### 6.1 Candidate stories

| Story ID | User story | Candidate priority |
|---|---|---|
| US-01 | As an agent, I want to create a support request so issues are recorded consistently | Must |
| US-02 | As an agent, I want to assign a request to an authorized owner so responsibility is clear | Must |
| US-03 | As an agent, I want to update a request status so progress is visible | Must |
| US-04 | As a team lead, I want to filter requests by status and owner so I can monitor workload | Must |
| US-05 | As an agent, I want to search by request reference so I can find a conversation quickly | Should |
| US-06 | As a customer, I want confirmation after website submission so I know it was received | Should; confirm policy |
| US-07 | As a manager, I want a summary by status so I can review operations | Could, subject to scope |

Priorities are examples. Confirm them with the authorized business decision-maker.

### 6.2 INVEST quality check

| Letter | Meaning | Check |
|---|---|---|
| I | Independent | Can it be planned without unnecessary dependency? |
| N | Negotiable | Does it describe an outcome rather than dictate every design detail? |
| V | Valuable | Is user or business benefit clear? |
| E | Estimable | Does the team understand enough to estimate it? |
| S | Small | Can it fit a reasonable delivery increment? |
| T | Testable | Can criteria prove completion? |

Split a story that is too large by user outcome, workflow, rule or scenario. Do not split only by technical layer if that hides user value.

## 7. Write acceptance criteria

Acceptance criteria define conditions that must be met for a story to be accepted.

### 7.1 Given–When–Then

~~~text
Given [starting context]
When [an action occurs]
Then [observable expected result]
~~~

Example for US-01:
- Given an authorized agent is creating a request,
- When the agent enters all mandatory valid details and saves,
- Then the solution stores the request and displays its unique reference.

Negative scenario:
- Given a mandatory field is missing,
- When the agent attempts to save,
- Then the solution identifies the missing field and does not create an incomplete request.

Avoid vague criteria such as "the screen looks good" or "the search works properly." State observable behaviour, conditions and expected result.

### 7.2 Worked story: assign a request

**US-02:** As a support agent, I want to assign a request to an authorized owner so that responsibility for the next action is clear.

| AC ID | Given | When | Then |
|---|---|---|---|
| AC-02-01 | An authorized agent opens an unassigned request | The agent selects an eligible owner and saves | The request displays the selected owner |
| AC-02-02 | The agent lacks assignment permission | The agent attempts to change the owner | The change is prevented and a clear message appears |
| AC-02-03 | The selected owner is inactive or ineligible | The agent attempts assignment | The assignment is rejected and current ownership remains unchanged |
| AC-02-04 | A valid reassignment is saved | The request is viewed again | The latest owner is displayed; audit history is recorded if approved |

The audit expectation in AC-02-04 must link to an approved audit requirement. Confirm it rather than assuming it is policy.

## 8. Prioritize requirements

MoSCoW helps stakeholders decide what matters most when capacity is limited.

| Priority | Meaning | Example |
|---|---|---|
| Must have | Essential for the agreed release | Create and save a request |
| Should have | Important, but a workable temporary approach may exist | Search by request reference |
| Could have | Useful if capacity allows | Optional dashboard customization |
| Won't have this time | Explicitly excluded from this release | AI-generated response suggestions |

A Won't-have item is not necessarily rejected forever. Record the release boundary and revisit through change control.

Ask:
- What outcome does this support?
- Who is affected if it is not delivered?
- Is it legally, contractually or operationally mandatory?
- Is there a safe workaround?
- Does another requirement depend on it?
- What are effort and delivery risks?
- Who has authority to approve priority?

Priority labels do not replace stakeholder decisions.

## 9. Capture data and integration needs

### 9.1 Candidate data dictionary

| Field | Meaning | Example | Validation question |
|---|---|---|---|
| Request reference | Unique identifier | SR-10025 | Who generates it? Can it be reused? |
| Customer identifier | Link to customer record | C-2041 | Is it mandatory for every channel? |
| Customer name | Display name | Asha Rao | Is it retrieved from a trusted source? |
| Contact detail | Reply route | Email address | Which formats and validation rules apply? |
| Request channel | How request arrived | Website, email, phone | Are these approved values? |
| Subject | Short description | Delivery status | Is there a length limit? |
| Description | Issue details | Package not received | What sensitive data should not be entered? |
| Received date/time | When request entered process | 2026-11-07 10:30 | Which time zone is authoritative? |
| Status | Current lifecycle state | Open | What states and transitions are valid? |
| Owner | Person responsible | Agent 12 | Can a request be unassigned? |
| Resolution notes | How it was resolved | Delivery status confirmed | When are notes mandatory? |

This is not a final database schema. Confirm data ownership, privacy, retention and field rules with relevant stakeholders.

### 9.2 Integration questions

- Must the solution retrieve customer details from an existing system?
- Is an order identifier needed to investigate delivery issues?
- Which system is authoritative for customer information?
- What happens if an external service is unavailable?
- Which data may be shared?
- Are retries, duplicate submissions and error messages required?

The BA records business needs and failure scenarios. Detailed API design belongs to technical analysis.

## 10. Traceability

Traceability connects a requirement to why it exists and how it will be verified.

~~~text
Business objective
       |
       v
Stakeholder need
       |
       v
User story
       |
       v
Functional requirement
       |
       v
Acceptance criterion
       |
       v
Test case
~~~

Example:

| Objective | Story | Requirement | Acceptance criterion | Future test |
|---|---|---|---|---|
| Improve ownership visibility | US-02 | FR-03 | AC-02-01, AC-02-02 | TC-05, TC-06 |
| Record issues consistently | US-01 | FR-01, FR-02 | AC-01-01, AC-01-02 | TC-01, TC-02 |
| Monitor workload | US-04 | FR-07 | AC-04-01 | TC-10 |

IDs are examples. Keep identifiers stable when wording changes. Record version history rather than reusing an ID for a different requirement.

## 11. Review and baseline the specification

Before approval:
1. Check each requirement against the quality checklist.
2. Confirm its source or documented rationale.
3. Check duplicates, contradictions and missing scenarios.
4. Confirm scope and priority with the appropriate decision-maker.
5. Confirm acceptance criteria are observable and testable.
6. Link stories, requirements and criteria in the traceability matrix.
7. Record open questions, assumptions and unresolved decisions.
8. Share the document for review and record feedback.
9. Update version history.
10. Obtain approval from the authorized stakeholder before marking it baselined.

A baseline is an agreed reference version, not a ban on future changes. Later changes must be assessed, approved and recorded through change control.

| Version | Date | Change | Status |
|---|---|---|---|
| 0.1 | 2026-11-07 | Initial draft | Draft |
| 0.2 | To be agreed | Updated after stakeholder review | Review |
| 1.0 | To be agreed | Approved first baseline | Approved by authorized approver |

Dates are illustrative. Use actual dates and approver details only in your own project evidence.

## 12. Follow along: create the specification

Use any Markdown or document editor.

1. Create a folder named customer-support-capstone.
2. Create requirements_specification.md.
3. Add project name, author, version, status and date.
4. Copy the problem and scope from your Day 40 initiation pack.
5. Add stakeholder and source tables.
6. Add the discovery log; keep raw statements separate from interpretation.
7. Write at least five user stories with unique IDs.
8. Add at least two acceptance criteria per story.
9. Add functional requirements with unique IDs.
10. Add NFR candidates; label unknown targets as open questions.
11. Add business rules, data needs, assumptions and dependencies.
12. Create a traceability matrix.
13. Record unresolved questions, owners and decisions.
14. Save as version 0.1 Draft. Do not claim approval without actual approval.

**Expected result:** A reviewer can understand who needs what, why it matters, what the solution should do and how to verify it.

## 13. Worked example: stakeholder statement to testable requirement

**Raw statement:** "I need to find a customer's request without opening every spreadsheet."

**Clarify**
- What information is available when searching?
- Can the agent search by request reference or customer identifier?
- Are partial matches required?
- Which records may the agent view?
- What should happen when no match exists?

**User story**

As an authorized support agent, I want to search for a request using its reference so that I can locate the correct record without checking multiple tracking files.

**Functional requirement**

FR-05: The solution shall allow an authorized support agent to search for a request using its exact request reference.

**Acceptance criteria**
- Given an authorized agent enters an existing reference, when search is submitted, then the matching permitted request is displayed.
- Given the reference does not exist, when search is submitted, then a no-results message is displayed.
- Given a user lacks permission to view a record, when access is attempted, then access is denied.

**Traceability**

| Link | ID |
|---|---|
| Discovery source | DISC-05 |
| User story | US-05 |
| Requirement | FR-05 |
| Acceptance criteria | AC-05-01 to AC-05-03 |
| Future tests | TC-08 to TC-10 |

**Open questions:** Should partial reference search be supported? Should search activity be audited? What response-time target is required? Record owners and obtain decisions.

## 14. Common mistakes and fixes

| Mistake | Why it is a problem | Fix |
|---|---|---|
| Designing before understanding the need | Can lock the team into a poor solution | Ask about problem and outcome first |
| Copying stakeholder words as final requirements | Statements may be vague or conflicting | Clarify and analyze without changing intent |
| Combining multiple behaviours in one requirement | Difficult to estimate, trace and test | Split into atomic requirements |
| Using fast, easy or secure without definition | Cannot agree whether requirement is met | Define measurable or observable conditions |
| Stories without acceptance criteria | Completion is open to interpretation | Add positive, negative and exception cases |
| Everything marked Must | Priorities stop helping | Discuss value, risk and release constraints |
| Confusing functional and non-functional requirements | Quality needs may be missed | Classify behaviour separately from quality |
| Treating assumptions as facts | Teams may build on false information | Label and assign an owner to validate |
| Missing requirement source | Reason for requirement is lost | Record stakeholder, policy, observation or evidence |
| Changing a requirement without history | Approved version becomes unclear | Use IDs, versions and change records |
| Inventing a service target | Creates unsupported commitment | Record open question until agreed |

## 15. If you are stuck

Use this ladder in order:
1. Re-read Sections 4–7 and identify user, need and benefit.
2. Hint: write the story from the user's point of view, then ask what observable result proves it works.
3. Compare with the worked search example in Section 13.
4. Review the common mistakes in Section 14.
5. Only after a genuine attempt, compare your draft with the sample artifacts in the project section and record what you changed.

## 16. Independent mini-project: Requirements specification

### 16.1 Problem and objective

Continue the fictional Customer Support Request Management capstone from Day 40. Produce a Requirements Specification that translates the business problem and agreed scope into structured, reviewable and testable requirements.

**Objective:** Create a clear baseline candidate that stakeholders can review and the delivery team can use for later process modelling, prototype design and UAT planning.

### 16.2 Skills and prerequisites

Skills: elicitation, discovery logging, requirement analysis, FR/NFR writing, user stories, acceptance criteria, business rules, prioritization, traceability and review.

Prerequisites: Day 40 Business Analysis Initiation Pack and Sections 4–11 of today's notes.

### 16.3 Required content

Your specification must include:
- At least four stakeholder/user groups.
- At least six discovery findings or questions.
- At least five user stories.
- At least eight functional requirements.
- At least three NFR candidates or explicitly documented NFR open questions.
- At least three business rules.
- At least two acceptance criteria for every story.
- Priority and rationale.
- A traceability matrix.
- Assumptions, dependencies, open questions and version history.

### 16.4 Workspace layout

Create this flat folder structure:

~~~text
customer-support-capstone/
├── requirements_specification.md
├── requirements_checklist.md
├── sample_discovery_inputs.md
└── check_requirements.py
~~~

| File | Action | Purpose |
|---|---|---|
| requirements_specification.md | Create and edit | Main deliverable |
| requirements_checklist.md | Create and edit | Review evidence |
| sample_discovery_inputs.md | Create, then treat as read-only input | Fictional discovery statements |
| check_requirements.py | Create and run; do not edit after copying | Structural checker |

### 16.5 Sample discovery input

Copy this into sample_discovery_inputs.md. These are fictional discovery notes, not confirmed company policy.

~~~text
DISC-01 | Support agent | "I need to know who owns a request."
DISC-02 | Team lead | "I need to see requests by status and assigned agent."
DISC-03 | Customer representative | "I want confirmation that my website request was received."
DISC-04 | Support agent | "I need to find a request using its reference."
DISC-05 | Operations manager | "I need to understand how many requests are still open."
DISC-06 | IT representative | "Access must follow the company's approved sign-in and permissions approach."
OPEN-01 | Business owner | Confirm whether customers may check request status online.
OPEN-02 | Operations manager | Define what makes a request overdue and the response-time target.
OPEN-03 | Data/privacy owner | Confirm customer fields permitted and retention period.
~~~

### 16.6 Ordered tasks

1. Read the Day 40 initiation pack and copy the problem and scope.
2. Add document control with version 0.1 and status Draft.
3. List stakeholders and what each can validate.
4. Record all six discovery inputs with source IDs.
5. Write five or more stories with unique US IDs.
6. Write eight or more functional requirements with unique FR IDs.
7. Add three or more NFR candidates; label unknown targets OPEN.
8. Add three or more candidate business rules.
9. Write two or more Given–When–Then criteria for every story.
10. Prioritize each story with MoSCoW and a reason.
11. Link discovery sources, stories, requirements and criteria in a matrix.
12. Record at least three open questions, owners and evidence needed.
13. Complete the checklist and run the checker.
14. Fix all structural errors. Keep the document at version 0.1 Draft.

### 16.7 Expected results

| Check | Minimum expected |
|---|---:|
| Stakeholder groups | 4 |
| Discovery records | 6 |
| User stories | 5 |
| Functional requirements | 8 |
| NFR candidates/open questions | 3 |
| Business rules | 3 |
| Acceptance criteria | 2 per story |
| Open questions | 3 with owners |
| Version | 0.1 Draft |
| Traceability | Every story links to requirement and criteria |
| Scope | Consistent with Day 40 |

### 16.8 Automated structural checker

Create check_requirements.py with this code. It checks structure and minimum counts only; it cannot judge requirement quality or approval.

~~~python
from pathlib import Path
import re
import sys

folder = Path(__file__).parent
spec_path = folder / "requirements_specification.md"

if not spec_path.exists():
    print("ERROR: requirements_specification.md is missing. Create it beside this checker.")
    sys.exit(1)

text = spec_path.read_text(encoding="utf-8")
checks = []

def record(label, passed, fix):
    checks.append((label, passed, fix))

sections = [
    "Document control",
    "Problem and scope",
    "Stakeholders and sources",
    "Discovery log",
    "User stories",
    "Functional requirements",
    "Non-functional requirements",
    "Business rules",
    "Acceptance criteria",
    "Traceability",
    "Open questions",
    "Version history",
]

for section in sections:
    pattern = r"^#{1,3}\s+.*" + re.escape(section) + r".*$"
    found = re.search(pattern, text, flags=re.IGNORECASE | re.MULTILINE)
    record("Section: " + section, bool(found),
           "Add a heading containing: " + section)

patterns = {
    "US": r"\bUS-\d{2,}\b",
    "FR": r"\bFR-\d{2,}\b",
    "DISC": r"\bDISC-\d{2,}\b",
    "AC": r"\bAC-\d{2,}-\d{2,}\b",
    "BR": r"\bBR-\d{2,}\b",
}
found_ids = {key: re.findall(pattern, text) for key, pattern in patterns.items()}

minimums = {"US": 5, "FR": 8, "DISC": 6, "AC": 10, "BR": 3}
for key, minimum in minimums.items():
    count = len(set(found_ids[key]))
    record("At least {} unique {} IDs".format(minimum, key),
           count >= minimum,
           "Add distinct {} IDs; current count is {}.".format(key, count))

duplicates = []
for key, values in found_ids.items():
    duplicates.extend(sorted({v for v in values if values.count(v) > 1}))

record("No repeated IDs within categories", not duplicates,
       "Review repeated IDs: " + ", ".join(duplicates))
record("Draft status is visible",
       bool(re.search(r"\bDraft\b", text, re.IGNORECASE)),
       "Show status as Draft.")
record("Version 0.1 is visible", "0.1" in text,
       "Add version 0.1 to document control.")
record("At least 3 open question IDs",
       len(set(re.findall(r"\bOPEN-\d{2,}\b", text))) >= 3,
       "Add OPEN-01, OPEN-02 and OPEN-03 with owners.")

failed = [item for item in checks if not item[1]]
print("\nREQUIREMENTS SPECIFICATION CHECK")
print("=" * 40)
for label, passed, fix in checks:
    print(("PASS: " if passed else "FIX: ") + label)
    if not passed:
        print("      " + fix)

print("\nResult: {}/{} checks passed.".format(
    len(checks) - len(failed), len(checks)
))
if failed:
    print("Update the specification and run the checker again.")
    sys.exit(1)

print("Structural checks passed. Complete the human review checklist.")
~~~

**Run the checker**
1. Install Python 3 if needed.
2. Open a terminal in the project folder.
3. Run: python check_requirements.py
4. If that command is unavailable on Windows, try: py check_requirements.py.
5. Read each FIX message, update the specification and run it again.

A structural pass does not prove that requirements are clear, consistent, feasible or approved. Human review remains essential.

### 16.9 Common project errors

| Symptom | Likely cause | Fix |
|---|---|---|
| Main specification missing | Wrong file name or folder | Create exact file beside checker |
| Section check fails | Heading absent or differently worded | Add heading containing the required phrase |
| Story/requirement count too low | IDs absent or malformed | Use distinct IDs such as US-01 and FR-01 |
| Acceptance criteria count too low | Criteria lack unique IDs | Add at least two AC IDs per story |
| Duplicate ID warning | Identifier reused | Assign unique ID and update references |
| Open question count too low | Questions lack OPEN identifiers | Use OPEN-01 through OPEN-03 and assign owners |
| Checker passes but requirement is vague | Structural checks cannot assess meaning | Add conditions and observable outcomes |
| Story has no linked requirement | Traceability incomplete | Update the matrix and references |

### 16.10 Interpretation and submission

The specification helps stakeholders understand needs before design, helps teams estimate work, exposes unresolved policy and data questions, supports test planning and makes change impact visible.

Submit:
- requirements_specification.md
- requirements_checklist.md
- sample_discovery_inputs.md
- check_requirements.py
- Terminal output showing checker results

Ready for review when the minimum counts pass, requirements are clear and testable, sources and traceability exist, unknowns are visible, scope matches Day 40 and the document remains Draft.

**Optional extension:** Add a proposed customer self-service status feature. Identify every affected objective, scope item, story, requirement, data need, criterion and future test. Do not silently add it to the baseline; assess and approve the change.

## 17. Daily quiz

Attempt each question before reading its answer.

**Q1. An agent says, "I need to know who owns a request." What should the BA do first?**

A. Select a database table  
B. Clarify the current process and the ownership information needed  
C. Promise automatic assignment  
D. Mark the request complete

**Answer: B.** Clarify the need and context before proposing a solution.

**Q2. Which is the strongest functional requirement?**

A. The system should be easy  
B. The system should be modern  
C. An authorized agent shall be able to assign an open request to an eligible owner  
D. The system should be fast

**Answer: C.** It states observable behaviour and an authorization condition.

**Q3. In Given–When–Then, what does When describe?**

A. Initial context  
B. Action or event  
C. Expected result  
D. Business owner

**Answer: B.** Given is context, When is action/event and Then is the expected result.

**Q4. Which technique classifies features as Must, Should, Could and Won't have this time?**

A. MoSCoW  
B. Fishbone analysis  
C. Data normalization  
D. Regression testing

**Answer: A.** MoSCoW is a prioritization technique.

**Q5. A response-time target has not been decided. What should the BA do?**

A. Invent a target  
B. Ignore performance  
C. Record an open question, identify an owner and seek an agreed target  
D. Mark it approved

**Answer: C.** Uncertainty must be visible and resolved by an authorized stakeholder.

## 18. Interview preparation

### Question 1: How do you convert a stakeholder request into a clear requirement?

**Answer:** I understand the stakeholder's role, problem and desired outcome. I ask open and probing questions, review documents or process evidence, and separate the raw statement from my interpretation. I then write an atomic requirement, record its source, add acceptance criteria, check feasibility and testability, agree priority and maintain traceability.

**Example:** If an agent wants to find requests faster, I clarify search fields, permissions and no-result behaviour. I can then write a requirement for searching by request reference with testable outcomes.

**Follow-up:** What would you do if two stakeholders give conflicting requirements?

### Question 2: What is the difference between a user story and a functional requirement?

**Answer:** A user story describes a capability from the user's perspective and explains its value. A functional requirement specifies a behaviour the solution must provide. Acceptance criteria define the conditions for accepting the story.

**Example:** Story: As an agent, I want to assign a request so ownership is clear. Requirement: The solution shall allow an authorized agent to assign an open request to an eligible owner. Criterion: When a valid owner is selected and saved, the request displays that owner.

**Follow-up:** Can one user story have several functional requirements?

### Question 3: How do you make requirements testable?

**Answer:** I avoid vague words, identify the actor and conditions, specify observable results, include important negative and exception cases, and agree measurable targets where needed. I link requirements to acceptance criteria and future test cases.

**Example:** Instead of "search should be quick", define supported search fields, expected results and an agreed response-time target.

**Follow-up:** How would you handle a performance target that stakeholders have not agreed?

### Question 4: Why is traceability important?

**Answer:** Traceability shows why a requirement exists, which need it supports, where it is implemented and how it will be tested. It helps identify change impact and reduces the chance of delivering unrequested or untested functionality.

**Example:** If request ownership rules change, the BA can identify affected stories, requirements, criteria and UAT tests.

**Follow-up:** What would you do if a requirement has no identifiable business source?

## 19. Revision sheet

| Concept | Remember |
|---|---|
| Elicitation | Discover needs using interviews, workshops, observation, documents and data |
| Requirement | A capability or condition needed by a stakeholder or solution |
| Functional requirement | What the solution must do |
| Non-functional requirement | Quality or operating condition |
| User story | As a user, I want a capability, so that I get a benefit |
| Acceptance criteria | Observable conditions for acceptance |
| INVEST | Independent, Negotiable, Valuable, Estimable, Small, Testable |
| MoSCoW | Must, Should, Could, Won't this time |
| Business rule | Policy or decision governing behaviour |
| Traceability | Link source, story, requirement, criterion and test |
| Baseline | Approved reference version controlled through change management |

Five questions to ask:
1. Who needs this and why?
2. What source or evidence supports it?
3. Is it clear, atomic and feasible?
4. How will someone verify it?
5. What other requirements or scope items does it affect?

## 20. Day 41 completion checklist

**Concept**
- [ ] I can explain elicitation and select a suitable technique.
- [ ] I can distinguish a stakeholder statement, business need, requirement and solution.
- [ ] I can write functional and non-functional requirement candidates.
- [ ] I can create user stories and acceptance criteria.
- [ ] I can apply INVEST and MoSCoW.
- [ ] I can explain traceability and baselining.

**Practical**
- [ ] I created requirements_specification.md.
- [ ] I recorded stakeholder sources and discovery findings.
- [ ] I wrote at least five stories and eight functional requirements.
- [ ] Every story has acceptance criteria.
- [ ] I recorded business rules, NFR candidates and open questions.
- [ ] I created a traceability matrix.
- [ ] I ran the checker and reviewed the output.
- [ ] I completed the self-review checklist.

**Validation and evidence**
- [ ] IDs are unique and references consistent.
- [ ] Requirements are clear and testable.
- [ ] Unknowns are recorded rather than guessed.
- [ ] Scope matches Day 40.
- [ ] Document is Draft until formally approved.
- [ ] I can explain at least two requirements and their criteria.

Day 41 is complete when the specification and evidence are present, structural checks pass and you can explain the decisions and remaining questions.

## 21. Bridge to Day 42

Day 42 uses the problem, scope and requirements from Days 40–41 to document the current AS-IS process, design the proposed TO-BE process and analyze the gaps.

Your requirements help identify which process steps need to change, which roles perform each activity, where the solution supports the work and which requirements address a validated gap. Do not design the future workflow before understanding the current one.

## 22. References and further learning

- IIBA — Business Analysis resources and BABOK Guide: https://www.iiba.org/standards-and-resources/babok/
- Agile Alliance — User stories: https://www.agilealliance.org/glossary/user-stories/
- Scrum Guides — Official Scrum Guide: https://scrumguides.org/
- Atlassian — User stories and agile requirements: https://www.atlassian.com/agile/project-management/user-stories
- NASA Systems Engineering Handbook — Requirements and verification concepts: https://www.nasa.gov/reference/systems-engineering-handbook/
