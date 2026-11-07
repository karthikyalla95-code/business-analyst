# Day 45: Capstone — Presentation, Recommendation and Final Documentation

**Phase:** 7 — End-to-end Business Analysis Capstone  
**Estimated time:** 2–3 hours  
**Difficulty:** Advanced  
**Prerequisites:** Days 40–44 and the complete Customer Onboarding and Service Improvement System capstone.  
**Approved independent mini-project:** **Complete BA portfolio project**

---

## 1. Why this day matters

A Business Analyst does not finish a project by creating a collection of documents. The analysis must help stakeholders understand a business problem, compare possible solutions, make a decision and agree on what happens next.

Imagine that you have spent several weeks studying a company's customer onboarding process. You have interviewed stakeholders, documented requirements, mapped the current process, proposed an improved process, created a prototype and prepared a UAT plan.

Now you must present the work to a business owner.

The business owner may have only 15 minutes. They do not want to read every requirement or inspect every test case during the meeting. They need clear answers:

- What is the problem?
- Who is affected?
- What evidence supports the problem?
- What is causing the delay or difficulty?
- What solution do you recommend?
- What will the solution change?
- What are the costs, benefits, risks and dependencies?
- How will success be measured?
- What decision do you need today?

Your job is to turn detailed analysis into a clear, honest and useful decision package.

## 2. Learning objectives

By the end of this day, you should be able to:

- Assemble the outputs from Days 40–44 into one organized BA portfolio.
- Write an executive summary for a non-technical stakeholder.
- Explain the business problem, evidence, scope and recommended solution.
- Compare options and justify a recommendation using transparent criteria.
- Present expected benefits, KPIs, assumptions, risks and dependencies.
- Create a concise stakeholder presentation and supporting documentation.
- Distinguish verified results from estimates, assumptions and illustrative examples.
- Prepare a decision log, action plan and handover checklist.
- Present the capstone and answer stakeholder and interview questions.

---

## 3. Words you need

| Term | Plain-English meaning | Example |
|---|---|---|
| Executive summary | Short overview of the problem, recommendation and decision needed | One-page summary for a business owner |
| Business case | Explanation of why a change is worth considering | Benefits, costs, options and risks |
| Recommendation | The option you advise stakeholders to choose | Introduce an application status tracker |
| Evidence | Information that supports a statement | Process records, stakeholder feedback or test results |
| Baseline | Starting measurement used for comparison | Current average onboarding time |
| Target | Desired future measurement | Agreed target onboarding time |
| KPI | Key Performance Indicator: a measure used to monitor an important outcome | Application completion rate |
| Benefit | Positive outcome expected from a change | Fewer incomplete applications |
| Assumption | Something treated as true for planning but not yet confirmed | The existing identity service can be reused |
| Constraint | A limitation that affects the solution | Fixed delivery budget |
| Dependency | Something the project relies on | API access from another team |
| Risk | An uncertain event that could affect the project | External integration may be delayed |
| Trade-off | A compromise between competing needs | Faster release versus broader functionality |
| Roadmap | Ordered view of planned work over time | Discovery, build, pilot and rollout |
| Decision log | Record of important decisions and their owners | Business owner approves the first release scope |
| Handover | Transfer of information and responsibility to another team | BA hands requirements and known issues to delivery |
| Portfolio | A collection of work demonstrating skills and practical ability | Complete BA capstone repository |
| Lessons learned | What the team should repeat or improve next time | Validate integration assumptions earlier |

---

## 4. Reassemble the capstone

The final project is **Customer Onboarding and Service Improvement System**.

The project follows a logical chain:

~~~text
Business problem
      |
      v
Stakeholders and scope
      |
      v
Elicitation and requirements
      |
      v
AS-IS process and analysis
      |
      v
TO-BE process and gap analysis
      |
      v
Wireframes, data and acceptance criteria
      |
      v
UAT plan, test cases and traceability
      |
      v
Recommendation, presentation and handover
~~~

Each stage should support the next. A recommendation should not introduce a feature that has no business justification. A test case should not validate a requirement that was never agreed. A KPI should measure an outcome the business actually cares about.

### 4.1 Capstone deliverable map

| Day | Work completed | What it contributes to the final pack |
|---:|---|---|
| 40 | Business problem, stakeholders and scope | Why the project exists, who is involved and what is included |
| 41 | Elicitation, user stories and functional requirements | What users and the business need |
| 42 | AS-IS, TO-BE and gap analysis | How work happens today and how it could improve |
| 43 | Wireframes, data requirements and acceptance criteria | How the proposed solution may behave and what it must satisfy |
| 44 | UAT plan, test cases and traceability | How business users will validate the solution |
| 45 | Presentation, recommendation and final documentation | How stakeholders decide and how the work is handed over |

### 4.2 Consistency review

Before presenting, check that the artifacts agree.

| Check | Example question |
|---|---|
| Problem to objective | Does the objective address the problem from Day 40? |
| Stakeholder to requirement | Does each important stakeholder need have a documented outcome? |
| Requirement to process | Does the TO-BE process support the agreed requirements? |
| Process to prototype | Do the screens support the proposed workflow? |
| Prototype to acceptance criteria | Can the intended behaviour be checked objectively? |
| Requirement to UAT | Is every in-scope requirement covered by tests or a documented gap? |
| Recommendation to evidence | Does the recommendation follow from the analysis? |
| KPI to business objective | Does each KPI measure a meaningful outcome? |

If an inconsistency is found, correct the source artifact or document the open decision. Do not hide the inconsistency in the presentation.

---

## 5. Build the final project workspace

Use one clear folder for the final capstone. Adapt the names if your earlier daily files use a different structure, but keep a single source of truth for each artifact.

