# Day 37: Software Testing Fundamentals and the Business Analyst's Role in UAT

## Learning outcomes

By the end of this lesson, you should be able to:

- Explain why software testing is needed and where it fits in the delivery lifecycle.
- Distinguish verification from validation and quality assurance from quality control.
- Understand common testing levels, types and techniques.
- Explain the purpose of User Acceptance Testing (UAT).
- Describe the Business Analyst's responsibilities before, during and after UAT.
- Convert business requirements into testable UAT scenarios.
- Prepare a practical UAT Test Scenario Design pack for a customer onboarding process.

## 1. What is software testing?

Software testing is the process of evaluating a software product or component to find defects and determine whether it behaves as expected.

A software feature can look correct on screen but still fail because:
- It saves incorrect data.
- It allows an unauthorized user to access information.
- It calculates a value incorrectly.
- It fails when required information is missing.
- It works in one browser but not another.
- It does not follow the approved business process.

Testing helps the team discover these problems before the solution is released to users.

### 1.1 Simple example: customer registration

A company launches an online customer registration form.

Expected business behaviour:
1. A customer enters a valid name, email and mobile number.
2. The system validates the information.
3. The customer submits the form.
4. The system creates the customer profile.
5. A confirmation message is displayed.

Possible defects:
- The form accepts an invalid email address.
- The Submit button does nothing.
- The same customer is registered twice.
- The system stores a mobile number in the wrong field.
- The confirmation message appears even though saving failed.
- A user can view another customer's profile.

Testing checks these behaviours against requirements and expected outcomes.

### 1.2 Why testing matters to a business

Testing is not only about finding code errors. It protects business outcomes.

| Business concern | How testing helps |
|---|---|
| Customer experience | Checks that users can complete important tasks |
| Revenue | Finds issues that may block purchases or payments |
| Data quality | Checks accuracy, completeness and consistency |
| Compliance | Checks approved controls and required evidence |
| Security | Helps reveal access-control and data-exposure problems |
| Operations | Checks that processes work reliably |
| Reputation | Reduces the chance of visible failures after release |

Testing cannot prove that software has no defects. It provides evidence about the behaviour that has been checked and the risks that remain.

## 2. Verification and validation

These terms are related but different.

### Verification

Verification asks: **Are we building the solution correctly according to the specified requirements and design?**

Examples:
- Reviewing a requirement for completeness.
- Checking that a developer's implementation follows the API contract.
- Reviewing a design against an approved specification.
- Checking that calculations follow the documented rule.

### Validation

Validation asks: **Are we building the right solution for the real business need?**

Examples:
- A business user checks that the onboarding process supports the way customers actually register.
- A manager confirms that the new report answers the operational question.
- A customer service representative confirms that the support workflow is usable.

### Comparison

| Verification | Validation |
|---|---|
| Conformance to specification | Fitness for business purpose |
| Are we building it right? | Are we building the right thing? |
| Reviews, inspections and testing against requirements | User evaluation and acceptance against business needs |
| Can occur throughout delivery | Often includes user validation of the solution |

Both are necessary. A system may match a written requirement but still fail to solve the actual business problem if the requirement was incomplete or misunderstood.

## 3. Quality Assurance and Quality Control

### Quality Assurance (QA)

QA focuses on the processes used to prevent defects.

Examples:
- Defining development and review standards.
- Establishing test processes.
- Requiring peer reviews.
- Improving requirement quality.
- Defining release controls.

### Quality Control (QC)

QC focuses on evaluating the product or output to identify defects.

Examples:
- Executing test cases.
- Checking a report's calculations.
- Comparing actual and expected results.
- Recording defects.

| QA | QC |
|---|---|
| Process-oriented | Product-oriented |
| Prevents defects through good processes | Finds defects in deliverables |
| Standards, reviews and process improvement | Testing, inspection and measurement |

QA and QC work together. Testing is an important quality-control activity, while good requirement and delivery practices contribute to quality assurance.

## 4. Where testing fits in the software development lifecycle

A simplified delivery lifecycle:

~~~text
Business need
    |
    v
Requirements and analysis
    |
    v
Solution design
    |
    v
Development
    |
    v
Testing and defect correction
    |
    v
User Acceptance Testing
    |
    v
Release decision
    |
    v
Production monitoring and support
~~~

