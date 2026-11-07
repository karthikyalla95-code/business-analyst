# Day 40: Capstone — Business Problem, Stakeholder Map and Scope

**Phase:** 7 — End-to-End Business Analysis Capstone  
**Estimated time:** 2–3 hours  
**Difficulty:** Intermediate  
**Approved independent mini-project:** Business analysis initiation pack

## 1. What you will build

During Days 40–45, you will complete one end-to-end Business Analyst portfolio project. You will work as a junior Business Analyst on a realistic business case, progressively creating the artifacts needed to understand a problem, define a solution, validate it and present a recommendation.

Today you will establish the foundation:
- Understand the business situation and separate symptoms from the actual problem.
- Write a concise, evidence-based problem statement.
- Define measurable business objectives and success measures.
- Identify stakeholders and understand their interests, influence and decision authority.
- Define project scope, exclusions, assumptions, constraints and dependencies.
- Assemble a Business Analysis Initiation Pack that can guide the next capstone activities.

Do not design screens or write detailed functional requirements today. Those belong to later capstone days.

## 2. Capstone scenario: Customer Support Request Management

A fictional mid-sized online retailer receives customer questions and complaints through email, telephone and a website contact form. Support agents use separate inboxes and spreadsheets to track requests. Managers have difficulty seeing the overall workload and identifying overdue requests.

Customers sometimes contact the company more than once because they do not know whether their request has been received. Agents may have to search multiple places for previous conversations. Management wants to understand the problem and evaluate a more consistent request-management process.

**Important:** This is a fictional scenario for learning. The figures below are illustrative assumptions, not real company data. In a real project, the BA would validate them with evidence and stakeholders.

### Initial discovery information

| Item | Initial information | Evidence status |
|---|---|---|
| Contact channels | Email, telephone and website form | Reported by operations |
| Tracking method | Separate inboxes and spreadsheets | To be confirmed by observation |
| Customer updates | Customers may not receive a consistent acknowledgement | Reported concern |
| Workload visibility | Managers cannot easily see all open requests | Reported concern |
| Duplicate contacts | Some customers contact support again | Needs measurement |
| Target solution | Not yet decided | Open |

The business has not approved a specific software product. Your role is to understand the need before recommending a solution.

## 3. Why a Business Analyst starts with the problem

A common mistake is to jump directly to a proposed system:

"We need a new ticketing platform."

That statement describes a possible solution, not the underlying business problem.

A BA first investigates:
1. What is happening?
2. Who is affected?
3. How does the current process work?
4. What evidence supports the concern?
5. What business impact does it create?
6. What outcome would represent improvement?
7. What is inside and outside the initiative?

A well-defined problem gives stakeholders a shared reason for the project and prevents premature solution decisions.

## 4. Key terms

| Term | Plain-English meaning | Example |
|---|---|---|
| Business problem | A situation preventing the organization from achieving an outcome | Support requests are difficult to track across channels |
| Symptom | A visible sign of a deeper problem | A customer calls again to ask for an update |
| Root cause | An underlying reason a problem occurs | No shared request record or ownership process |
| Business need | The capability or change the organization requires | A consistent way to record and monitor requests |
| Business objective | A result the initiative intends to achieve | Improve visibility of open support work |
| Stakeholder | A person or group affected by or able to influence the work | Support agent, customer, operations manager |
| Scope | The boundaries of the work | Request intake and tracking for the support team |
| Exclusion | Something deliberately not included | Replacing the retailer's payment system |
| Assumption | Something treated as true for planning but not yet confirmed | Support agents can access a shared web application |
| Constraint | A fixed limitation | The first release must use the existing identity provider |
| Dependency | Something the project relies on | The customer database must provide customer identifiers |
| Deliverable | A specific output produced by the project | Approved process model or requirements document |
| Success measure | Evidence used to assess whether an objective was achieved | Percentage of requests with a recorded owner |

## 5. Separate symptoms, causes and solutions

Do not confuse what people observe with why it happens or what should be built.

| Statement | Category | Why |
|---|---|---|
| Customers call again for updates | Symptom | It is an observable behaviour |
| Agents use different spreadsheets | Current-state observation | It describes how work is handled |
| There is no shared request status | Possible cause | It may explain limited visibility |
| Build a new ticketing system | Proposed solution | It is one possible response |
| Reduce avoidable repeat contacts | Desired outcome | It describes a business result |