~~~text
customer-onboarding-ba-capstone/
|
|-- README.md
|
|-- 01_initiation/
|   |-- business_problem_statement.md
|   |-- stakeholder_register.csv
|   |-- stakeholder_map.png
|   |-- scope_and_objectives.md
|
|-- 02_requirements/
|   |-- elicitation_summary.md
|   |-- business_requirements.md
|   |-- functional_requirements.csv
|   |-- non_functional_requirements.csv
|   |-- user_stories.csv
|   |-- acceptance_criteria.md
|   |-- assumptions_constraints.md
|
|-- 03_process_analysis/
|   |-- as_is_process.png
|   |-- to_be_process.png
|   |-- gap_analysis.md
|   |-- root_cause_analysis.md
|
|-- 04_solution_design/
|   |-- wireframes/
|   |-- screen_flow.png
|   |-- data_dictionary.csv
|   |-- api_requirements.md
|   |-- prototype_link.md
|
|-- 05_validation/
|   |-- uat_plan.md
|   |-- test_scenarios.csv
|   |-- test_cases.csv
|   |-- traceability_matrix.csv
|   |-- defect_log.csv
|   |-- test_execution.csv
|   |-- uat_summary.md
|   |-- signoff_record.md
|
|-- 06_final_presentation/
|   |-- executive_summary.md
|   |-- recommendation.md
|   |-- presentation_outline.md
|   |-- speaker_notes.md
|   |-- decision_log.csv
|   |-- action_plan.csv
|
|-- 07_evidence/
|   |-- evidence_index.md
|   |-- screenshots/
|
|-- 08_references/
    |-- sources_and_attributions.md
~~~

### 5.1 File organization rules

- Keep editable source artifacts as Markdown, CSV or native tool files.
- Export diagrams and screenshots only when useful; keep the editable original too.
- Use descriptive file names and stable IDs.
- Keep one authoritative version of each artifact.
- Put dates and version information in document metadata.
- Use relative links inside the repository where possible.
- Do not commit credentials, access tokens, private customer records or confidential company information.
- Use synthetic data for portfolio examples.
- Do not add files that are empty merely to make the folder look complete.

### 5.2 Example README opening

~~~markdown
# Customer Onboarding and Service Improvement System

## Project overview

This portfolio project demonstrates an end-to-end Business
Analysis workflow for a fictional customer onboarding process.

## Business problem

[Summarize the validated problem and evidence.]

## Proposed solution

[Summarize the recommended change.]

## BA deliverables

- Business problem and scope
- Stakeholder analysis
- Requirements and user stories
- AS-IS and TO-BE process models
- Gap and root-cause analysis
- Wireframes and data requirements
- UAT plan and test cases
- Traceability and validation summary
- Final recommendation and presentation

## Evidence and limitations

[Link to artifacts. State which outputs are illustrative,
which are based on supplied scenario data and which were
actually validated.]

## Privacy

All portfolio data is synthetic. No real customer data,
credentials or confidential company information is included.
~~~

---

## 6. Write an executive summary

The executive summary is often the first and sometimes the only section a senior stakeholder reads in detail.

It should be understandable without reading the full requirements document.

### 6.1 Recommended structure

1. **Context:** What business process or service is being analyzed?
2. **Problem:** What is not working well?
3. **Evidence:** What supports the problem statement?
4. **Impact:** Who or what is affected?
5. **Recommendation:** What change is proposed?
6. **Expected value:** What improvement should the change create?
7. **Risks and dependencies:** What could affect delivery?
8. **Decision needed:** What must the stakeholder approve or clarify?

### 6.2 Example executive summary

The following is a teaching example. It is not a claim that a real company was measured or that a live solution was deployed.

~~~text
PROJECT
Customer Onboarding and Service Improvement System

CONTEXT
The project reviews a fictional company's customer onboarding
journey, from application start through document submission,
review and status tracking.

PROBLEM
The current process is described in the scenario as difficult
to track. Customers may be uncertain about missing information
and the next action required. Operations staff need a clearer
way to identify and review applications.

EVIDENCE
The analysis uses the supplied scenario, documented stakeholder
needs, the AS-IS process model and the identified process gaps.
No live operational dataset was supplied for this exercise.

RECOMMENDATION
Proceed with a phased design for a customer onboarding portal
that supports application capture, document upload, submission,
status visibility and reviewer requests for additional
information.

EXPECTED VALUE
The proposed workflow is intended to improve process visibility,
reduce avoidable incomplete submissions and make review work
more consistent. These benefits must be measured during a
controlled pilot.

RISKS AND DEPENDENCIES
The design depends on confirmed access rules, document
requirements, integration feasibility, business ownership and
an agreed support process.

DECISION REQUESTED
Approve the proposed scope for detailed solution estimation
and a controlled pilot-planning exercise. Confirm the business
owner and the stakeholders responsible for access, document
policy and integration decisions.
~~~

### 6.3 Keep claims honest

Use these distinctions:

| Type of statement | Example wording |
|---|---|
| Verified fact | “The approved requirements specify a document upload step.” |
| Stakeholder feedback | “Interview participants reported difficulty understanding application status.” |
| Scenario assumption | “The existing identity service may be reusable; this needs technical confirmation.” |
| Expected benefit | “The status tracker is expected to improve visibility.” |
| Measured result | “The pilot reduced average processing time from X to Y.” Only use if measured. |
| Recommendation | “I recommend validating the status tracker in a controlled pilot.” |

Do not present expected benefits as achieved results. Do not invent baseline values, savings, interview counts, test outcomes or stakeholder approvals.

---

## 7. Analyze options before recommending one

A recommendation is stronger when stakeholders can see that alternatives were considered.

### 7.1 Example options

For the onboarding scenario, consider:

- **Option A — Improve the existing manual process:** clarify instructions, standardize checklists and improve communication.
- **Option B — Add a lightweight digital tracking workflow:** provide application status, missing-item notifications and a reviewer queue.
- **Option C — Build a broader integrated onboarding portal:** include application capture, document handling, tracking, reviewer workflow and integrations.

These options are illustrative. A real project must validate feasibility, cost, policy and stakeholder needs.

### 7.2 Compare options using agreed criteria

| Criteria | Option A | Option B | Option C |
|---|---|---|---|
| Initial complexity | Lower | Medium | Higher |
| Process visibility | Limited improvement | Improved tracking | Potentially broad visibility |
| Integration dependency | Low | Depends on design | Potentially high |
| Time to pilot | Potentially shorter | Moderate | Potentially longer |
| Change impact | Mostly procedural | Process and tool change | Broader operational change |
| Future extensibility | Limited | Moderate | Potentially higher |