Testing should not be postponed until the final week. Requirements, designs and test ideas can be reviewed early.

### Shift-left testing

Shift-left means involving quality and testing activities earlier in the delivery lifecycle.

Examples:
- Review acceptance criteria before development.
- Identify boundary conditions during requirement analysis.
- Agree test data before the sprint begins.
- Review API contracts before integration testing.
- Prepare UAT scenarios while the feature is being built.

A BA contributes by making requirements clear, identifying business exceptions and helping stakeholders agree what successful behaviour means.

## 5. Testing levels

Testing can take place at different levels. The exact names and ownership vary between organizations.

### 5.1 Unit testing

Checks a small unit of code, such as a function or method, in isolation.

Example:
A developer tests a function that calculates a discount.

BA connection:
The BA provides the business rule and example values so the developer can understand the expected calculation.

### 5.2 Integration testing

Checks whether two or more components or systems communicate correctly.

Example:
The onboarding portal sends customer details to a customer-management system and receives a customer ID.

BA connection:
The BA clarifies field mapping, mandatory data, status handling and business outcomes across the systems.

### 5.3 System testing

Checks the integrated application as a complete system against its requirements.

Example:
A tester checks registration, login, profile updates, notifications and related error handling.

BA connection:
The BA helps clarify requirement intent and resolves questions about expected business behaviour.

### 5.4 User Acceptance Testing (UAT)

UAT checks whether the solution supports the agreed business processes and is acceptable to its intended users or business representatives.

Example:
Customer service representatives use the new onboarding system with representative scenarios and confirm whether they can complete their work correctly.

BA connection:
The BA helps define scenarios, coordinate users, clarify requirements, record outcomes and support the acceptance decision.

### Comparison

| Level | Main focus | Typical participants |
|---|---|---|
| Unit | Individual code units | Developers |
| Integration | Communication between components/systems | Developers and testers |
| System | Complete application behaviour | Testers/QA |
| UAT | Business fitness and user acceptance | Business users, product owner, BA, QA support |

UAT is not a replacement for system testing. Business users should not be expected to discover every technical defect that earlier testing should have found.

## 6. Testing types and approaches

### 6.1 Functional testing

Checks what the system does against functional requirements.

Examples:
- A user can register.
- A manager can approve a request.
- A customer can view an order.
- A report calculates total sales correctly.

### 6.2 Non-functional testing

Checks qualities of the system rather than a particular business function.

Examples:
- Performance: Does the page respond within the agreed target?
- Security: Can users access only permitted information?
- Usability: Can users complete the task without confusion?
- Compatibility: Does the application work in supported browsers?
- Reliability: Does it behave consistently under expected operating conditions?
- Accessibility: Can users with different access needs use the product?

A BA should capture business expectations and involve the relevant specialists for technical test design.

### 6.3 Positive testing

Checks behaviour when valid input is supplied.

Example:
A customer enters a valid email address and required details, then submits the registration form.

### 6.4 Negative testing

Checks behaviour when invalid, incomplete or unauthorized input is supplied.

Examples:
- Submit without a required field.
- Enter an invalid email address.
- Use an expired session.
- Attempt to access another customer's record.

### 6.5 Regression testing

Checks that previously working behaviour still works after a change.

Example:
A change to the registration page should not break login or profile updates.

### 6.6 Smoke testing

A quick check of critical functions to determine whether a build is stable enough for further testing.

Example:
Confirm that the application opens, a user can sign in and the main page loads.

### 6.7 Exploratory testing

A tester explores the application, learning its behaviour while designing and performing tests. It can uncover unexpected issues that scripted cases do not cover.

### 6.8 End-to-end testing

Checks a complete business journey across multiple components or systems.

Example:
A customer registers, verifies contact details, receives a customer ID, signs in and completes onboarding.

## 7. Testing techniques a BA should understand

### 7.1 Equivalence partitioning

Divide input values into groups expected to behave similarly. Test representative values from each group.

Example: An age field accepts values from 18 to 60 inclusive.

| Partition | Example | Expected |
|---|---:|---|
| Below minimum | 17 | Reject |
| Valid range | 35 | Accept |
| Above maximum | 61 | Reject |

The test designer may select representative values from each partition rather than testing every possible number.

### 7.2 Boundary value analysis

Many defects occur at the edges of allowed ranges.