A possible cause is not a confirmed root cause until it is investigated.

### Practice: classify each statement

1. "Agents cannot see requests handled by another team."
2. "Purchase a new CRM platform."
3. "Reduce the time customers wait for a first response."
4. "Customers send the same question through email and the website."

**Suggested answers**
1. Current-state problem or observation.
2. Proposed solution.
3. Desired outcome.
4. Symptom or observed behaviour.

## 6. Write a problem statement

A useful problem statement is specific enough to guide analysis but does not prescribe the solution.

### Problem statement structure

~~~text
[Business area / affected group] experiences [problem]
in [situation or process], resulting in [business impact].
The current evidence is [known evidence and its limitations].
The organization needs to understand how to [desired outcome]
within [known constraints, if any].
~~~

### Worked example

**Draft problem statement**

"Customer support agents handle requests through separate email inboxes, telephone notes and spreadsheets. This makes it difficult to obtain a consistent view of request ownership and status. Customers may contact the company again when they do not know whether a request has been received. Operations managers need better visibility of workload and request progress. The scale of the issue and its causes must be validated using request data and stakeholder interviews before a solution is selected."

Why this is a useful draft:
- Identifies the business area.
- Describes the current situation.
- Explains possible impacts.
- Separates reported concerns from verified facts.
- Avoids committing to a particular software product.

### Weak versus strong problem statements

| Weak | Better |
|---|---|
| The company needs an app | Support requests are tracked in separate places, limiting shared visibility |
| Customers are unhappy | Customer feedback and repeat-contact data should be examined to understand service issues |
| Agents are slow | Measure handling and waiting time by request type before identifying causes |
| We need automation | Identify which manual steps create delay, errors or avoidable effort |

## 7. Define business objectives

A problem statement explains the issue. Objectives explain the outcomes the business wants.

Objectives should be:
- Relevant to the problem.
- Understandable to stakeholders.
- Measurable where practical.
- Achievable within the agreed scope.
- Time-bound when the business can define a target date.

### Example objective table

| Objective ID | Objective | Possible measure | Baseline | Target |
|---|---|---|---|---|
| OBJ-01 | Improve visibility of open support requests | Percentage of open requests visible in a shared view | To be measured | To be agreed |
| OBJ-02 | Improve request ownership | Percentage of open requests with an assigned owner | To be measured | To be agreed |
| OBJ-03 | Improve customer acknowledgement | Percentage of requests receiving an acknowledgement | To be measured | To be agreed |
| OBJ-04 | Improve management reporting | Availability of an agreed workload report | No shared report confirmed | To be agreed |

Do not invent baselines or targets. The BA should collect current data and obtain agreement from the business owner.

### Output, outcome and benefit

- **Output:** The project creates a shared request register.
- **Outcome:** Agents and managers can see request ownership and status.
- **Benefit:** The organization may reduce avoidable follow-ups and improve service consistency.

A delivered feature is not automatically a realized business benefit. Benefits should be measured after implementation.

## 8. Define scope boundaries

Scope tells the team what the initiative will and will not address.

### 8.1 In-scope examples

For the discovery and first-release planning exercise, the candidate scope may include:
- Recording support requests received through agreed channels.
- Capturing request category, customer reference and received date.
- Assigning an owner or responsible team.
- Tracking request status.
- Recording status history.
- Providing a basic operational view of open requests.
- Defining customer acknowledgement needs.

These are candidate scope items for stakeholder review, not approved requirements.

### 8.2 Out-of-scope examples

- Replacing the retailer's e-commerce platform.
- Changing payment processing.
- Redesigning the entire customer loyalty program.
- Replacing the corporate identity provider.
- Building a full AI chatbot in the first release.
- Rewriting unrelated finance or inventory processes.

An exclusion is useful because it prevents unrelated requests from silently entering the project.

### 8.3 Scope statement template

~~~text
PROJECT:
BUSINESS PROBLEM:
BUSINESS OBJECTIVES:

IN SCOPE:
1.
2.
3.

OUT OF SCOPE:
1.
2.
3.

KEY DELIVERABLES:
1.
2.
3.

ASSUMPTIONS:
1.

CONSTRAINTS:
1.

DEPENDENCIES:
1.