Do not assign numerical scores until the stakeholders agree on the criteria, scoring scale and evidence.

### 7.3 Weighted decision matrix

A weighted decision matrix helps compare options consistently.

1. Agree on evaluation criteria.
2. Assign a weight to each criterion.
3. Ensure the weights total 100%.
4. Score each option using an agreed scale, for example 1–5.
5. Explain the evidence behind each score.
6. Multiply score by weight.
7. Sum weighted scores.
8. Discuss sensitivity and risks before choosing.

Formula:

\[
\text{Weighted score}=\sum_{i=1}^{n}(\text{criterion score}_i \times \text{criterion weight}_i)
\]

If weights are percentages, either divide by 100 at the end or use decimal weights.

**Illustrative example only**

| Criterion | Weight | A score | B score | C score |
|---|---:|---:|---:|---:|
| Business fit | 35% | 3 | 4 | 5 |
| Delivery feasibility | 25% | 5 | 4 | 2 |
| User experience | 20% | 2 | 4 | 5 |
| Integration simplicity | 20% | 5 | 4 | 2 |

Option A:

\[
(3 \times 0.35)+(5 \times 0.25)+(2 \times 0.20)+(5 \times 0.20)=3.65
\]

Option B:

\[
(4 \times 0.35)+(4 \times 0.25)+(4 \times 0.20)+(4 \times 0.20)=4.00
\]

Option C:

\[
(5 \times 0.35)+(2 \times 0.25)+(5 \times 0.20)+(2 \times 0.20)=3.55
\]

Under these hypothetical weights and scores, Option B ranks highest. This is not proof that it is the correct option. The scoring must be validated, and a critical constraint may override a numerical ranking.

### 7.4 Make the recommendation actionable

A useful recommendation includes:
- Chosen option.
- Reason for selection.
- Expected benefits.
- Main trade-offs.
- Risks and dependencies.
- Conditions to proceed.
- Decision owner.
- Next action and due date.

Example:

> Recommend taking Option B into solution estimation and a controlled pilot, subject to confirmation of access-control rules, document policy, integration feasibility and operational ownership. This option offers a narrower first release than a full portal while addressing the key visibility problem. The pilot should test customer and reviewer journeys before wider rollout.

---

## 8. Define benefits and KPIs

A benefit is an outcome the business wants. A KPI is a measure that helps determine whether the outcome is being achieved.

### 8.1 Build a benefits chain

~~~text
Solution capability
       |
       v
Change in user behaviour
       |
       v
Operational outcome
       |
       v
Business benefit
       |
       v
KPI measurement
~~~

Example:

- Capability: customer can see missing documents.
- Behaviour: customer responds to the specific request.
- Operational outcome: fewer applications remain incomplete due to unclear requests.
- Business benefit: smoother onboarding and less avoidable follow-up.
- KPI: percentage of applications completed without a second document request.

The relationship is a hypothesis until measured.

### 8.2 Example KPI catalogue

| KPI | Definition | Example calculation | Data needed |
|---|---|---|---|
| Application completion rate | Share of started applications that reach submission | Submitted applications ÷ started applications × 100 | Start and submission events |
| First-time document completeness | Share of submissions with all required documents on first submission | Complete first submissions ÷ total submissions × 100 | Document validation records |
| Average onboarding time | Average elapsed time between agreed start and completion events | Total elapsed time ÷ completed applications | Timestamped status history |
| Rework rate | Share of applications requiring correction or resubmission | Applications requiring rework ÷ reviewed applications × 100 | Review outcomes |
| Status enquiry rate | Number of status enquiries per defined application volume | Status enquiries ÷ applications × 100 | Support enquiry records |
| Review turnaround time | Time between submission and first review decision | Total review elapsed time ÷ reviewed applications | Submission and review timestamps |

### 8.3 Define each KPI properly

For every KPI, document:
- Name.
- Business purpose.
- Exact formula.
- Numerator and denominator.
- Start and end events.
- Inclusion and exclusion rules.
- Reporting frequency.
- Data source and owner.
- Baseline.
- Target.
- Known limitations.

For example, “onboarding time” is ambiguous until the business agrees whether it starts when a customer opens a form, saves a draft or submits the first required information.

### 8.4 Baseline, target and actual

| Measure | Meaning |
|---|---|
| Baseline | Current measured performance |
| Target | Desired performance after change |
| Actual | Observed performance during or after rollout |

Use a table like this, but do not invent values:

| KPI | Baseline | Target | Pilot actual | Status |
|---|---|---|---|---|
| Application completion rate | To measure | To agree | Pending | Not measured |
| First-time document completeness | To measure | To agree | Pending | Not measured |
| Average onboarding time | To measure | To agree | Pending | Not measured |
| Status enquiry rate | To measure | To agree | Pending | Not measured |

### 8.5 Avoid misleading KPI comparisons

- Compare equivalent time periods.
- Define whether incomplete or cancelled applications are included.
- Separate average from median where long delays distort the average.
- Check sample size.
- Account for seasonality and process changes.
- Do not claim causation from correlation alone.
- Record missing data and data-quality limitations.

---

## 9. Present risks, assumptions and dependencies

A stakeholder presentation should not hide uncertainty.

### 9.1 Example RAID summary

RAID stands for Risks, Assumptions, Issues and Dependencies.

| Type | Example | Owner role | Next action |
|---|---|---|---|
| Risk | Integration work may take longer than planned | Technical lead | Confirm API feasibility |
| Assumption | Required document rules are stable | Business owner | Validate policy |
| Issue | Current process does not clearly define who owns a pending application | Operations lead | Agree ownership rule |
| Dependency | Access-control model needs security review | Security lead | Review role permissions |

A risk is uncertain; an issue is already happening. An assumption is treated as true pending validation. A dependency is something the work relies on.

### 9.2 Risk register fields

- Risk ID.
- Description and cause.
- Likelihood.
- Impact.
- Overall rating using the agreed method.
- Mitigation.
- Contingency.
- Owner.
- Due date.
- Current status.