For the age rule 18–60, useful values include:
- 17: just below the minimum.
- 18: minimum allowed.
- 19: just above the minimum.
- 59: just below the maximum.
- 60: maximum allowed.
- 61: just above the maximum.

### 7.3 Decision table testing

Useful when the outcome depends on combinations of conditions.

Example: A customer receives a welcome benefit only when registration is complete and email verification is successful.

| Registration complete? | Email verified? | Benefit issued? |
|---|---|---|
| No | No | No |
| No | Yes | No |
| Yes | No | No |
| Yes | Yes | Yes |

The table makes the business rule visible and helps testers cover combinations.

### 7.4 State transition testing

Useful when an item moves through defined statuses.

Example: A customer application may move through:

~~~text
Draft -> Submitted -> Under Review -> Approved
                              |
                              v
                           Rejected
~~~

Questions:
- Which transitions are allowed?
- Who can perform each transition?
- Can an application be reopened?
- What happens if a user attempts an invalid transition?
- Is a reason required for rejection?

### 7.5 Use-case testing

Tests a realistic sequence of user actions, including alternative and exception paths.

Example:
- Main flow: customer submits a complete registration.
- Alternative: customer saves a draft.
- Exception: email verification fails.
- Exception: duplicate email is already registered.

## 8. What is User Acceptance Testing?

User Acceptance Testing is a planned evaluation in which business representatives check whether a solution meets agreed business needs and is suitable for the intended use.

UAT focuses on real business tasks, rules and outcomes.

### 8.1 Example

A company replaces its manual customer onboarding process with a digital portal.

Business users may need to confirm:
- A customer can submit an application.
- Mandatory documents are captured.
- The system prevents duplicate registrations.
- An incomplete application can be saved or resumed according to the approved rule.
- Reviewers can approve or reject an application.
- Customers receive the correct notifications.
- The process gives staff enough information to complete their work.

### 8.2 UAT versus other testing

| System testing | UAT |
|---|---|
| Checks system behaviour against system requirements | Checks suitability against business needs |
| Usually led by QA/testers | Usually led by business representatives |
| Can include technical and functional coverage | Uses business scenarios and realistic workflows |
| Finds defects before business acceptance | Provides evidence for business acceptance |
| Does not by itself authorize business sign-off | Supports an authorized acceptance decision |

UAT should occur in an agreed test environment with approved test data and a defined entry and exit approach.

## 9. Roles and responsibilities in UAT

UAT is a team activity. Responsibilities should be agreed for each project.

| Role | Typical responsibility |
|---|---|
| Business sponsor | Provides business direction and may approve acceptance |
| Product owner/business owner | Confirms priorities and expected business outcomes |
| Business Analyst | Clarifies requirements, prepares scenarios, coordinates questions and traces outcomes |
| UAT lead/coordinator | Plans UAT, manages schedule, users, status and reporting |
| Business tester/end user | Executes scenarios and evaluates practical usability |
| QA/tester | Supports test design, environment readiness, defect reproduction and retesting |
| Developer | Investigates and fixes assigned defects |
| Project manager/scrum master | Coordinates delivery dependencies and decisions |
| System owner/vendor | Supports integration, access and system-specific questions |

The BA may coordinate UAT, but should not automatically approve acceptance on behalf of the business. The authorized business owner must make or confirm the acceptance decision.

## 10. BA responsibilities before UAT

### 10.1 Confirm requirement readiness

Check that:
- Requirements are approved or have an agreed baseline.
- Business rules are clear.
- Acceptance criteria are testable.
- Requirement changes are controlled.
- Dependencies and assumptions are visible.
- Important exceptions are documented.

### 10.2 Identify UAT scope

Agree:
- Which features and processes are included?
- Which user roles will participate?
- Which scenarios are critical?
- Which requirements are excluded?
- Which integrations must be available?
- Which browsers, devices or business locations are in scope?

### 10.3 Prepare UAT scenarios

A UAT scenario describes a business situation or objective to be evaluated.

Examples:
- Register a new customer with valid details.
- Attempt registration with an existing email address.
- Save an incomplete application and resume it.
- Submit an application with all mandatory documents.
- Reviewer approves an eligible application.
- Reviewer rejects an application with a required reason.
- Customer receives the correct confirmation.

