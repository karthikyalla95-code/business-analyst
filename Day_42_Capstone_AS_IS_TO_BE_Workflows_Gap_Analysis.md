# Day 42: Capstone — AS-IS and TO-BE Workflows and Gap Analysis

**Phase:** 7 — End-to-End Business Analysis Capstone  
**Estimated time:** 2–3 hours  
**Difficulty:** Intermediate  
**Approved mini-project:** Process model and improvement plan  
**Scenario:** Customer Support Request Management

## 1. Learning objectives

By the end of this day, you should be able to:

- Explain why a Business Analyst studies the current process before proposing a new one.
- Define a process boundary, trigger, inputs, outputs, actors and outcome.
- Document an AS-IS workflow using a clear flowchart or BPMN-style model.
- Identify delays, rework, hand-offs, bottlenecks and control gaps.
- Distinguish symptoms from root causes.
- Compare the current process with a proposed TO-BE process.
- Create a gap analysis and practical improvement plan.
- Connect process steps to the requirements from Day 41.
- Record assumptions and validate proposed changes with stakeholders.

**Today's deliverable:** An AS-IS process model, a TO-BE process model, a gap analysis and a prioritized improvement plan. This is the approved independent mini-project for Day 42.

## 2. What is process analysis?

A business process is a set of related activities that people, systems or teams perform to produce an outcome for a customer or the organization.

Example: A customer submits a support request. The business receives it, records it, assigns an owner, investigates it, communicates with the customer and resolves or escalates it.

Process analysis helps answer:
- What actually happens today?
- Who performs each activity?
- What information is needed?
- Where do decisions happen?
- Where are delays, errors or repeated activities?
- What should change, and why?
- How will we know the new process is better?

A process model is a simplified representation of work. It should be accurate enough to support analysis without trying to show every tiny detail.

### 2.1 Process versus procedure versus policy

| Term | Meaning | Example |
|---|---|---|
| Process | Connected activities that create an outcome | Handle a customer support request |
| Procedure | Detailed instructions for performing a task | Steps to record a telephone request |
| Policy | A rule or principle that governs decisions | Customer data must be handled under approved privacy policy |
| Workflow | The sequence and routing of work | New → Assigned → In Progress → Resolved |
| Process model | Visual representation of process flow | Flowchart or BPMN diagram |

A process model is not automatically a procedure, policy or technical design.

## 3. Start with the process boundary

Before drawing, agree what process you are modeling. A vague boundary produces a diagram that is too large or too small.

### 3.1 Define start and end points

For this capstone:

- **Process name:** Customer Support Request Handling.
- **Start trigger:** A customer contacts support through an accepted channel.
- **End outcome:** The request is resolved and the outcome is recorded, or it is routed to an agreed escalation path.
- **Primary customer:** Customer who raised the request.
- **Primary business outcome:** A request is recorded, owned, handled and closed or escalated with a traceable status.

The exact channel coverage and closure rules are assumptions for this learning scenario. Validate them in a real project.

### 3.2 SIPOC overview

SIPOC stands for Suppliers, Inputs, Process, Outputs and Customers. It provides a high-level view before detailed process mapping.

| SIPOC element | Capstone example |
|---|---|
| Suppliers | Customer, website, email service, telephone support |
| Inputs | Customer details, question or complaint, order reference if available |
| Process | Receive, record, assign, investigate, respond, resolve or escalate |
| Outputs | Request reference, recorded request, status, response, resolution |
| Customers | Customer, support agent, team lead, operations manager |

SIPOC is a boundary and context tool. It does not replace a detailed workflow.

### 3.3 Process inventory

| Field | Example |
|---|---|
| Process ID | PROC-01 |
| Process name | Customer Support Request Handling |
| Owner | Support Operations Manager — proposed; confirm |
| Trigger | Customer contacts support |
| Inputs | Customer message and available identifying details |
| Outputs | Recorded request, owner, status and resolution/escalation |
| Systems | Email, spreadsheets and website form — scenario assumptions |
| Main roles | Customer, agent, team lead |
| Measures | Time to acknowledge, time to assign, resolution time, reopened rate |
| Boundary | Contact received through resolution or escalation |

Do not list a person as process owner until the organization confirms ownership.

## 4. Understand the AS-IS process

AS-IS describes how work is currently performed. It should represent observed or validated reality, not the process people wish they had.

### 4.1 Why model AS-IS first?

It helps the BA:
- Understand real tasks, roles, systems and information.
- Discover informal workarounds that may not appear in official procedures.
- Identify duplicate data entry and unnecessary hand-offs.
- Separate actual problems from assumptions.
- Establish a baseline for comparison.
- Avoid automating a broken process without understanding it.

### 4.2 Elicit process information

Use a combination of techniques:

| Technique | What to do | Evidence to collect |
|---|---|---|
| Interview | Ask agents to walk through recent requests | Steps, exceptions, pain points |
| Observation | Watch real work, with permission | Actual sequence, waiting and workarounds |
| Document analysis | Review forms, spreadsheets and instructions | Fields, rules and status definitions |
| Workshop | Ask agents and team leads to map one case together | Shared understanding and disagreements |
| Data analysis | Review request timestamps and categories | Volumes, ageing and repeated work |
| System analysis | Inspect existing forms and inboxes | Available fields and limitations |