### 9.3 Example risk response

Risk:

> The proposed portal may not integrate with the existing customer identity service within the planned delivery window.

Mitigation:
- Confirm API documentation and ownership early.
- Run a technical feasibility check.
- Agree the authentication approach before build commitment.

Contingency:
- Consider an approved interim authentication pattern if security and architecture owners accept it.

Do not choose a workaround that weakens security or bypasses policy.

---

## 10. Create the stakeholder presentation

A presentation is a guided decision conversation, not a copy of the full project folder.

For a 10–15 minute presentation, use approximately 8–10 slides. Adjust the length to the audience and meeting purpose.

### 10.1 Recommended slide structure

| Slide | Title | What to show | Key question answered |
|---:|---|---|---|
| 1 | Project overview | Project name, purpose and presenter role | What is this work? |
| 2 | Business problem | Problem statement, affected users and evidence | Why are we here? |
| 3 | Current process | AS-IS flow and pain points | What happens today? |
| 4 | Findings and requirements | Key causes, stakeholder needs and priority requirements | What needs to change? |
| 5 | Proposed future process | TO-BE flow and gap closure | How should work improve? |
| 6 | Proposed solution | Wireframes, screen flow and key capabilities | What are we proposing? |
| 7 | Validation approach | UAT coverage, traceability and test readiness | How will we know it works? |
| 8 | Benefits and measures | Benefit chain, KPIs, baseline/target status | What value should result? |
| 9 | Risks and delivery approach | Dependencies, phased roadmap and open decisions | What could affect delivery? |
| 10 | Recommendation and decision | Recommended option and explicit decision request | What do we need approved? |

### 10.2 Slide design rules

- One main message per slide.
- Use a descriptive title, not a vague label such as “Analysis”.
- Prefer a diagram or chart when it communicates better than paragraphs.
- Use short phrases rather than full document sections.
- Label assumptions, estimates and actual results.
- Show sources for data and diagrams.
- Keep text readable at normal presentation size.
- Use consistent terms and requirement IDs.
- Do not use decorative charts that have no decision value.
- Keep detailed tables in the appendix.
- Do not use confidential or real customer information.

### 10.3 Example slide title improvement

Weak title:

> Current Process

Stronger title:

> Customers cannot easily identify missing information in the current journey

The stronger title communicates the message rather than merely naming the topic. Only use it if the evidence supports that conclusion.

### 10.4 What belongs in the appendix?

- Full stakeholder register.
- Complete functional and non-functional requirements.
- Detailed user stories and acceptance criteria.
- Full AS-IS and TO-BE diagrams.
- Data dictionary.
- API requirements.
- Full UAT test case repository.
- Traceability matrix.
- Defect log.
- Assumptions and decision register.

The appendix allows detailed review without overcrowding the main presentation.

---

## 11. Prepare speaker notes

Speaker notes help you explain the logic rather than read the slide.

### 11.1 Example speaker script

**Slide 1 — Project overview**

> This project analyzes a fictional customer onboarding process and develops a proposed improvement. I will explain the business problem, stakeholder needs, current and future workflows, proposed solution, validation approach and the decision required.

**Slide 2 — Business problem**

> The scenario identifies difficulty in tracking application progress and understanding missing information. I have separated the stated problem from assumptions that still need validation. The supporting analysis is in the initiation and elicitation documents.

**Slide 3 — Current process**

> This AS-IS model shows the steps from application start through submission and review. The marked handoffs and waiting points are areas to investigate. The model describes the process in the supplied scenario; it should be confirmed with process owners before implementation.

**Slide 4 — Findings and requirements**

> The requirements translate stakeholder needs into specific capabilities. The highest-priority items focus on application capture, document completeness, submission, status visibility and reviewer actions. The full requirement IDs and acceptance criteria are available in the requirements specification.

**Slide 5 — Future process**

> The TO-BE process introduces clearer application tracking and a defined request-and-response path. The gap analysis explains which process changes and system capabilities are needed.

**Slide 6 — Proposed solution**

> These wireframes communicate the intended customer and reviewer interactions. They are a design artifact, not evidence of a deployed application. Detailed behaviour is defined in the acceptance criteria and data requirements.

**Slide 7 — Validation**

> The UAT pack maps requirements to business scenarios and test cases. The current pack defines how validation should be conducted. Unless execution evidence is available, I will not claim that UAT has passed.

**Slide 8 — Benefits**

> The proposed capabilities are expected to improve visibility and reduce avoidable rework. The KPI catalogue defines how the business can measure those outcomes. Baselines and targets must be agreed before a pilot.

**Slide 9 — Risks and delivery**

> Key dependencies include access control, document policy, integration feasibility and operational ownership. A phased approach allows the business to validate the critical journey before broader rollout.

**Slide 10 — Recommendation**

> I recommend progressing the selected scope to estimation and pilot planning, subject to the listed feasibility and governance checks. The decision requested today is approval to proceed with that next stage and assignment of the relevant owners.

Adapt the wording to your actual artifacts and evidence. Do not present this script as a record of meetings or approvals that never occurred.

---

## 12. Plan the next steps and handover

A recommendation should finish with clear actions.

### 12.1 Example phased roadmap

~~~text
PHASE 1: CONFIRM
- Confirm business rules and process ownership
- Validate requirements and open questions
- Confirm security and integration constraints

             |
             v

PHASE 2: DESIGN AND ESTIMATE
- Review solution architecture
- Refine prototype and acceptance criteria
- Estimate effort, cost and delivery dependencies

             |
             v

PHASE 3: BUILD AND VERIFY
- Deliver agreed priority capabilities
- Complete developer and system testing
- Prepare UAT environment and synthetic data

             |
             v

PHASE 4: PILOT
- Select an approved pilot group
- Execute UAT and resolve release-blocking defects
- Monitor agreed KPIs and user feedback

             |
             v

PHASE 5: DECIDE AND IMPROVE
- Review pilot evidence
- Decide whether to expand, revise or stop
- Plan wider rollout and continuous improvement
~~~

This is a proposed sequence, not an approved delivery commitment. The project manager and delivery team must estimate and schedule the work.