SUCCESS MEASURES:
1.

APPROVAL OWNER:
VERSION:
STATUS:
~~~

## 9. Identify stakeholders

A stakeholder is an individual, group or organization that can affect the initiative, is affected by it, or has an interest in its outcome.

Start broad, then validate the list with the sponsor and process owner.

### Initial stakeholder register

| Stakeholder ID | Stakeholder | Interest / concern | Potential contribution |
|---|---|---|---|
| ST-01 | Executive sponsor | Business value, investment and risk | Funding and strategic decisions |
| ST-02 | Customer Support Manager | Workload, service levels and reporting | Process ownership and priorities |
| ST-03 | Support agents | Daily workflow and usability | Current-state knowledge and feedback |
| ST-04 | Customers | Acknowledgement and request updates | Customer needs and experience |
| ST-05 | Product Owner | Scope, value and prioritization | Product decisions |
| ST-06 | IT / Solution Architect | Architecture and integration | Technical feasibility |
| ST-07 | Security / Privacy representative | Access, data handling and retention | Control and policy input |
| ST-08 | QA / UAT representative | Verifiable outcomes and test coverage | Test scenarios and validation |
| ST-09 | Operations / Service Desk | Support and operational readiness | Handover and support needs |

Customers may be represented through interviews, surveys, feedback records or customer research. Do not assume that one customer speaks for all customers.

## 10. Stakeholder analysis: power and interest

A power-interest matrix helps plan engagement.

| | Low interest | High interest |
|---|---|---|
| High power | Keep satisfied | Manage closely |
| Low power | Monitor appropriately | Keep informed |

### Example placement

| Stakeholder | Illustrative power | Illustrative interest | Engagement approach |
|---|---|---|---|
| Executive sponsor | High | High | Manage closely; decision summaries |
| Support Manager | High | High | Workshops and regular reviews |
| Support agents | Low to medium | High | Interviews, observation and prototypes |
| Security representative | High in control area | Medium | Focused control reviews |
| Customers | Variable | High | Research and feedback channels |
| IT architect | High in technical design | Medium to high | Feasibility and integration discussions |

These are starting assumptions. Confirm actual influence, interest and decision rights in the organization.

## 11. Decision authority and RACI

A stakeholder may provide information without having authority to approve scope.

RACI is a responsibility assignment model:
- **R — Responsible:** performs the work.
- **A — Accountable:** owns the outcome and final decision for that activity.
- **C — Consulted:** provides input.
- **I — Informed:** receives updates.

Example:

| Activity | Sponsor | BA | Support Manager | Architect | QA |
|---|---|---|---|---|---|
| Confirm business objectives | A | R | C | I | I |
| Document current process | I | R | A/C | C | C |
| Draft scope | C | R | A | C | C |
| Assess technical dependencies | I | C | C | A/R | I |
| Review acceptance approach | I | R | C | C | A/R |
| Approve business scope | A | C | C | I | I |

A real RACI must be agreed with the organization. Avoid assigning multiple Accountable roles to one activity unless governance explicitly supports it.

## 12. Eliciting evidence for the initiation pack

A BA should not rely only on opinions. Identify what evidence is available and what needs to be collected.

| Evidence source | What it may reveal | Limitation to consider |
|---|---|---|
| Support inboxes | Request volume and common topics | Multiple inboxes may duplicate records |
| Existing spreadsheets | Current tracking fields and status | Data may be incomplete or inconsistent |
| Customer feedback | Common pain points | Feedback may not represent all customers |
| Agent interviews | Workarounds and exceptions | Individual experience may vary |
| Process observation | Actual steps and handoffs | Observation period may be limited |
| Operational reports | Volume, age and service performance | Metric definitions may differ |

### Initial discovery questions

**For the Support Manager**
- How are requests received and assigned today?
- How do you know which requests are overdue?
- Which reports do you use?
- What decisions are difficult with the current information?
- Which service measures are already defined?

**For support agents**
- Show me how you handle a new request.
- How do you find previous conversations?
- What happens when a request needs another team's help?
- Which information do you enter more than once?
- What exceptions occur most often?

**For customers**
- How do you contact support?
- How do you know the request was received?
- What information do you need while waiting?
- Which communication channels are accessible to you?