Do not assume the written procedure is the same as the work people actually perform. Compare the sources and record discrepancies.

### 4.3 Ask process-focused questions

- What triggers the process?
- What is the first activity after a request arrives?
- Who performs each activity?
- What information is required at each step?
- Which system, form or spreadsheet is used?
- What decisions change the route?
- What happens when information is missing?
- What happens when the request is urgent?
- Where does work wait?
- How does an agent know the task is complete?
- What causes requests to be reopened?
- Which steps are mandatory and which are workarounds?

Ask for a recent example and walk through it from start to finish.

### 4.4 Record the process before drawing

| Step ID | Actor | Activity | Input | Output | System or evidence |
|---|---|---|---|---|---|
| AS-01 | Customer | Sends question or complaint | Message and available details | Incoming request | Website, email or phone |
| AS-02 | Agent | Checks incoming channel | Incoming request | Request understood | Inbox or phone notes |
| AS-03 | Agent | Records request in tracking file | Customer and issue details | Spreadsheet row or note | Spreadsheet |
| AS-04 | Agent | Checks whether enough information exists | Recorded details | Complete or incomplete case | Manual check |
| AS-05 | Agent | Contacts customer if details are missing | Missing information | Updated details or pending case | Email or phone |
| AS-06 | Agent / team lead | Determines who should handle it | Request category and workload | Informal owner decision | Manual coordination |
| AS-07 | Agent | Investigates the issue | Request and available records | Findings | Separate business systems |
| AS-08 | Agent | Responds to customer | Findings | Response | Email or phone |
| AS-09 | Agent | Records outcome in tracking file | Resolution details | Updated record | Spreadsheet |
| AS-10 | Agent | Closes or escalates request | Outcome and remaining work | Closed or escalated case | Tracking file / hand-off |

This is an illustrative candidate workflow derived from the learning scenario. It is not a claim that a real retailer uses these exact steps. Validate each step, role and exception before calling it an approved AS-IS model.

## 5. Flowchart fundamentals

A flowchart shows the sequence of activities and decisions.

### 5.1 Common symbols

| Symbol | Name | Purpose | Example |
|---|---|---|---|
| Oval / rounded terminator | Start or end | Marks process boundary | Request received |
| Rectangle | Process | Activity or task | Record request |
| Diamond | Decision | Branch based on a condition | Details complete? |
| Parallelogram | Input/output | Data entering or leaving | Receive customer details |
| Arrow | Flow line | Shows direction | Next activity |
| Document symbol | Document | Represents a document or record | Request log |
| Connector | Connector | Links distant parts of a diagram | Continue at another page |

Use consistent symbols and label decision branches, such as Yes and No. A decision should normally have clear outgoing paths.

### 5.2 Simple AS-IS flow

~~~text
              (Start)
                 |
                 v
       [Customer contacts support]
                 |
                 v
       [Agent checks the channel]
                 |
                 v
       [Agent records request]
                 |
                 v
        <Details complete?>
           /           \
         No             Yes
         |               |
         v               v
 [Contact customer] [Find an owner]
         |               |
         v               v
 [Wait for details] [Investigate issue]
         |               |
         +------->-------+
                         |
                         v
                [Respond to customer]
                         |
                         v
                [Update tracking file]
                         |
                         v
                 <Resolved now?>
                    /       \
                  No         Yes
                  |           |
                  v           v
              [Escalate] [Close request]
                  |           |
                  v           v
                (End)       (End)
~~~

The diagram is intentionally simplified. A real model may need a loop for follow-up, separate paths for telephone and web requests, a timeout/escalation rule, and more than one resolution outcome.

### 5.3 Flowchart quality checklist

- Does the diagram have a clear start and end?
- Does each activity have an action-oriented label?
- Are decisions written as questions?
- Are all decision branches labelled?
- Do arrows show a logical direction?
- Are loops and exception paths visible?
- Are actors or swimlanes shown when responsibility matters?
- Does the diagram match the written step table?
- Is the scope boundary clear?
- Are assumptions and unvalidated steps identified?

## 6. Swimlane diagrams and responsibility

A swimlane diagram groups activities by role, team or system. It helps reveal hand-offs and unclear ownership.

### 6.1 Example swimlane

~~~text
CUSTOMER
  Submit request ------------------------------ Receive response
          |                                             ^
          v                                             |
SUPPORT AGENT
  Receive -> Record -> Check details -> Investigate -> Respond
               |          |
               |          +-- Missing details -> Ask customer
               v
TEAM LEAD
  Review workload -> Decide/confirm assignment -> Support escalation
               |
               v
TRACKING TOOLS
  Spreadsheet entry -> Manual update -> Status record
~~~

This is a compact responsibility sketch, not a precise BPMN diagram. Use a proper diagramming tool for a final visual model and validate lane ownership.

### 6.2 Hand-offs

A hand-off occurs when work or responsibility moves from one actor or team to another.

Examples:
- Agent asks team lead who should handle a request.
- Agent asks another department for investigation.
- Agent contacts customer for missing details.

Hand-offs can create waiting time, repeated explanation and unclear accountability. Not every hand-off is wasteful: specialist review or approval may be necessary.

### 6.3 RACI as a supporting tool

RACI identifies who is Responsible, Accountable, Consulted and Informed for an activity.