### 12.2 Action plan template

| Action ID | Action | Owner role | Due date | Dependency | Status |
|---|---|---|---|---|---|
| ACT-01 | Confirm document policy | Business owner | To agree | Policy stakeholders | Open |
| ACT-02 | Validate role and access model | Security lead | To agree | User-role definition | Open |
| ACT-03 | Assess integration feasibility | Technical lead | To agree | API documentation | Open |
| ACT-04 | Agree KPI baseline and targets | Operations analyst | To agree | Data availability | Open |
| ACT-05 | Confirm pilot scope | Product owner | To agree | Feasibility and estimate | Open |

Use named individuals only after owners have been assigned. Do not invent due dates or claim actions are complete.

### 12.3 Handover checklist

- [ ] Approved business problem and objectives are available.
- [ ] Scope, exclusions and assumptions are documented.
- [ ] Stakeholder and decision-owner list is current.
- [ ] Requirements have unique IDs and agreed priorities.
- [ ] Open questions and unresolved requirements are visible.
- [ ] AS-IS and TO-BE models have been reviewed.
- [ ] Business rules are documented.
- [ ] Wireframes and prototype limitations are explained.
- [ ] Data and integration requirements are documented.
- [ ] Acceptance criteria are testable.
- [ ] UAT plan and test cases are ready for review.
- [ ] Requirement traceability is maintained.
- [ ] Open risks, issues and dependencies have owners.
- [ ] Decisions and change requests are recorded.
- [ ] Evidence is stored in an approved location.
- [ ] Confidential information and credentials are excluded.
- [ ] Next steps and ownership are agreed.

---

## 13. Decision log and change control

A decision log prevents important choices from being lost in meeting notes or chat messages.

### 13.1 Decision log template

| Field | Description |
|---|---|
| Decision ID | Unique identifier, such as DEC-001 |
| Date | Date the decision was made |
| Topic | What decision is required |
| Options considered | Alternatives discussed |
| Decision | Agreed outcome |
| Rationale | Why this option was selected |
| Decision owner | Authorized decision-maker |
| Impacted artifacts | Requirements, process, design, tests or schedule |
| Follow-up action | Work needed after the decision |

### 13.2 Example decision record

**Decision ID:** DEC-001  
**Topic:** Customer visibility of internal review notes  
**Options considered:** Show all notes; show customer-safe status messages only; provide a separate customer explanation field.  
**Decision:** Pending business and security review.  
**Rationale:** Internal notes may contain operational or sensitive information and should not automatically be exposed.  
**Decision owner:** Business owner with security input.  
**Impacted artifacts:** FR-06, access requirements, wireframes and UAT cases.  
**Follow-up:** Confirm policy and update affected artifacts.

This example deliberately remains pending. Never convert a proposed decision into an approved decision without evidence.

### 13.3 When a decision changes a requirement

1. Record the change request.
2. Identify the affected requirement and reason.
3. Analyze process, design, data, testing, cost and schedule impact.
4. Identify impacted stakeholders.
5. Obtain the required approval.
6. Update the requirement version and related artifacts.
7. Update traceability and test coverage.
8. Communicate the change to affected people.

This keeps the project consistent and prevents undocumented scope changes.

---

## 14. Communicate with different audiences

The same analysis should be explained differently depending on who is listening.

| Audience | What they usually need | Useful emphasis |
|---|---|---|
| Executive sponsor | Business outcome and decision | Value, cost, risk and recommendation |
| Operations manager | Practical process impact | Work queues, responsibilities and exceptions |
| Customer support | Customer experience and common problems | Status messages, missing information and escalation |
| Developer | Unambiguous behaviour | Requirements, data, rules and interfaces |
| QA / tester | Verifiable expected behaviour | Acceptance criteria, scenarios and traceability |
| Security / compliance | Control and policy impact | Access, data handling, audit and retention |
| Project manager | Delivery coordination | Scope, dependencies, milestones and risks |

### 14.1 Translate technical language

| Technical wording | Business-friendly explanation |
|---|---|
| API integration | The portal exchanges information with another system through an agreed interface |
| Authentication | The system checks who the user is |
| Authorization | The system checks what the user is allowed to do |
| Data validation | The system checks whether entered information follows the required rules |
| Audit log | A record of important actions and when they happened |
| API timeout | The connected service did not respond within the allowed time |
| Regression test | A check that an existing feature still works after a change |

Do not remove technical detail when the audience needs it. Explain the business consequence first, then provide the technical detail.

---

## 15. Common presentation and documentation mistakes

| Mistake | Why it hurts | Better approach |
|---|---|---|
| Presenting every requirement on a slide | Audience loses the main message | Show key requirements and link the full specification |
| Making unsupported benefit claims | Stakeholders may make decisions on false confidence | Label expected, estimated and measured outcomes |
| Showing a prototype as a completed product | Creates incorrect expectations | Label it as a prototype and explain limitations |
| Hiding unresolved questions | Creates delivery surprises | Show open decisions and owners |
| Recommending a solution without alternatives | Looks biased or incomplete | Compare feasible options transparently |
| Using a KPI without a formula | Different teams may calculate it differently | Define events, numerator and denominator |
| Reporting a pass rate without a denominator | Misleads the audience | State planned, executed, passed, failed and blocked counts |
| Overloading slides with text | Audience reads instead of listening | Use concise messages and supporting visuals |
| Using unexplained acronyms | Excludes non-technical stakeholders | Define terms on first use |
| Ending without a decision request | Meeting produces no clear next step | State the decision, owner and required date |
| Treating a recommendation as approval | Misrepresents authority | Record the authorized decision separately |
| Including confidential data in a portfolio | Creates privacy and security risk | Use synthetic examples and sanitized evidence |

---

## 16. Independent mini-project: Complete BA portfolio project

**Approved title:** Complete BA portfolio project

### 16.1 Objective

Assemble and present the complete Customer Onboarding and Service Improvement System as a professional entry-level Business Analyst portfolio project.

The portfolio must show the reasoning from business problem to recommendation. It should be understandable to a recruiter, BA interviewer, product owner or business stakeholder who has not followed the learning pathway.