A scenario is broader than a detailed test case. Day 38 will cover test cases and expected results in greater depth.

### 10.4 Prepare users and test data

Confirm:
- Who will execute each scenario?
- Do users understand their assigned roles?
- Are test accounts available?
- Is the test environment accessible?
- Is data synthetic or properly masked?
- Are all required integration dependencies available?
- Is there a support contact during execution?

Do not copy real customer data into a test environment unless explicitly approved and protected under organizational policy.

### 10.5 Define entry criteria

Entry criteria are conditions that should be satisfied before UAT begins.

Possible criteria:
- Required build is deployed to the UAT environment.
- Critical system testing is completed.
- Known high-severity defects are resolved or formally accepted for evaluation.
- UAT scope and scenarios are reviewed.
- Test accounts and data are prepared.
- Business users have access and a schedule.
- Required integrations are available.
- Defect logging and escalation process is agreed.

The project should define its actual criteria and any permitted exceptions.

## 11. BA responsibilities during UAT

The BA supports business users without leading them toward a predetermined result.

Typical activities:
1. Explain the business objective and scenario.
2. Confirm the tester is using the correct role and test data.
3. Observe whether the workflow matches the approved requirement.
4. Answer requirement questions consistently.
5. Record unexpected behaviour and user feedback.
6. Help distinguish a defect from a requirement gap, training issue or test-data issue.
7. Ensure each finding has enough detail for investigation.
8. Track scenario status and requirement coverage.
9. Escalate blockers and unresolved business decisions.
10. Communicate progress and risks to stakeholders.

A BA should not tell a tester to mark a scenario as passed when the expected business outcome was not achieved.

## 12. BA responsibilities after UAT

After execution, the BA helps:
- Review passed, failed, blocked and not-run scenarios.
- Confirm defects are linked to affected requirements and scenarios.
- Clarify business impact and priority with stakeholders.
- Coordinate retesting and regression evidence.
- Document workarounds and accepted limitations.
- Identify outstanding risks.
- Prepare an outcome summary.
- Obtain the appropriate business acceptance or rejection decision.
- Record conditions attached to any conditional acceptance.

### Possible UAT outcomes

| Outcome | Meaning |
|---|---|
| Accepted | Authorized business representative accepts the solution |
| Accepted with conditions | Acceptance is given subject to documented conditions and owners |
| Rejected/not accepted | Important business criteria are not met |
| Deferred | Decision is postponed pending evidence or resolution |

Acceptance rules and authority must be defined by the organization. A BA should not convert a failed result into acceptance simply to meet a release date.

## 13. UAT scenario design

A UAT scenario should be understandable to a business user and connected to a business requirement.

### 13.1 Scenario template

| Field | Description |
|---|---|
| Scenario ID | Unique reference, e.g. UAT-SC-001 |
| Scenario name | Short business-focused title |
| Business objective | What the user needs to accomplish |
| Requirement ID | Requirement being validated |
| User role | Person or role performing the scenario |
| Preconditions | Conditions required before starting |
| Test data | Approved data needed |
| High-level steps | Main business actions |
| Expected business outcome | What should be true at the end |
| Priority | Critical, High, Medium or Low based on agreed criteria |
| Owner | Person responsible for execution |
| Status | Not Started, In Progress, Passed, Failed or Blocked |

A detailed step-by-step test case, actual result and defect reference can be added during test case design.

### 13.2 Scenario quality checklist

A good scenario:
- Has a clear business purpose.
- Is linked to one or more requirements.
- Names the user role.
- Includes necessary preconditions.
- Uses appropriate test data.
- Describes a realistic business journey.
- Includes the expected business outcome.
- Covers important alternative and negative paths.
- Can be executed and evaluated consistently.

Avoid vague scenarios such as "Test registration." Prefer "Register a new customer using valid mandatory details and confirm that a unique customer profile is created."

## 14. Example: customer onboarding UAT scenario catalogue

Business context: A company wants to replace email-based customer registration with a digital onboarding portal.

### 14.1 Business requirements