| Activity | Customer | Agent | Team lead | Operations manager |
|---|---|---|---|---|
| Submit request | R | I | I | I |
| Record request | I | R | A* | I |
| Assign owner | I | R* | A* | I |
| Investigate | C | R | A* | I |
| Approve process target | I | C | C | A* |

R = Responsible, A = Accountable, C = Consulted, I = Informed. Asterisks indicate roles that are only proposed for the learning scenario and require confirmation. A real RACI should normally have one clearly accountable owner for each activity, where the organization’s governance supports that convention.

## 7. Analyze the AS-IS process

Once the process is mapped, look for evidence of friction and risk.

### 7.1 Common process issues

| Issue | Meaning | Capstone example |
|---|---|---|
| Waiting | Work is idle before the next step | Agent waits for missing customer details |
| Rework | Work must be repeated or corrected | Request details entered twice |
| Duplicate work | Multiple people perform the same activity | Two agents investigate the same request |
| Excess hand-offs | Work moves between people unnecessarily | Agent asks multiple people to identify an owner |
| Bottleneck | One step limits overall throughput | Only one team lead can allocate work |
| Manual dependency | Process relies on manual memory or updates | Status is updated in a spreadsheet |
| Missing control | Important validation or authorization is absent | Unauthorized user can change ownership |
| Information gap | Required data is missing or unclear | No order reference or contact detail |
| Unclear ownership | No one knows who must act next | Request remains unassigned |
| No feedback loop | Outcome is not communicated or measured | Customer does not know whether request was received |

### 7.2 Distinguish symptom, impact and cause

| Type | Example |
|---|---|
| Symptom | Requests remain unassigned |
| Impact | Investigation starts late and customers wait |
| Possible cause | Assignment depends on manual coordination |
| Evidence needed | Timestamp from receipt to assignment; agent and lead interviews |
| Candidate improvement | Shared queue and explicit assignment rules |

Do not write "the team is careless" as a root cause. Analyze process conditions, information, capacity, tools, policies and skills without blaming individuals.

### 7.3 Process performance measures

Useful measures include:

| Measure | Basic calculation | What it reveals |
|---|---|---|
| Total lead time | End time − start time | Overall elapsed time |
| Processing time | Sum of active work time | Effort spent doing the work |
| Waiting time | Lead time − processing time, if definitions align | Time work is idle |
| First response time | First response timestamp − received timestamp | Delay before first response |
| Assignment time | Assignment timestamp − received timestamp | Delay before ownership |
| Resolution time | Resolution timestamp − received timestamp | End-to-end handling time |
| Reopen rate | Reopened requests ÷ resolved requests × 100 | Resolution quality or unmet expectations |
| First-contact resolution | Requests resolved in first interaction ÷ eligible requests × 100 | Ability to resolve without follow-up |
| Backlog | Count of open requests at a point in time | Work waiting to be completed |

Define the population, time window, start/end events, exclusions and data source before comparing metrics. Otherwise, teams may calculate the same metric differently.

### 7.4 Worked example: lead time and waiting time

A sample request:
- Received at 09:00.
- Active work: 10 minutes recording, 20 minutes investigation, 5 minutes response and closure.
- Waiting for customer information: 3 hours.
- Waiting for assignment: 45 minutes.

Active processing time:

10 + 20 + 5 = 35 minutes.

Total elapsed lead time from 09:00 to 12:40:

3 hours 40 minutes = 220 minutes.

If the categories cover the whole elapsed period and do not overlap, waiting time is:

220 − 35 = 185 minutes.

The example demonstrates why active work time and total elapsed time are different. Confirm timestamps and category definitions before using this calculation in a real report.

## 8. Find root causes

A visible problem may have several underlying causes. Use evidence and structured questioning rather than guessing.

### 8.1 Five Whys

Five Whys repeatedly asks why a problem occurs. Five is a guide, not a required count.

**Problem:** A customer request is not assigned promptly.

1. Why? The agent does not know who should handle it.
2. Why? Assignment depends on asking a team lead.
3. Why? There is no shared view of workload and eligibility.
4. Why? Requests are stored in separate inboxes and spreadsheets.
5. Why? The current process and tools were built around individual channels rather than shared request ownership.

**Candidate root cause:** No consistent shared intake and assignment process.

Validate each answer. If the evidence does not support a why, revise the chain. Avoid stopping at "people forgot" when a process or system condition may explain the behaviour.

### 8.2 Fishbone / Ishikawa analysis

A fishbone diagram organizes possible causes into categories. Common categories include People, Process, Technology, Data, Policy and Environment.

~~~text
                    PEOPLE
             Training / role clarity
                       \
                        \
PROCESS -----------------\ 
Separate steps / hand-offs \ 
                            > Requests assigned late
TECHNOLOGY ----------------/
Separate inboxes / files  /
                         /
DATA -------------------/
Missing fields / duplicates

POLICY: unclear ownership and escalation rules
MEASUREMENT: no shared assignment-time metric
~~~

Possible causes are hypotheses until validated. A fishbone helps generate and organize them; it does not prove which cause is true.

### 8.3 Validate root causes

For every candidate cause, record:
- What evidence would support it?
- What evidence would disprove it?
- Which stakeholder can validate it?
- Which data or observation is needed?
- Is it within project scope?
- Does it explain the problem or merely correlate with it?

Example:

| Candidate cause | Evidence to collect | Validation owner |
|---|---|---|
| Separate tracking tools | Sample records and channel walkthrough | Support team lead |
| Manual assignment | Observe allocation and compare timestamps | Support operations |
| Missing contact details | Review a representative sample of requests | Support agent |
| No shared workload view | Interview leads and inspect reports | Operations manager |

## 9. Design the TO-BE process

TO-BE describes a proposed future process. It should address validated problems and meet agreed business objectives. It is a proposal until stakeholders review and approve it.

### 9.1 Design principles

- Start from the customer and business outcome.
- Remove unnecessary steps, but preserve required controls.
- Capture information once where practical.
- Make ownership visible.
- Define statuses and transitions.
- Make exceptions and escalation paths explicit.
- Use automation only where rules and data are understood.
- Ensure access, privacy and audit needs are considered.
- Make the process measurable.
- Keep the process feasible within approved scope and constraints.

### 9.2 Candidate TO-BE process

~~~text
                         (Start)
                            |
                            v
                [Customer submits request]
                            |
                            v
                 [Capture request centrally]
                            |
                            v
                [Validate mandatory details]
                            |
                     <Details complete?>
                       /           \
                     No             Yes
                     |               |
                     v               v
           [Request missing data] [Create unique reference]
                     |               |
                     v               v
           [Notify customer]   [Place in shared queue]
                     |               |
                     v               v
              [Await response] [Apply assignment rules]
                     |               |
                     +----->---------+
                                     |
                                     v
                           [Owner investigates]
                                     |
                                     v
                           <Can agent resolve?>
                              /          \
                            No            Yes
                            |              |
                            v              v
                    [Escalate with] [Record resolution]
                    [context/details]      |
                            |              |
                            v              |
                    [Specialist review]    |
                            |              |
                            +------>-------+
                                     |
                                     v
                           [Send customer update]
                                     |
                                     v
                           [Update status/history]
                                     |
                                     v
                            [Close request]
                                     |
                                     v
                                   (End)
~~~

This is a target-state proposal for analysis, not a confirmed design. Confirm channel intake, notification triggers, assignment rules, escalation ownership, status transitions and closure policy with stakeholders. The diagram intentionally shows a simplified flow; actual process paths may require more exception handling.

### 9.3 AS-IS versus TO-BE comparison

| Area | AS-IS candidate | TO-BE proposal | Intended benefit |
|---|---|---|---|
| Intake | Multiple inboxes and forms | Central request record | Shared visibility |
| Recording | Manual spreadsheet entry | Consistent request capture | Fewer duplicate records |
| Reference | May be difficult to track | Unique request reference | Easier retrieval |
| Assignment | Manual coordination | Shared queue and agreed rules | Clear ownership |
| Status | Separate manual updates | Defined status lifecycle | Better progress visibility |
| Missing details | Follow-up handled inconsistently | Explicit pending-information path | Clear next action |
| Escalation | Informal hand-off | Defined escalation route | Less ambiguity |
| Reporting | Manual consolidation | Agreed operational measures | Better management visibility |

A TO-BE model must not promise a benefit unless the process design and measurement plan can support it.

## 10. Gap analysis

Gap analysis compares the current state with the desired state to identify what must change.

### 10.1 Gap analysis structure

| Field | Meaning |
|---|---|
| Gap ID | Unique identifier |
| Current state | What happens today |
| Desired state | What should happen |
| Gap | Difference between the two |
| Root cause | Validated reason, or hypothesis clearly labelled |
| Impact | Effect on customer, operations, risk or cost |
| Proposed action | Change that may close the gap |
| Owner | Person accountable for validating or delivering action |
| Priority | Relative urgency or value |
| Measure | Evidence that the gap has reduced |

### 10.2 Worked gap register

| Gap ID | Current state | Desired state | Gap / candidate action | Priority |
|---|---|---|---|---|
| GAP-01 | Requests tracked across separate channels | Shared request record | Define central intake and record creation | Must |
| GAP-02 | Assignment relies on manual coordination | Visible owner and agreed assignment rules | Define queue, eligibility and reassignment rules | Must |
| GAP-03 | Status is updated in separate files | Consistent lifecycle and status visibility | Define statuses, transitions and permissions | Must |
| GAP-04 | Customer confirmation varies by channel | Agreed acknowledgement behaviour | Confirm triggers, content and channel policy | Should |
| GAP-05 | Operational reporting is manually assembled | Agreed workload and ageing measures | Define metric rules and reporting needs | Should |
| GAP-06 | Missing information causes unstructured follow-up | Clear pending-information path | Define mandatory fields, follow-up and escalation | Must |

Priorities are illustrative. Confirm them with the business owner and delivery constraints.

### 10.3 Gap versus solution

A gap describes the difference between current and desired states. A solution is an option to address it.

Example:
- Gap: Team leads cannot see all open requests and their owners in one place.
- Possible solution A: A shared work queue.
- Possible solution B: A consolidated report from existing tools.
- Possible solution C: A new request management application.

Evaluate options against business needs, cost, risk, feasibility and constraints. Do not jump to a preferred product before comparing alternatives.

## 11. Create an improvement plan

An improvement plan converts gaps into controlled actions.