### 16.2 Required deliverables

Create or complete the following:

1. **Project README** — overview, context, navigation, setup and limitations.
2. **Executive summary** — problem, evidence, recommendation and decision needed.
3. **Initiation pack** — business problem, objectives, stakeholders and scope.
4. **Requirements pack** — business and functional requirements, user stories and acceptance criteria.
5. **Process analysis pack** — AS-IS, TO-BE and gap analysis.
6. **Solution design pack** — wireframes, screen flow, data requirements and API requirements.
7. **Validation pack** — UAT plan, scenarios, test cases, traceability and defect log.
8. **Recommendation document** — options, decision criteria, benefits, KPIs, risks and next steps.
9. **Presentation outline** — 8–10 slides with a clear decision request.
10. **Speaker notes** — concise explanation for each slide.
11. **Decision and action logs** — pending items clearly identified.
12. **Evidence index** — links to the supporting artifacts.

### 16.3 Task A — Audit your artifacts

For every deliverable:
- Confirm that the file exists.
- Confirm that its title and IDs are consistent.
- Confirm that it links to the correct upstream artifact.
- Identify assumptions and unresolved questions.
- Remove duplicate or outdated copies.
- Check spelling, readability and access permissions.

Create an audit table:

| Artifact | Exists? | Reviewed? | Issue found | Action |
|---|---|---|---|---|
| Business problem | Yes/No | Yes/No | Record issue | Correct / accept |
| Requirements | Yes/No | Yes/No | Record issue | Correct / accept |
| Process models | Yes/No | Yes/No | Record issue | Correct / accept |
| Prototype | Yes/No | Yes/No | Record issue | Correct / accept |
| UAT pack | Yes/No | Yes/No | Record issue | Correct / accept |
| Recommendation | Yes/No | Yes/No | Record issue | Correct / accept |

### 16.4 Task B — Write the executive summary

Use the structure in Section 6. Keep it to approximately one page. It must:
- State the problem.
- Identify the evidence available.
- Summarize the recommended option.
- State expected benefits without claiming they have already happened.
- Highlight material risks and dependencies.
- End with a specific decision request.

### 16.5 Task C — Create the recommendation

Include:
- Options considered.
- Evaluation criteria and their agreed weights, if using a weighted matrix.
- Evidence and assumptions behind scores.
- Recommended option.
- Trade-offs and limitations.
- Conditions before proceeding.
- Decision owner and next step.

If no reliable cost or performance data exists, say so. Do not manufacture a return-on-investment figure.

### 16.6 Task D — Create the KPI catalogue

Document at least five relevant KPIs. For each one include:
- Definition.
- Formula.
- Data source.
- Measurement frequency.
- Owner.
- Baseline status.
- Target status.
- Limitation.

At least one KPI should measure customer experience or process quality, not only speed.

### 16.7 Task E — Create the presentation

Prepare 8–10 slides using the structure in Section 10.

Check:
- The first two slides establish context and problem.
- The middle slides show analysis and proposed solution.
- Validation and risks are visible.
- The final slide states the recommendation and decision needed.
- Detailed supporting artifacts are linked in an appendix or README.

### 16.8 Task F — Prepare speaker notes

Write approximately 2–5 sentences per slide. Explain:
- What the audience is looking at.
- Why it matters.
- What evidence supports it.
- What question or decision follows.

Practise presenting without reading every word.

### 16.9 Task G — Final handover

Prepare:
- Handover checklist.
- Decision log.
- Action plan.
- Open questions list.
- Risks and dependencies.
- Evidence index.
- Known limitations.

Clearly label each item as complete, pending, assumed or not in scope.

### 16.10 Task H — Final quality review

Ask a person unfamiliar with the project to review the README and presentation if possible. If no reviewer is available, perform the review yourself after a short break.

Ask:
1. Can the reader understand the problem in two minutes?
2. Can the reader identify who is affected?
3. Is the recommendation supported by the analysis?
4. Can the reader trace important requirements to tests?
5. Are the expected benefits measurable?
6. Are risks and unknowns visible?
7. Is the requested decision clear?
8. Can another person find and understand every supporting artifact?

### 16.11 Expected final outcome

A complete portfolio should let another person follow this chain:

~~~text
Problem and evidence
       |
       v
Business objectives and scope
       |
       v
Stakeholder needs and requirements
       |
       v
Process analysis and improvement
       |
       v
Proposed solution and acceptance criteria
       |
       v
UAT and traceability
       |
       v
Recommendation and decision request
       |
       v
Actions, ownership and measurement
~~~

### 16.12 Final submission checklist

- [ ] README explains the project and links to all sections.
- [ ] Executive summary is concise and evidence-based.
- [ ] Business problem and objectives are clear.
- [ ] Stakeholders and scope are documented.
- [ ] Requirements have unique IDs.
- [ ] User stories and acceptance criteria are understandable.
- [ ] AS-IS and TO-BE models are readable.
- [ ] Gap analysis connects the current and future processes.
- [ ] Wireframes and prototype are labelled correctly.
- [ ] Data and integration requirements are documented.
- [ ] UAT plan and test cases are ready for review.
- [ ] Traceability links requirements to validation.
- [ ] UAT execution claims match actual evidence.
- [ ] Options and recommendation are explained.
- [ ] At least five KPIs are defined.
- [ ] Risks, assumptions and dependencies are visible.
- [ ] Presentation contains 8–10 focused slides.
- [ ] Speaker notes are prepared.
- [ ] Decision request and next steps are explicit.
- [ ] Handover checklist and action plan are complete.
- [ ] Portfolio uses synthetic data and contains no secrets.
- [ ] All diagrams and images have captions and appropriate attribution.
- [ ] Known limitations are stated honestly.

### 16.13 Stuck ladder

1. Re-read the capstone deliverable map in Section 4.2.
2. Use the executive summary structure in Section 6.1.
3. Use the option comparison in Section 7.2.
4. Use the KPI catalogue in Section 8.2.
5. Copy the 10-slide structure in Section 10.1.
6. Use the speaker notes in Section 11 as a guide, not as a claim about your own results.
7. Review the handover checklist in Section 12.3.
8. If an artifact is missing, return to the corresponding day and complete it before claiming the capstone is complete.