**For IT and security**
- Which systems hold customer identifiers?
- What authentication and access controls are required?
- Are there integration, retention or audit constraints?
- Which technical dependencies need early investigation?

## 13. Assumptions, constraints and dependencies

Keep these categories separate.

### Assumptions

Something believed to be true for planning, but not yet confirmed.

Examples:
- Support agents will participate in discovery sessions.
- Existing request records can be sampled for analysis.
- The organization can nominate a business owner.

### Constraints

A fixed boundary that limits available choices.

Examples:
- The first release must comply with the organization's security policies.
- The project has a fixed funding approval window.
- Customer data must remain within approved hosting locations.

### Dependencies

Something the initiative needs from another team, system, supplier or decision.

Examples:
- Access to historical request data.
- Availability of the customer identity service.
- Security review before production release.
- Approval of the service-status definitions.

### Assumption and dependency register

| ID | Type | Description | Validation / impact | Owner | Status |
|---|---|---|---|---|---|
| ASD-01 | Assumption | Historical request data can be sampled | Confirm data access and quality | Support Manager | Open |
| ASD-02 | Assumption | Agents can attend workshops | Confirm shift coverage | BA | Open |
| DEP-01 | Dependency | Customer identifier source is available | Integration discovery required | IT Lead | Open |
| CON-01 | Constraint | Access must follow company security policy | Security review required | Security Lead | Known |

## 14. Risks at initiation

A risk is an uncertain event that could affect objectives. An issue is something that has already happened and needs action.

Examples:

| Risk ID | Risk | Likelihood | Impact | Initial response |
|---|---|---|---|---|
| R-01 | Historical records may be incomplete | Medium | High | Sample and profile records early |
| R-02 | Key agents may not be available for discovery | Medium | Medium | Agree workshop schedule with manager |
| R-03 | Integration capability may be limited | Unknown | High | Arrange technical assessment |
| R-04 | Stakeholders may disagree on first-release scope | Medium | High | Agree decision authority and prioritization |

Risk ratings are illustrative. Use the organization's defined scoring method.

## 15. Build the Business Analysis Initiation Pack

The pack is the independent mini-project for Day 40.

### Deliverables

1. Business problem statement.
2. Business objectives and candidate success measures.
3. Current-state summary and evidence gaps.
4. Scope statement with inclusions and exclusions.
5. Stakeholder register.
6. Power-interest analysis.
7. RACI / decision authority draft.
8. Assumption, constraint and dependency register.
9. Initial risk register.
10. Discovery questions and next-step plan.

### Suggested folder structure

~~~text
Day_40_Initiation_Pack/
|
+-- 01_Problem_Statement.md
+-- 02_Objectives_and_Success_Measures.xlsx
+-- 03_Current_State_and_Evidence_Gaps.md
+-- 04_Project_Scope.md
+-- 05_Stakeholder_Register.xlsx
+-- 06_Power_Interest_Matrix.xlsx
+-- 07_RACI_and_Decision_Rights.xlsx
+-- 08_Assumptions_Constraints_Dependencies.xlsx
+-- 09_Initial_Risk_Register.xlsx
+-- 10_Discovery_Questions_and_Plan.md
+-- 11_Initiation_Pack_Readme.md
~~~

For this learning exercise, Markdown tables or spreadsheet files are both acceptable. Use a consistent ID for each objective, stakeholder, risk and dependency.

### Step-by-step work plan

**Task 1 — Write the problem statement**
- Use the structure in Section 6.
- Identify facts, reported concerns and unknowns separately.
- Do not prescribe a product.

**Task 2 — Define objectives**
- Write at least three objectives.
- Propose one measure for each.
- Mark baseline and target as "To be measured" or "To be agreed" when unknown.

**Task 3 — Draft scope**
- Write at least five candidate in-scope items.
- Write at least four exclusions.
- Identify expected project deliverables.

**Task 4 — Map stakeholders**
- Include at least eight stakeholder groups.
- Document their concerns and contributions.
- Estimate power and interest, then mark estimates for validation.

**Task 5 — Draft RACI**
- Include at least five project activities.
- Assign responsibility and accountability.
- Identify roles that must be consulted or informed.

**Task 6 — Record uncertainty**
- Include at least three assumptions, two constraints and two dependencies.
- Include at least three initial risks.
- Assign an owner and next action to each item.