| Action ID | Action | Related gap | Owner role | Dependency | Measure of success |
|---|---|---|---|---|---|
| ACT-01 | Confirm accepted intake channels and minimum fields | GAP-01 | Business owner and support lead | Stakeholder review | Approved intake rules |
| ACT-02 | Define request reference and duplicate handling | GAP-01 | BA and technical representative | Data review | Agreed reference and duplicate rules |
| ACT-03 | Define owner eligibility and reassignment | GAP-02 | Support operations | Role/permission review | Approved assignment rules |
| ACT-04 | Agree status lifecycle and transitions | GAP-03 | Support lead | Workflow review | Approved status model |
| ACT-05 | Confirm acknowledgement policy | GAP-04 | Customer experience owner | Privacy and channel review | Approved acknowledgement rule |
| ACT-06 | Define operational measures and data source | GAP-05 | Operations manager | Timestamp/data availability | Metric definitions approved |
| ACT-07 | Define missing-information and escalation paths | GAP-06 | Support lead | Policy decisions | Approved exception flow |

### 11.1 Prioritize improvement actions

Consider:
- Customer impact.
- Business value.
- Risk reduction.
- Regulatory or policy obligation.
- Delivery effort and cost.
- Dependencies.
- Change readiness.
- Availability of reliable data.

A simple value-versus-effort matrix can support discussion:

| | Lower effort | Higher effort |
|---|---|---|
| Higher value | Quick wins | Strategic improvements |
| Lower value | Optional improvements | Defer or reconsider |

Do not treat this matrix as a substitute for governance or mandatory controls.

### 11.2 Define success measures

For each improvement, define:
- Metric name and business purpose.
- Numerator and denominator if a rate.
- Start and end event for time measures.
- Data source and owner.
- Baseline measurement period.
- Target and target date approved by stakeholders.
- Exclusions and segmentation.
- Reporting frequency.

Example measure definition:

**Assignment time:** Time from request receipt to first valid owner assignment. Report median and 90th percentile for requests received in the reporting period. Exclude test records and document how reopened requests are handled. Confirm the target after measuring a reliable baseline.

Do not invent a numerical improvement target without baseline evidence and stakeholder approval.

## 12. Link process models to Day 41 requirements

A process model and a requirements specification should support each other.

| Process need | Day 41 story / requirement link | Process step | Validation |
|---|---|---|---|
| Record request consistently | US-01 / FR-01 | Capture request centrally | Required fields and successful save |
| Make ownership clear | US-02 / FR-03 | Assign owner | Valid assignment and permission checks |
| Show progress | US-03 / FR-04 | Update status | Allowed transition and displayed status |
| Monitor workload | US-04 / FR-07 | View shared queue | Filters and counts match records |
| Find a request | US-05 / FR-05 | Search by reference | Correct record or no-results behaviour |
| Confirm receipt | US-06 / candidate FR-06 | Acknowledge submission | Approved trigger and confirmation |

These IDs are illustrative links; align them to the actual identifiers in your Day 41 file. If a process step has no supporting requirement, ask whether a requirement is missing or the step is outside solution scope. If a requirement does not appear in any process or outcome, confirm its purpose.

### 12.1 Traceability in both directions

Forward traceability: business objective → requirement → process step → acceptance criterion → test.

Backward traceability: test or process activity → requirement → business need → stakeholder source.

Both directions help detect:
- Requirements with no business reason.
- Process steps with no owner.
- Important needs with no supporting functionality.
- Tests that verify behaviour nobody requested.
- Changes that affect multiple deliverables.

## 13. Validate the process models

A diagram that looks clear is not necessarily correct.

### 13.1 Review participants

Invite the people who understand or approve the process:
- Front-line agent who performs the work.
- Team lead who coordinates assignments and exceptions.
- Process owner or operations manager.
- Customer representative or service-design representative where appropriate.
- IT, security, privacy or compliance representatives when relevant.

### 13.2 Walkthrough method

1. State the process boundary and assumptions.
2. Select a real or realistic case.
3. Follow each activity from start to end.
4. Ask who performs the activity and what information they use.
5. Test decision branches and exception paths.
6. Confirm hand-offs and ownership.
7. Check whether the model matches actual practice.
8. Review proposed TO-BE changes and their impacts.
9. Record disagreements, decisions and actions.
10. Update the model and circulate the revised version.

### 13.3 Scenario-based validation

| Scenario | What the walkthrough should verify |
|---|---|
| Complete website request | Capture, reference, queue, assignment and acknowledgement |
| Missing customer details | Pending path, owner, follow-up and return to work |
| Duplicate request | Identification, linking or duplicate-handling rule |
| Urgent complaint | Priority decision and escalation path |
| Agent unavailable | Reassignment and ownership |
| Specialist investigation needed | Handoff details, status and return path |
| Customer replies after closure | Reopen or new-request rule |
| External system unavailable | Safe fallback, retry and communication |

If the process cannot handle a realistic scenario, the model is incomplete or a business rule is unresolved.

## 14. Model notation and tools

You may create models using:
- diagrams.net (draw.io): https://www.diagrams.net/
- Lucidchart: https://www.lucidchart.com/
- Microsoft Visio: https://www.microsoft.com/microsoft-365/visio/flowchart-software
- Miro: https://miro.com/
- Figma: https://www.figma.com/

### 14.1 Flowchart or BPMN?