| ID | Requirement |
|---|---|
| BR-01 | A new customer can submit an application with all mandatory information |
| BR-02 | The system validates mandatory fields and email format |
| BR-03 | The system prevents duplicate registration using the approved uniqueness rule |
| BR-04 | A customer can save and resume a draft if this capability is enabled |
| BR-05 | A submitted application receives a unique reference |
| BR-06 | An authorized reviewer can approve an eligible application |
| BR-07 | An authorized reviewer can reject an application and record a reason |
| BR-08 | The customer receives the approved status notification |
| BR-09 | Users can access only applications permitted by their role |

These are example requirements. Confirm the actual rules with the business owner before using them in a real project.

### 14.2 UAT scenarios

| Scenario ID | Scenario | Requirement | Priority |
|---|---|---|---|
| UAT-SC-001 | Submit a complete new customer application | BR-01, BR-05 | Critical |
| UAT-SC-002 | Submit an application with a missing mandatory field | BR-02 | High |
| UAT-SC-003 | Enter an invalid email address | BR-02 | High |
| UAT-SC-004 | Attempt to register an existing customer | BR-03 | Critical |
| UAT-SC-005 | Save a draft and resume it later | BR-04 | Medium |
| UAT-SC-006 | Reviewer approves an eligible application | BR-06 | Critical |
| UAT-SC-007 | Reviewer rejects an application with a reason | BR-07 | High |
| UAT-SC-008 | Confirm the customer receives the correct notification | BR-08 | High |
| UAT-SC-009 | User attempts to access an unauthorized application | BR-09 | Critical |
| UAT-SC-010 | Verify application reference can be used to locate the submission | BR-05 | High |

### 14.3 Detailed example scenario

**Scenario ID:** UAT-SC-001

**Name:** Submit a complete new customer application

**Business objective:** Confirm that a new customer can complete the registration process and receive a unique application reference.

**Requirement links:** BR-01, BR-05

**User role:** New customer

**Preconditions:**
- UAT environment is available.
- A test customer who does not already exist is available.
- Required test data has been approved.
- The customer can access the registration portal.

**High-level steps:**
1. Open the customer registration page.
2. Enter valid mandatory customer information.
3. Complete required declarations and consent fields.
4. Submit the application.
5. Record the confirmation reference.
6. Search for the application using the reference, if the user role permits.

**Expected business outcome:**
- The application is accepted for processing.
- A unique reference is generated.
- The submitted details are associated with that application.
- The customer sees the approved confirmation message.
- No duplicate application is created by the single submission.

**Priority:** Critical

**Evidence:** UAT tester records the generated reference and captures approved test-environment evidence without exposing sensitive data.

## 15. UAT data, environment and evidence

### Test data

Test data should represent the situations that matter to the business.

Examples:
- New customer with valid details.
- Existing customer to test duplicate rules.
- Application missing a mandatory document.
- Application eligible for approval.
- Application that should be rejected.
- User with a reviewer role.
- User without reviewer permission.

Use synthetic or approved masked data. Document how test data is created, reset and removed.

### Test environment

A UAT environment is a controlled environment used for business acceptance testing. It should be sufficiently representative of the intended solution while remaining separate from production unless the organization has explicitly approved a different approach.

Confirm:
- Correct application version.
- Required integrations and test endpoints.
- User access and roles.
- Configuration and reference data.
- Test notifications or safe notification routing.
- Known environment limitations.
- Data reset and cleanup process.

### Evidence

Evidence may include:
- Scenario execution record.
- Screenshots from an approved test environment.
- Application or transaction reference.
- Output report.
- Timestamp and tester identity.
- Defect ID.

Evidence should be relevant, readable and protected. Avoid recording credentials, access tokens or unnecessary personal information.

## 16. Defect, requirement gap, data issue or training issue?

Not every failed scenario has the same cause.

| Finding type | Meaning | Example |
|---|---|---|
| Defect | Delivered behaviour differs from approved requirement | Submit accepts an invalid email despite the documented rule |
| Requirement gap | Required business behaviour was not defined clearly | No agreed rule exists for duplicate applications with different email addresses |
| Test-data issue | Test data is incorrect or unsuitable | Test customer already exists unexpectedly |
| Environment issue | UAT environment or dependency is unavailable or misconfigured | Notification service is not connected to the UAT endpoint |
| Training/usability issue | User cannot complete the task because instructions or interaction are unclear | Reviewer cannot identify where to record a rejection reason |

The BA helps investigate and classify the finding with the relevant owners. Do not label every unexpected result as a software defect before checking the requirement, data and environment.