### 16.14 Self-review rubric

| Dimension | Marks |
|---|---:|
| Business problem, objectives and scope | 10 |
| Stakeholder and requirements quality | 15 |
| Process analysis and gap reasoning | 15 |
| Solution design and acceptance criteria | 10 |
| UAT, testing and traceability | 15 |
| Recommendation and option evaluation | 10 |
| KPIs, benefits, risks and assumptions | 10 |
| Presentation and communication | 10 |
| Organization, evidence and privacy | 5 |
| **Total** | **100** |

Suggested interpretation:
- **90–100:** coherent, evidence-based portfolio ready for detailed review.
- **75–89:** strong portfolio; resolve remaining consistency or communication gaps.
- **60–74:** core artifacts exist; strengthen traceability, evidence and recommendation.
- **Below 60:** revisit missing capstone stages before presenting.

---

## 17. Final capstone presentation practice

Deliver a 10-minute presentation using this timing guide:

| Time | Content |
|---|---|
| 0:00–1:00 | Context and business problem |
| 1:00–2:00 | Stakeholders and scope |
| 2:00–3:30 | AS-IS process and findings |
| 3:30–5:00 | TO-BE process and requirements |
| 5:00–6:00 | Prototype and solution design |
| 6:00–7:00 | UAT and validation approach |
| 7:00–8:00 | Benefits, KPIs and risks |
| 8:00–9:00 | Options and recommendation |
| 9:00–10:00 | Decision request and next steps |

### 17.1 Practice delivery checklist

- [ ] Introduce the project in one sentence.
- [ ] Explain the business problem without jargon.
- [ ] Use one clear process diagram.
- [ ] Explain the most important requirement.
- [ ] Show one prototype journey.
- [ ] Explain how the solution will be validated.
- [ ] State what is known and what remains uncertain.
- [ ] Give a recommendation and explain why.
- [ ] Ask for a specific decision.
- [ ] Finish within the agreed time.

### 17.2 Handling stakeholder questions

Use this four-step method:

1. **Listen:** Let the stakeholder finish the question.
2. **Clarify:** Ask what decision or concern is behind it if needed.
3. **Answer with evidence:** Refer to the requirement, process, data or test artifact.
4. **Record unresolved items:** Assign an owner and next action instead of guessing.

Example:

Stakeholder: “Can this system reduce onboarding time by 30%?”

Good response:

> The proposed workflow is intended to reduce avoidable delays, but we do not yet have a measured baseline or pilot result to support a 30% claim. I recommend measuring current onboarding time, agreeing a target with operations and evaluating the result during the pilot.

This is more credible than promising an unsupported improvement.

---

## 18. Knowledge check

Attempt each question before checking the answers.

**Q1.** What is the main purpose of an executive summary?

A. Reproduce every requirement  
B. Help a decision-maker understand the problem, recommendation and decision needed  
C. Replace all project documentation  
D. List only technical implementation details

**Q2.** Which statement is an expected benefit rather than a measured result?

A. “The pilot reduced processing time by 12%, based on recorded data.”  
B. “The proposed status tracker is expected to improve customer visibility.”  
C. “The report contains 15 test cases.”  
D. “The business owner approved the scope on the recorded date.”

**Q3.** What should a weighted decision matrix contain?

A. Scores with no explanation  
B. Criteria, agreed weights, option scores and rationale  
C. Only the preferred option  
D. Only estimated costs

**Q4.** Which item belongs in a handover pack?

A. Unrecorded assumptions  
B. Credentials in plain text  
C. Open risks, owners, requirements and validation artifacts  
D. Unsupported benefit claims

**Q5.** What is the best way to respond when a stakeholder asks for a benefit that has not been measured?

A. Promise the requested number  
B. Avoid answering  
C. Explain the current evidence gap and propose a measurement approach  
D. Present an assumption as a fact

### Answer key and explanations

1. **B** — An executive summary gives a decision-maker the essential context and requested action.
2. **B** — “Expected to” clearly labels a proposed benefit that still needs measurement.
3. **B** — A transparent matrix documents the criteria, weights, scores and reasons.
4. **C** — Handover should make requirements, risks, ownership and validation information available.
5. **C** — A BA should be honest about evidence and propose a practical way to measure the outcome.

---

## 19. Business Analyst interview preparation

### Question 1: How would you present a complex BA project to senior stakeholders?

**Answer:** I would start with the business problem, its impact and the evidence. Then I would summarize the stakeholder needs, current process, key gaps and proposed solution. I would explain expected benefits, KPIs, risks and alternatives, and finish with a specific decision request. Detailed requirements and test cases would remain available in the supporting documents.

**Example:** For an onboarding improvement project, I would show the current customer journey, explain where status visibility is weak, demonstrate the proposed tracking flow and describe how a pilot would validate it.

**Follow-up:** What if stakeholders disagree with your recommendation?

**Answer:** I would understand their concerns, revisit the decision criteria and evidence, compare the alternatives and document the decision and its impact. The BA should support a transparent decision, not defend an option regardless of evidence.

### Question 2: How do you know whether a business recommendation is justified?

**Answer:** I check that it addresses the agreed business problem, is supported by stakeholder needs and process analysis, is feasible within known constraints and has measurable expected outcomes. I also compare alternatives and make assumptions, risks and dependencies visible.

**Follow-up:** What if there is not enough data?

**Answer:** I state the limitation, identify the data needed and recommend a discovery activity, baseline measurement or controlled pilot before making a strong performance claim.

### Question 3: What should a BA portfolio project demonstrate?

**Answer:** It should demonstrate the end-to-end reasoning process: problem definition, stakeholder analysis, elicitation, requirements, process modeling, gap analysis, solution design, acceptance criteria, UAT planning, traceability and stakeholder communication. It should also explain the learner's own contribution, assumptions and limitations.

**Follow-up:** Is a prototype alone enough?

**Answer:** No. A prototype shows a possible design, but a BA portfolio should also show why the solution is needed, what requirements it addresses and how it would be validated.