| Flowchart | BPMN |
|---|---|
| Easy to learn and communicate | More formal process notation |
| Useful for simple sequences and decisions | Useful for events, tasks, gateways, pools and message flows |
| Flexible symbol conventions | Standardized notation |
| Good for early discussion | Useful when precise collaboration and hand-offs matter |

Use the simplest notation that communicates the process accurately. Do not use BPMN symbols without understanding what they mean.

### 14.2 BPMN essentials

| BPMN element | Typical shape | Meaning |
|---|---|---|
| Start event | Thin circle | Process begins |
| End event | Thick circle | Process ends |
| Task | Rounded rectangle | Work performed |
| Exclusive gateway | Diamond with X or decision marker | Select one route based on a condition |
| Sequence flow | Solid arrow | Order of activities within a process |
| Message flow | Dashed arrow | Message exchanged between participants |
| Pool | Large container | Participant or process boundary |
| Lane | Subdivision of a pool | Role or responsibility grouping |

Important distinction: sequence flow stays within a pool; message flow represents communication between separate participants/pools. Use the official BPMN specification or a trusted guide when building formal BPMN diagrams.

### 14.3 BPMN-style example

~~~text
POOL: Customer
  Start -> Submit support request -> Receive acknowledgement -> End

POOL: Support organization
  Start/message received -> Validate request -> Gateway: complete?
      No -> Request missing information -> Wait for customer response
           -> Validate returned details
      Yes -> Create request -> Assign owner -> Investigate
           -> Gateway: resolved?
                No -> Escalate -> Specialist investigation
                Yes -> Record resolution
           -> Send update -> Close request -> End
~~~

This is a text outline, not a standards-complete BPMN diagram. In a visual BPMN model, show message events and flows between pools correctly.

## 15. Common mistakes and how to fix them

| Mistake | Why it is harmful | Better approach |
|---|---|---|
| Drawing the ideal process as AS-IS | Hides actual workarounds and delays | Observe and validate current work |
| Starting with software features | Makes the model solution-led | Start with trigger, actors, tasks and outcome |
| Missing process boundaries | Diagram becomes endless | Agree start and end events |
| Using vague activity labels | Nobody knows what work occurs | Use verb + object, e.g. "Validate request details" |
| Decision with one outgoing arrow | Branch logic is unclear | Label each outcome and show every route |
| Missing exception paths | Model fails real scenarios | Walk through incomplete, duplicate and urgent cases |
| No role ownership | Handoffs and accountability are hidden | Use swimlanes and validate roles |
| Assuming every hand-off is waste | Necessary specialist controls may disappear | Assess value, risk and delay |
| Treating a possible cause as proven | Improvement may target the wrong issue | Record evidence and validation owner |
| TO-BE adds automation without rules | Exceptions and failures are ignored | Define rules, permissions and fallback first |
| Gap register lists only technology | Business process issues remain | Include people, process, policy, data and measures |
| No baseline metrics | Cannot show whether improvement worked | Define metric and collect current-state data |
| No link to requirements | Models and specification drift apart | Maintain IDs and traceability |
| Treating a draft as approved | Creates false commitment | Mark status and obtain authorized review |

## 16. If you are stuck

Use this sequence:
1. Write the process trigger and end outcome in plain language.
2. List actors and steps before drawing.
3. Hint: use one verb and one object for each activity.
4. Add decision questions and label each outgoing route.
5. Walk through the incomplete-information scenario.
6. Compare the AS-IS and TO-BE tables in Sections 4 and 9.
7. Identify one gap and ask what evidence would validate its cause.
8. Only then complete the gap register and improvement plan.

Do not attempt to make the diagram visually perfect before the process is correct.

## 17. Independent mini-project: Process model and improvement plan

### 17.1 Project objective

Create an evidence-based AS-IS model and a proposed TO-BE model for the Customer Support Request Management scenario. Identify process gaps, analyze likely root causes and produce a prioritized improvement plan connected to Day 41 requirements.

### 17.2 Deliverables

Create the following folder:

~~~text
customer-support-capstone/
├── requirements_specification.md
├── process_inventory.md
├── as_is_process.md
├── to_be_process.md
├── gap_analysis.md
├── improvement_plan.md
└── process_review_checklist.md
~~~

Keep your Day 41 specification. Add the new files alongside it.

| File | Required content |
|---|---|
| process_inventory.md | Boundary, trigger, end, actors, SIPOC and process step table |
| as_is_process.md | Current workflow, flowchart, exceptions and assumptions |
| to_be_process.md | Target workflow, design principles, decisions and expected outcomes |
| gap_analysis.md | Current/desired state, gaps, root-cause hypotheses, impact and evidence |
| improvement_plan.md | Actions, owners, dependencies, priorities and measures |
| process_review_checklist.md | Validation evidence, review comments, decisions and sign-off status |

### 17.3 Step-by-step tasks

**Task 1 — Confirm boundary**
- Use PROC-01.
- Define trigger, start, end, customer and outcome.
- State what is outside scope.
- Mark scenario assumptions.

**Task 2 — Build SIPOC**
- Identify suppliers, inputs, process, outputs and customers.
- Keep it high-level.
- Confirm whether each input is genuinely needed.

**Task 3 — Document AS-IS**
- Include at least eight process steps.
- Identify actor, input, output and system/evidence.
- Add at least two decision points.
- Include missing-information and escalation paths.
- Label unvalidated assumptions.