**Task 7 — Plan discovery**
- Write at least five questions for each of two stakeholder groups.
- Identify evidence to request.
- Suggest the order of interviews or workshops.

**Task 8 — Review the pack**
- Check that objectives connect to the problem.
- Check that scope supports the objectives.
- Check that stakeholder roles cover the decisions and expertise required.
- Check that unknowns are visible.
- Prepare a short executive summary.

## 16. Expected results and self-check

A completed initiation pack should allow a reviewer to answer:

| Review question | Expected evidence |
|---|---|
| What business problem are we investigating? | Clear problem statement |
| What outcomes are desired? | Objectives and proposed measures |
| What do we know and not know? | Evidence summary and gaps |
| What work is included? | In-scope list |
| What is excluded? | Explicit exclusions |
| Who needs to participate? | Stakeholder register |
| Who makes which decisions? | RACI and decision rights |
| What could affect the project? | Risks and dependencies |
| What should happen next? | Discovery plan |

### Quality checklist

- [ ] Problem statement describes a business issue, not a preselected product.
- [ ] Facts are separated from assumptions and unverified claims.
- [ ] Objectives describe outcomes rather than activities.
- [ ] Measures have clear definitions or are marked for agreement.
- [ ] Scope includes both inclusions and exclusions.
- [ ] Stakeholders include users, business owners and technical/control roles.
- [ ] Decision authority is identified or marked as needing confirmation.
- [ ] Assumptions, constraints and dependencies are classified correctly.
- [ ] Risks have an owner and response.
- [ ] Discovery questions are open, neutral and relevant.
- [ ] IDs and terminology are consistent across artifacts.

## 17. If you are stuck

1. Re-read Sections 5–8 for problem, objectives and scope.
2. Hint: Start with what happens today, who experiences it and what evidence would confirm it.
3. Compare your work with the worked problem statement in Section 6.
4. Check whether you have described a solution before understanding the need.
5. Only after making a genuine attempt, use the sample structure below and explain what you changed.

### Short example structure

~~~text
Problem:
Support requests are recorded in separate channels, making shared tracking difficult.

Objective:
Improve visibility of request ownership and status.

Measure:
Percentage of open requests with a recorded owner.

Baseline:
To be measured from a validated sample.

Target:
To be agreed with the business owner.

Scope:
Discovery and first-release planning for request intake, assignment and tracking.

Exclusion:
Replacing the e-commerce payment platform.

Key stakeholders:
Support Manager, agents, customers, sponsor, IT, security and QA.

Next step:
Interview agents and manager, observe the current process and inspect available records.
~~~

This is a structure example, not a completed project submission.

## 18. Knowledge check

**Q1. Why should a BA define the business problem before recommending a tool?**

A. To avoid stakeholder discussions  
B. To understand the need and avoid premature solution selection  
C. To guarantee a project budget  
D. To remove the need for testing

**Answer: B.** The problem should guide the solution, not the other way around.

**Q2. Which statement is a proposed solution?**

A. Agents cannot see requests across inboxes  
B. Customers sometimes contact support again  
C. Implement a new ticketing platform  
D. Managers lack a consolidated workload view

**Answer: C.** It specifies a possible product or approach.

**Q3. What is an assumption?**

A. A confirmed project deliverable  
B. Something treated as true for planning but requiring validation  
C. A fixed legal restriction  
D. A completed task

**Answer: B.** Assumptions must be tracked and validated.

**Q4. What does an exclusion do?**

A. Defines work deliberately outside the project boundary  
B. Assigns a stakeholder  
C. Measures project value  
D. Approves the project

**Answer: A.** Exclusions protect scope clarity.

**Q5. Who is Accountable in RACI?**

A. The person who receives every update  
B. The person who owns the outcome or decision for the activity  
C. Every stakeholder  
D. Only the developer

**Answer: B.** Accountability should be clear for each activity.

**Q6. Which is a dependency?**

A. The team hopes the system is easy to use  
B. The project needs access to the customer identity service  
C. A manager dislikes a colour  
D. A completed report

**Answer: B.** The project relies on another system or team.

**Q7. What should a BA do when the baseline for a KPI is unknown?**

A. Invent a value  
B. Leave the measure undefined forever  
C. Mark it for measurement and identify the data source  
D. Claim the target has been achieved