### Question 4: How do you measure whether a proposed process improvement worked?

**Answer:** I define business outcomes and KPIs before implementation, establish a baseline, agree targets and data definitions, then compare results after a controlled rollout. I check data quality and other factors that may influence the result before attributing the change to the solution.

**Follow-up:** Why might average processing time be misleading?

**Answer:** A small number of very delayed cases can distort the average. I may also examine the median, distribution, sample size and the agreed start and end events.

### Question 5: What would you do if a project stakeholder requests a feature outside the approved scope?

**Answer:** I would record the request, clarify the business reason, analyze its impact on requirements, process, design, cost, schedule, risk and testing, then route it through the agreed change-control process. I would update affected artifacts only after the required decision.

**Follow-up:** Should the BA reject every out-of-scope request?

**Answer:** No. The BA should assess and communicate the impact. The authorized stakeholders decide whether to add, defer or reject the change.

---

## 20. Quick revision sheet

| Topic | Key point |
|---|---|
| Executive summary | Problem, evidence, recommendation and decision |
| Business case | Why a change is worth considering |
| Options analysis | Compare alternatives using agreed criteria |
| Weighted matrix | Criteria score multiplied by criterion weight |
| Benefit | Positive business outcome |
| KPI | Measure of an important outcome |
| Baseline | Current measured position |
| Target | Desired future position |
| Actual | Observed result |
| Assumption | Unconfirmed condition treated as true for planning |
| Constraint | Known limitation |
| Dependency | Something the work relies on |
| Risk | Uncertain event that may affect outcomes |
| Decision log | Record of decisions and authority |
| Action plan | Work, owner, due date and status |
| Handover | Transfer of knowledge and responsibility |
| Portfolio | Organized evidence of practical skills |
| Recommendation | Evidence-based advice, not automatic approval |

**Before presenting, ask yourself:**

1. Can I explain the business problem in one minute?
2. Can I show where the evidence came from?
3. Can I explain how the proposed solution addresses the requirements?
4. Can I show how the solution will be validated?
5. Can I distinguish expected benefits from measured results?
6. Can I explain risks and unresolved decisions?
7. Can I state exactly what I want stakeholders to decide?

---

## 21. References and further learning

- IIBA — International Institute of Business Analysis: https://www.iiba.org/
- IIBA BABOK Guide overview: https://www.iiba.org/standards-and-resources/babok/
- Atlassian — Project management and stakeholder communication resources: https://www.atlassian.com/
- Microsoft Learn — PowerPoint training and presentation guidance: https://support.microsoft.com/powerpoint
- GOV.UK Service Manual — measuring success and performance: https://www.gov.uk/service-manual/measuring-success
- Project Management Institute: https://www.pmi.org/

Use the organization's actual presentation, approval, privacy and change-control standards when working on a real project.

---

## 22. Day 45 completion checklist

- [ ] I reviewed and connected the outputs from Days 40–44.
- [ ] I checked consistency between problem, scope, requirements, process, design and tests.
- [ ] I organized the complete BA portfolio.
- [ ] I wrote an evidence-based executive summary.
- [ ] I compared solution options.
- [ ] I documented a clear recommendation and its trade-offs.
- [ ] I defined at least five relevant KPIs.
- [ ] I separated baseline, target and actual values.
- [ ] I documented risks, assumptions, issues and dependencies.
- [ ] I created an 8–10 slide stakeholder presentation.
- [ ] I prepared speaker notes and practised the presentation.
- [ ] I created a decision log and action plan.
- [ ] I completed the handover checklist.
- [ ] I stated limitations and unresolved questions.
- [ ] I used synthetic data and removed confidential information.
- [ ] I completed the knowledge check.
- [ ] I practised at least two interview questions.
- [ ] I can explain the complete project without reading every document.

**The pathway's final learning day is complete when you can explain the analysis, show the supporting artifacts, defend the recommendation with evidence and identify what still needs stakeholder approval or real-world validation.**

---

## 23. What you have completed across the 45-day pathway

The pathway has taken you through seven stages:

| Phase | Days | Capability developed |
|---|---:|---|
| 1. Business analysis foundations | 1–5 | Understand the BA role, business problems, stakeholders and scope |
| 2. Requirements engineering | 6–12 | Elicit, analyze, prioritize, document and trace requirements |
| 3. Process modeling and documentation | 13–19 | Discover and model processes, analyze gaps and document specifications |
| 4. Data analysis for business decisions | 20–26 | Define KPIs, work with spreadsheets and SQL, interpret statistics and trends |
| 5. Agile, Scrum and project management | 27–33 | Work with backlogs, sprints, Kanban, Jira, risks and changes |
| 6. Tools, testing and solution validation | 34–39 | Create wireframes, understand APIs, plan UAT and review requirements |
| 7. End-to-end BA capstone | 40–45 | Complete and present an end-to-end business analysis project |

### Your final portfolio should contain

- Business problem statement and scope.
- Stakeholder register and stakeholder map.
- Business and functional requirements.
- User stories and acceptance criteria.
- AS-IS and TO-BE process models.
- Gap and root-cause analysis.
- Wireframes and prototype.
- Data dictionary and API requirements.
- UAT plan, scenarios and test cases.
- Requirement traceability matrix.
- Defect log and validation summary.
- Executive summary and recommendation.
- KPI catalogue, risks and action plan.
- Final stakeholder presentation and README.

### Important career-readiness reminder

Completing a learning pathway does not automatically make someone an experienced Business Analyst. It gives you a structured foundation and a portfolio project to discuss. Continue practising with realistic datasets, mock stakeholder conversations, requirement reviews, process models, SQL questions and presentation exercises.

When describing this project in an interview:
- Call it an academic, self-directed or portfolio capstone, as appropriate.
- Explain exactly which artifacts you created.
- Do not claim a real company implemented the solution unless that happened.
- Do not claim measured business savings or successful production deployment without evidence.
- Be ready to explain one difficult requirement, one process gap, one design decision and one UAT test in detail.

**You have reached the end of the 45-day Business Analyst Career Pathway. The next step is to keep improving the portfolio and practise explaining your work clearly and honestly.**