**Task 4 — Draw AS-IS**
- Use a flowchart or swimlane diagram.
- Add start/end.
- Label decision branches.
- Show the role responsible for each activity.
- Save a clear diagram image or an editable source file if your tool supports it.

**Task 5 — Analyze issues**
- Identify at least five process issues.
- Separate symptom, impact and possible cause.
- Select two issues for Five Whys or fishbone analysis.
- State evidence needed to validate each root-cause hypothesis.

**Task 6 — Design TO-BE**
- Define the future workflow.
- Include central capture, validation, ownership, status, resolution and escalation as relevant to the approved scope.
- Add exception paths.
- Identify policy decisions still needing approval.

**Task 7 — Compare and analyze gaps**
- Record at least five gaps.
- Link each gap to a current-state issue and desired outcome.
- Record proposed action and priority.
- Do not assume the software itself is the only solution.

**Task 8 — Create improvement plan**
- Include at least five actions.
- Give each action an owner role and dependency.
- Add an observable success measure.
- Mark target values as pending where no baseline exists.

**Task 9 — Link to requirements**
- Link process steps and gaps to Day 41 story and requirement IDs.
- Use the real IDs in your own specification.
- Record missing requirements or out-of-scope activities.

**Task 10 — Review**
- Walk through at least four scenarios from Section 13.3.
- Record findings, owners and decisions.
- Keep models in Draft until reviewed and approved.

### 17.4 Sample acceptance checklist

| Check | Minimum expected |
|---|---:|
| Process boundary | Start, trigger, end and outcome defined |
| SIPOC | All five elements completed |
| AS-IS step table | 8 or more steps |
| AS-IS diagram | Start/end and at least 2 labelled decisions |
| Roles | Actor identified for every main activity |
| Exceptions | Missing details and escalation included |
| Process issues | 5 or more |
| Root-cause analysis | 2 issues analyzed with evidence needs |
| TO-BE model | Main flow and exception paths shown |
| Gap register | 5 or more gaps |
| Improvement plan | 5 or more actions with owner and measure |
| Traceability | Links to Day 41 IDs |
| Review | At least 4 scenarios walked through |
| Document status | Draft until approved |

### 17.5 Example review record

| Review ID | Finding | Type | Action / decision | Owner | Status |
|---|---|---|---|---|---|
| REV-01 | Does every channel use the same request reference? | Open question | Confirm reference creation rule | Business owner | Open |
| REV-02 | Who may change the assigned owner? | Policy gap | Confirm role permissions | Support lead | Open |
| REV-03 | What happens when customer does not respond? | Exception gap | Define follow-up and closure policy | Operations manager | Open |
| REV-04 | Is customer status visibility in release scope? | Scope decision | Refer to approved scope/change control | Product owner | Open |

### 17.6 What good work looks like

A reviewer should be able to:
- Follow the AS-IS workflow without guessing.
- See who performs each activity.
- Understand the real problem and supporting evidence.
- Identify what changes in the TO-BE workflow.
- See how every major gap leads to a proposed action.
- Understand dependencies, owners and success measures.
- Trace the proposed process back to approved business needs.
- See what is still an assumption or decision.

**Do not claim a measured improvement unless you have baseline and post-change data.** A proposal can state an expected benefit, but label it as expected rather than achieved.

## 18. Knowledge check

**Q1. What does an AS-IS model represent?**

A. The ideal future process  
B. The validated current process  
C. The database structure  
D. The project schedule

**Answer: B.** AS-IS documents how work currently happens.

**Q2. What is the purpose of a swimlane?**

A. Calculate project cost  
B. Group activities by role or participant  
C. Store customer records  
D. Prioritize user stories

**Answer: B.** Swimlanes make responsibility and hand-offs visible.

**Q3. A process takes four hours elapsed time but only 40 minutes active work. What does this suggest?**

A. There is no waiting  
B. Much of the elapsed time may be waiting or idle time  
C. The process is automatically efficient  
D. Active time must equal elapsed time

**Answer: B.** Investigate where the remaining time is spent and validate timestamps.

**Q4. Which is a gap?**

A. Use a new cloud platform  
B. Current requests have no shared owner view, while the desired state requires visible ownership  
C. Add a blue button  
D. Buy a license

**Answer: B.** It describes the difference between current and desired states.

**Q5. Does a fishbone diagram prove the root cause?**

A. Yes, always  
B. No, it organizes possible causes that need validation  
C. Only if there are six categories  
D. Only if a manager draws it

**Answer: B.** Evidence is needed to validate causes.

**Q6. What should happen when a TO-BE workflow includes an unapproved policy?**

A. Treat it as approved  
B. Hide it from the diagram  
C. Record it as an open decision and identify an owner  
D. Remove all exception paths

**Answer: C.** The model must make unresolved decisions visible.

## 19. Business Analyst interview preparation

### Question 1: What is the difference between AS-IS and TO-BE process models?

**Answer:** AS-IS represents the current validated way of working, including activities, roles, systems, decisions and exceptions. TO-BE represents the proposed future process designed to meet agreed business outcomes. I compare them to identify gaps and define improvement actions.

**Example:** Today requests may be recorded in separate spreadsheets and assigned manually. The proposed process may use a shared queue and explicit ownership rules.

**Follow-up:** How would you make sure the AS-IS model is accurate?

### Question 2: How do you identify bottlenecks in a business process?