## 17. UAT status and reporting

A simple status report gives stakeholders visibility into progress.

Example:

| Measure | Example value |
|---|---:|
| Total scenarios | 10 |
| Passed | 6 |
| Failed | 2 |
| Blocked | 1 |
| Not started | 1 |
| Execution completed | 80% |

Execution completion in this example means 8 of 10 scenarios have been attempted (passed, failed or blocked). It does not mean 80% of the solution is accepted.

Useful reporting measures:
- Planned scenarios.
- Executed scenarios.
- Passed, failed, blocked and not-started scenarios.
- Open defects by severity and priority.
- Critical business journeys not yet tested.
- Requirements with no UAT coverage.
- Retest progress.
- Outstanding risks and decisions.

Do not use pass percentage alone as the acceptance decision. One failed critical scenario can matter more than many passed low-priority scenarios.

## 18. Mini-project: UAT Test Scenario Design

<badge color="success">Day 37 practical project</badge>

### Project brief

A company currently collects customer onboarding applications through email and spreadsheets. It plans to introduce a digital portal.

The portal is expected to support:
- New customer application.
- Mandatory field validation.
- Duplicate customer checks.
- Draft saving and resumption, if approved.
- Application reference generation.
- Reviewer approval and rejection.
- Customer notifications.
- Role-based access.

Your task is to prepare a UAT Test Scenario Design document.

### Deliverable A: UAT scope

Document:
1. Business objective.
2. In-scope capabilities.
3. Out-of-scope capabilities.
4. User roles.
5. Systems and integrations.
6. Assumptions and dependencies.
7. Entry criteria.
8. Exit criteria.
9. UAT participants and responsibilities.

### Deliverable B: Scenario catalogue

Create at least 12 business scenarios covering:
- Successful application.
- Missing mandatory information.
- Invalid email or phone format.
- Duplicate customer.
- Draft and resume.
- Application submission and reference.
- Approval.
- Rejection with reason.
- Customer notification.
- Unauthorized access.
- Integration unavailable.
- Repeated submission or duplicate action.

For each scenario, include:
- Scenario ID.
- Scenario title.
- Business objective.
- Requirement reference.
- User role.
- Preconditions.
- Test data.
- High-level steps.
- Expected business outcome.
- Priority.
- Owner.

### Deliverable C: Requirement coverage

Use a simple traceability view:

| Requirement ID | Requirement summary | Scenario IDs | Covered? |
|---|---|---|---|
| BR-01 | Submit complete application | UAT-SC-001 | Yes |
| BR-02 | Validate mandatory fields | UAT-SC-002, UAT-SC-003 | Yes |
| BR-03 | Prevent duplicate registration | UAT-SC-004 | Yes |
| BR-04 | Save and resume draft | UAT-SC-005 | Yes |
| BR-05 | Generate application reference | UAT-SC-001, UAT-SC-006 | Yes |
| BR-06 | Approve eligible application | UAT-SC-007 | Yes |
| BR-07 | Reject with reason | UAT-SC-008 | Yes |
| BR-08 | Send customer notification | UAT-SC-009 | Yes |
| BR-09 | Enforce role-based access | UAT-SC-010 | Yes |

The scenario IDs above are illustrative. Make sure your final catalogue contains matching scenarios and that each requirement is genuinely covered.

### Deliverable D: UAT execution plan

Include:
- Planned dates and session schedule.
- Business testers and backup testers.
- Environment and access readiness.
- Test data preparation.
- Scenario execution order.
- Defect logging channel.
- Daily status reporting.
- Retest and regression approach.
- Final acceptance decision owner.

### Deliverable E: Final UAT summary template

~~~text
UAT SUMMARY

Project:
Build/version:
UAT period:
UAT lead:
Business acceptance owner:

Scope:
- In scope:
- Out of scope:

Execution:
- Total scenarios:
- Passed:
- Failed:
- Blocked:
- Not started:

Critical open defects:
1.
2.

Outstanding business risks:
1.
2.

Known limitations:
1.
2.

Decision:
- Accepted / Accepted with conditions / Not accepted / Deferred

Conditions and actions:
- Action:
- Owner:
- Due date:

Business decision-maker:
Decision date:
Evidence location:
~~~

### Evaluation rubric — 100%