**Answer: C.** Make the information gap explicit and plan how to close it.

**Q8. What is the best first step when identifying stakeholders?**

A. Invite only senior managers  
B. Identify people affected by, influencing or providing expertise for the change  
C. Start designing screens  
D. Select a software vendor

**Answer: B.** Stakeholder identification should cover all relevant perspectives.

## 19. Business Analyst interview questions

### 1. How do you approach a new business problem?
I first understand the business context and desired outcome. I speak with relevant stakeholders, examine available evidence and document the current situation. I separate symptoms from possible causes, define the problem and objectives, and then establish scope and a plan for further analysis.

### 2. What is the difference between a problem statement and a solution statement?
A problem statement describes the situation, affected people and business impact. A solution statement proposes a way to address it. A BA should understand and validate the problem before recommending a solution.

### 3. How do you identify stakeholders?
I review the process, organizational roles, affected user groups, decision-makers, technical teams and control functions. I validate the list with the sponsor or process owner and record each stakeholder's interest, influence and contribution.

### 4. What is the purpose of a scope statement?
It defines the boundaries of the initiative by documenting what is included, excluded and expected as a deliverable. It helps stakeholders align expectations and manage scope changes.

### 5. Explain assumptions, constraints and dependencies.
An assumption is something treated as true but not yet confirmed. A constraint is a fixed limitation. A dependency is something the project relies on, such as another team, system, decision or supplier.

### 6. How do you prioritize stakeholder engagement?
I consider influence, interest, impact, decision authority and the information each stakeholder can provide. High-influence stakeholders who are highly interested usually need close engagement, while other groups receive an appropriate level of communication.

### 7. How do you make business objectives measurable?
I identify the outcome, define a metric and its calculation, establish a baseline, agree a target and time period, and identify the data source and owner. If the baseline or target is unknown, I record it as an open item rather than inventing a number.

### 8. What would you do if stakeholders immediately requested a specific software product?
I would ask what business problem the product is expected to solve, what outcomes matter and what constraints apply. I would document the request as a proposed solution and evaluate it alongside other options after understanding the requirements.

## 20. Quick revision sheet

| Concept | Remember |
|---|---|
| Problem statement | Describes the business issue and impact |
| Symptom | Visible sign of a problem |
| Root cause | Underlying reason, to be investigated |
| Business objective | Desired business outcome |
| Measure | Evidence used to assess progress or success |
| Scope | Boundaries of the work |
| Exclusion | Work intentionally outside the boundary |
| Stakeholder | Person or group affected by or influencing change |
| Power-interest matrix | Helps plan stakeholder engagement |
| RACI | Responsible, Accountable, Consulted, Informed |
| Assumption | Unconfirmed belief used for planning |
| Constraint | Fixed limitation |
| Dependency | External input or condition the project relies on |
| Risk | Uncertain event that may affect objectives |
| Initiation pack | Foundation artifacts for starting analysis |

## 21. Day 40 completion checklist

- [ ] I can distinguish a symptom, a problem, a possible cause and a solution.
- [ ] I can write a neutral, evidence-based problem statement.
- [ ] I can define business objectives and possible measures.
- [ ] I can distinguish outputs, outcomes and benefits.
- [ ] I can define in-scope and out-of-scope work.
- [ ] I can identify and classify stakeholders.
- [ ] I can use a power-interest matrix.
- [ ] I can draft a RACI and identify decision authority.
- [ ] I can distinguish assumptions, constraints and dependencies.
- [ ] I can identify initial project risks.
- [ ] I have created the Business Analysis Initiation Pack.
- [ ] I can explain the next discovery activities.

## 22. Further learning references

- IIBA — Business Analysis standards and resources: https://www.iiba.org/
- IIBA — BABOK Guide overview: https://www.iiba.org/business-analysis-standards-and-resources/babok/
- PMI — Stakeholder engagement resources: https://www.pmi.org/
- Atlassian — Project scope and project management resources: https://www.atlassian.com/work-management/project-management
- Microsoft Learn — Business and project documentation resources: https://learn.microsoft.com/

Use the organization's actual governance, privacy, security and project approval policies in a live project.

---

**Day 40 outcome:** You have established the business problem, objectives, scope, stakeholder landscape and initial project controls. Day 41 continues the same capstone with elicitation, user stories and functional requirements.