**Answer:** I map the steps and hand-offs, observe the work, review timestamps and discuss delays with the people performing the process. I compare lead time with active processing time and look for queues, repeated work and capacity constraints. I validate the cause before recommending a change.

**Example:** If requests wait 45 minutes before assignment but assignment itself takes two minutes, I investigate the queue and assignment decision rather than assuming agents work slowly.

**Follow-up:** Which metrics would you use?

### Question 3: What is gap analysis?

**Answer:** Gap analysis compares the current state with the desired state. I document the difference, business impact, cause or cause hypothesis, proposed action, owner, priority and measure of success.

**Example:** The current process has no shared request ownership view, while the desired process requires a visible owner for every active request. The gap may lead to a shared queue and assignment rules, subject to feasibility review.

**Follow-up:** How do you prioritize gaps?

### Question 4: What is the difference between a symptom and a root cause?

**Answer:** A symptom is the visible problem; a root cause is an underlying condition that contributes to it. I use Five Whys or fishbone analysis to develop hypotheses and validate them with observation, interviews and data.

**Example:** Late assignment is a symptom. Manual coordination and separate tracking tools may be contributing causes, but I would validate those before recommending a change.

**Follow-up:** What if there are several root causes?

### Question 5: How do you validate a process model?

**Answer:** I conduct a walkthrough with the people who perform and own the process. We follow realistic scenarios from trigger to outcome, check responsibilities, data, decisions, exceptions and hand-offs, record disagreements and update the model. I keep it in draft until the authorized stakeholders approve it.

**Follow-up:** What would you do if two teams disagree about the process?

## 20. Quick revision sheet

| Topic | Key reminder |
|---|---|
| Process | Activities that create a business outcome |
| Process boundary | Trigger, start, end and scope |
| SIPOC | Suppliers, Inputs, Process, Outputs, Customers |
| AS-IS | Current validated way of working |
| TO-BE | Proposed future way of working |
| Flowchart | Activities, decisions and sequence |
| Swimlane | Activities grouped by responsibility |
| Hand-off | Work or responsibility moves between actors |
| Bottleneck | Step or resource constraining flow |
| Lead time | Total elapsed time |
| Processing time | Active work time |
| Five Whys | Explore why a problem occurs |
| Fishbone | Organize possible causes |
| Gap analysis | Compare current and desired states |
| Improvement plan | Actions, owners, dependencies and measures |
| Validation | Walk through real scenarios with stakeholders |

**Remember this sequence:**

~~~text
Define boundary
    -> Understand actual work
    -> Document AS-IS
    -> Analyze evidence and root causes
    -> Define desired outcomes
    -> Design TO-BE
    -> Compare and record gaps
    -> Prioritize improvement actions
    -> Validate with stakeholders
~~~

## 21. Day 42 completion checklist

**Understanding**
- [ ] I can explain process, workflow, procedure and policy.
- [ ] I can define a process boundary and create a SIPOC.
- [ ] I can distinguish AS-IS from TO-BE.
- [ ] I can explain flowchart symbols and swimlanes.
- [ ] I can identify waiting, rework, hand-offs and bottlenecks.
- [ ] I can distinguish symptom, impact and root cause.
- [ ] I can explain Five Whys and fishbone analysis.
- [ ] I can create a gap register and improvement plan.

**Practical deliverables**
- [ ] I created process_inventory.md.
- [ ] I documented at least eight AS-IS steps.
- [ ] I created an AS-IS diagram with labelled decisions.
- [ ] I documented exceptions and responsibilities.
- [ ] I identified at least five process issues.
- [ ] I analyzed two issues using root-cause techniques.
- [ ] I created a TO-BE model with exception paths.
- [ ] I documented at least five gaps.
- [ ] I created at least five improvement actions with owners and measures.
- [ ] I linked the models to Day 41 requirements.
- [ ] I completed a scenario-based review.

**Quality and governance**
- [ ] Assumptions are clearly labelled.
- [ ] Root-cause hypotheses have evidence needs.
- [ ] Metrics have definitions and data sources.
- [ ] Proposed benefits are not presented as measured results.
- [ ] Unapproved decisions are recorded as open.
- [ ] Models are marked Draft until authorized approval.

Day 42 is complete when the process inventory, AS-IS and TO-BE models, gap analysis and improvement plan are present, internally consistent and ready for stakeholder review.

## 22. Bridge to Day 43

Day 43 turns the agreed requirements and process improvements into a solution prototype. You will create wireframes, define data requirements and connect interface behaviour to acceptance criteria.

Use the Day 41 requirements and Day 42 TO-BE process as inputs. A prototype should illustrate how users may complete the required tasks; it should not silently introduce new scope or replace stakeholder approval.

## 23. References and further learning

- Object Management Group — Business Process Model and Notation (BPMN): https://www.omg.org/spec/BPMN/
- ASQ — Process analysis and improvement resources: https://asq.org/quality-resources
- IIBA — Business Analysis resources and BABOK Guide: https://www.iiba.org/standards-and-resources/babok/
- diagrams.net — Flowchart and process diagram tool: https://www.diagrams.net/
- Microsoft — Visio flowchart software and process diagramming: https://www.microsoft.com/microsoft-365/visio/flowchart-software
- Atlassian — Process mapping overview: https://www.atlassian.com/work-management/project-management/process-mapping