| Assessment area | Weight |
|---|---:|
| Business objective, scope and roles | 10% |
| Scenario quality and business realism | 25% |
| Requirement traceability | 15% |
| Positive, negative and exception coverage | 15% |
| Preconditions, data and expected outcomes | 15% |
| UAT plan, entry/exit criteria and responsibilities | 10% |
| Reporting, evidence and acceptance approach | 10% |
| **Total** | **100%** |

### Portfolio discussion points

Be ready to explain:
- How you selected the scenarios.
- Which scenarios are most critical and why.
- How you ensured requirements had test coverage.
- How you would handle a failed scenario.
- How you would distinguish a defect from a requirement gap.
- Who has authority to accept the solution.
- What risks remain if a critical scenario is blocked.

## 19. Common UAT mistakes

1. Starting UAT before the build and environment are ready.
2. Asking users to test without explaining the business scenario.
3. Testing only the happy path.
4. Using production customer data without authorization.
5. Writing scenarios that are not linked to requirements.
6. Treating a scenario as passed without checking its expected outcome.
7. Letting the BA or developer decide business acceptance without authority.
8. Ignoring blocked scenarios in the final report.
9. Failing to retest after a defect fix.
10. Assuming a high pass percentage automatically means the solution is acceptable.
11. Failing to record conditions attached to acceptance.
12. Treating UAT as a substitute for integration and system testing.

## 20. Knowledge check

**Q1. What is the primary purpose of software testing?**

A. To guarantee that software has no defects  
B. To evaluate behaviour and find defects against expected outcomes  
C. To replace requirement analysis  
D. To approve project budgets

**Answer: B.** Testing provides evidence about the behaviour checked and helps discover defects. It cannot guarantee the absence of all defects.

**Q2. What is the main focus of UAT?**

A. Checking individual code functions  
B. Checking business fitness and user acceptance  
C. Designing database indexes  
D. Writing application source code

**Answer: B.** UAT checks whether the solution supports agreed business needs and intended user workflows.

**Q3. Who normally provides the business acceptance decision?**

A. Any developer  
B. The authorized business owner or representative  
C. The API gateway  
D. The database administrator in every project

**Answer: B.** Acceptance authority should be agreed and documented. The BA supports the decision but does not automatically own it.

**Q4. What is negative testing?**

A. Testing only successful input  
B. Testing invalid, incomplete or unauthorized conditions  
C. Deleting all test cases  
D. Testing only in production

**Answer: B.** Negative testing checks how the solution handles invalid or disallowed situations.

**Q5. What is an entry criterion?**

A. A condition that should be satisfied before UAT begins  
B. A final production invoice  
C. A defect severity  
D. A database column

**Answer: A.** Entry criteria establish readiness for UAT.

**Q6. A tester cannot complete a scenario because the UAT environment is down. What is the most appropriate status?**

A. Passed  
B. Failed automatically  
C. Blocked  
D. Accepted

**Answer: C.** The scenario cannot be evaluated until the environment issue is resolved. Record the blocker and its owner.

**Q7. What is regression testing?**

A. Checking that existing behaviour still works after a change  
B. Approving a new employee  
C. Replacing UAT  
D. Changing an API URL

**Answer: A.** Regression testing checks that a change has not broken previously working functionality.

**Q8. Why link UAT scenarios to requirements?**

A. To make the document longer  
B. To show which business requirements have been validated and identify gaps  
C. To avoid stakeholder review  
D. To remove the need for test evidence

**Answer: B.** Traceability helps demonstrate coverage and identify untested requirements.

**Q9. A feature behaves exactly as documented, but users say the process does not solve their problem. What might this indicate?**

A. The requirement may not represent the actual business need  
B. All testing should stop permanently  
C. The user must be wrong  
D. The API status code must be 200

**Answer: A.** This is a validation concern. The team should revisit the business need and requirement quality.

**Q10. Is a 95% UAT pass rate sufficient for acceptance by itself?**

A. Always  
B. Never, under any circumstances  
C. No; critical failures, risks, scope and authorized business judgement also matter  
D. Only if the BA says so

**Answer: C.** Acceptance is a business decision based on agreed criteria and risk, not a percentage alone.

## 21. Business Analyst interview questions and sample answers

### 1. What is UAT?

UAT is User Acceptance Testing. Business representatives execute realistic scenarios to confirm that the solution supports the agreed business processes and requirements. The results help the authorized business owner decide whether to accept the solution.

### 2. What is the BA's role in UAT?

The BA clarifies requirements, identifies business scenarios, links scenarios to requirements, coordinates with business users, answers requirement questions, records findings, helps classify issues and prepares outcome reporting. The BA supports acceptance but does not automatically approve on behalf of the business.

### 3. What is the difference between system testing and UAT?

System testing checks the integrated application against system requirements and is generally led by QA/testers. UAT is led by business representatives and checks whether the solution is suitable for real business tasks and outcomes.

### 4. What are entry and exit criteria?

Entry criteria are readiness conditions that should be met before testing starts, such as an available build, environment, test data and approved scenarios. Exit criteria define what evidence and conditions are required to finish the test phase, such as execution status, defect thresholds, risk review and business decision.

### 5. What would you do if a UAT scenario failed?

I would capture the scenario, test data, actual behaviour, expected behaviour, evidence and impact. I would help determine whether it is a defect, requirement gap, data issue or environment issue. I would link it to the requirement, coordinate investigation with the responsible team and support retesting after a fix.

### 6. What is the difference between a test scenario and a test case?

A test scenario describes a business situation or objective to validate, such as submitting a new customer application. A test case gives the detailed preconditions, data, steps and expected results needed to execute and evaluate that scenario.

### 7. How do you know whether UAT is complete?

I would compare execution results with the agreed exit criteria, review failed and blocked critical scenarios, examine open defects and risks, confirm retesting evidence, and obtain the acceptance decision from the authorized business owner. A pass percentage alone is not enough.

## 22. Quick revision sheet

| Concept | Key point |
|---|---|
| Software testing | Evaluates behaviour against expected outcomes |
| Verification | Are we building it right? |
| Validation | Are we building the right solution? |
| QA | Focuses on processes that prevent defects |
| QC | Evaluates the product to identify defects |
| Unit testing | Individual code unit |
| Integration testing | Communication between components |
| System testing | Complete integrated application |
| UAT | Business fitness and user acceptance |
| Positive testing | Valid inputs and expected use |
| Negative testing | Invalid, incomplete or unauthorized use |
| Regression testing | Existing behaviour after a change |
| Smoke testing | Basic build stability |
| Entry criteria | Conditions to begin UAT |
| Exit criteria | Conditions to complete UAT |
| Test scenario | Business situation to validate |
| Test case | Detailed executable test instructions |
| Defect | Delivered behaviour differs from agreed expectation |
| Blocked | Execution cannot proceed |
| Traceability | Link requirements to scenarios and results |

## 23. Day 37 completion checklist

- [ ] I can explain why software testing is needed.
- [ ] I can distinguish verification and validation.
- [ ] I can distinguish QA and QC.
- [ ] I understand unit, integration, system and UAT testing.
- [ ] I can explain functional and non-functional testing.
- [ ] I understand positive, negative, regression and smoke testing.
- [ ] I can explain equivalence partitioning and boundary value analysis.
- [ ] I understand decision tables and state transition testing.
- [ ] I can describe the BA's responsibilities before, during and after UAT.
- [ ] I can define UAT entry and exit criteria.
- [ ] I can write business-focused UAT scenarios.
- [ ] I can link scenarios to requirements.
- [ ] I can distinguish a defect from a requirement, data or environment issue.
- [ ] I have prepared the UAT Test Scenario Design mini-project.

## 24. Official learning references

- ISTQB — Certified Tester Foundation Level information: https://www.istqb.org/certifications/certified-tester-foundation-level
- ISTQB glossary: https://glossary.istqb.org/
- Atlassian — User Acceptance Testing: https://www.atlassian.com/software-testing/types-of-software-testing
- Microsoft Learn — Testing concepts and guidance: https://learn.microsoft.com/en-us/
- GOV.UK Service Manual — Testing: https://www.gov.uk/service-manual/agile-delivery/how-the-discovery-phase-works

Use these references as additional reading. Your project's approved test strategy, organizational standards and business acceptance rules take precedence.

---

**Day 37 outcome:** You can explain software testing levels and techniques, describe the BA's contribution to UAT, and create a business-focused UAT scenario catalogue. Day 38 builds on this by covering detailed test cases, expected results, defect recording and acceptance validation.
