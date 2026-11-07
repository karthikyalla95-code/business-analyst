# Day 38: Test Cases, Expected Results, Defects and Acceptance Validation

## Learning outcomes
By the end of this lesson, you should be able to:
- Distinguish a test scenario from a detailed test case.
- Write repeatable test cases with preconditions, data, steps and expected results.
- Understand test design, execution status and coverage.
- Record, classify and track defects.
- Distinguish severity from priority and retesting from regression testing.
- Validate acceptance criteria and support an evidence-based business acceptance decision.
- Build a practical UAT Test Case Repository.

## 1. From requirement to test case

A requirement describes what the business needs. An acceptance criterion defines a condition that must be satisfied. A test scenario describes a business situation to validate. A test case gives the detailed instructions and expected outcomes.

~~~text
Business requirement
       |
       v
Acceptance criteria
       |
       v
Test scenario
       |
       v
Detailed test case
       |
       v
Execute and record actual result
       |
       +---- Matches expected ----> Pass
       |
       +---- Differs --------------> Fail / investigate
~~~

**Example**

Requirement: A customer must provide a valid email address before submitting an application.

Acceptance criterion: If the email address is missing or invalid, the system prevents submission and displays a clear validation message.

Scenario: Attempt to submit an application using an invalid email address.

Test case: Enter all required details, enter an invalid email such as asha.example.com in the email field, submit the form and inspect the outcome.

Expected result: The application is not submitted, the email field is identified and a clear validation message is displayed.

A test case should be specific enough that another tester can execute it and decide consistently whether it passed.

## 2. Test scenario versus test case

| Test scenario | Test case |
|---|---|
| High-level business situation | Detailed validation procedure |
| Describes what to test | Describes how to test it |
| May have multiple test cases | Contains specific steps and expected results |
| Example: Validate registration | Example: Submit registration with missing email |
| Helps define coverage | Helps execute and record evidence |

One scenario can contain multiple cases. For customer registration, cases might cover valid details, missing name, missing email, invalid email, duplicate email, invalid phone number, unusually long input and unauthorized access.

## 3. Anatomy of a good test case

| Field | Purpose |
|---|---|
| Test Case ID | Unique identifier |
| Scenario ID | Parent business scenario |
| Requirement ID | Requirement being validated |
| Title | Short description |
| Objective | What the test proves |
| Preconditions | Conditions before execution |
| Test data | Input values and records |
| Steps | Ordered actions |
| Expected result | Required behaviour |
| Actual result | Observed behaviour |
| Status | Not Run, Pass, Fail or Blocked |
| Evidence | Screenshot, output, reference or log |
| Executed by/date | Execution ownership and date |
| Defect ID | Related defect, if raised |
| Comments | Notes or limitations |

### 3.1 Test case writing principles
A good test case is:
- **Clear:** Avoid vague wording such as works properly.
- **Specific:** Use concrete inputs and actions.
- **Repeatable:** Another tester can follow the same procedure.
- **Traceable:** Link it to a requirement and scenario.
- **Observable:** Its outcome can be checked.
- **Business-relevant:** It validates a real user or business outcome.
- **Maintainable:** Update it when approved requirements change.

Avoid combining unrelated checks into one case. Separate cases make failures easier to investigate.

## 4. Preconditions, test data, steps and expected results

**Preconditions** are conditions that must be true before execution:
- UAT environment is available.
- Tester has the correct role.
- Customer record does not already exist.
- Required test configuration is enabled.

**Test data** is the input used by the test. Example synthetic data:

| Field | Example value |
|---|---|
| Customer name | Asha Rao |
| Email | asha.rao.test@example.com |
| Phone | 9000012345 |
| City | Hyderabad |
| Application type | Individual |

These values are fictional. Use approved synthetic or masked data in real projects.

**Steps** should be written in execution order:
1. Open the registration page.
2. Enter the customer name.
3. Enter the email address.
4. Enter the mobile number.
5. Select the application type.
6. Submit the form.

**Expected result** should describe observable behaviour.

Weak: The form should work correctly.

Strong: The system saves the application, generates a unique application reference and displays a confirmation message.

For complex workflows, state expected outcomes after important steps as well as at the end.

## 5. Positive and negative test cases

**Positive testing** checks valid input and expected use.

Example: Enter valid customer details, submit the form and confirm the application is created.

**Negative testing** checks invalid, incomplete, duplicate or unauthorized input.

Example: Leave the email field blank, submit the form and confirm that the application is not created and a required-field message appears.

| ID | Test case | Test data | Expected result |
|---|---|---|---|
| TC-001 | Submit valid application | All mandatory fields valid | Application created and reference displayed |
| TC-002 | Submit with blank name | Name empty | Submission prevented; name validation shown |
| TC-003 | Submit with blank email | Email empty | Submission prevented; email validation shown |
| TC-004 | Submit invalid email | asha.example.com | Submission prevented; email format message shown |
| TC-005 | Submit duplicate email | Existing test email | Approved duplicate rule applied |
| TC-006 | Submit invalid phone | 123 | Phone validation shown according to approved rule |

Do not invent business rules. Confirm phone format, duplicate matching logic and exact validation messages with the requirement owner.

## 6. Test design techniques

### 6.1 Equivalence partitioning
Divide values into groups expected to behave similarly and select representative values.

Example: A quantity field accepts 1 through 100 inclusive.

| Partition | Example | Expected |
|---|---:|---|
| Below range | 0 | Reject |
| Valid range | 50 | Accept |
| Above range | 101 | Reject |

### 6.2 Boundary value analysis
Test values at and around the limits. For a 1–100 rule, useful values are 0, 1, 2, 99, 100 and 101.

### 6.3 Decision table testing
Use a table when an outcome depends on combinations of conditions.

Example: An application is eligible for approval only when identity verification is complete and mandatory documents are present.

| Identity verified? | Documents complete? | Expected decision |
|---|---|---|
| No | No | Cannot approve |
| No | Yes | Cannot approve |
| Yes | No | Cannot approve |
| Yes | Yes | Eligible for approval |

### 6.4 State transition testing
Test allowed and disallowed status changes.

~~~text
Draft -> Submitted -> Under Review -> Approved
                              |
                              +------> Rejected
~~~

Potential cases:
- Draft can be submitted.
- Submitted application enters review.
- Authorized reviewer can approve.
- Authorized reviewer can reject with a reason.
- Customer cannot approve their own application.
- Approved application cannot return to Draft unless an explicit rule permits it.

### 6.5 Exploratory testing and error guessing
Explore likely failure points using product knowledge. Examples:
- Double-click Submit.
- Refresh immediately after submission.
- Use the browser Back button after saving.
- Open the same application in two sessions.
- Paste a very long value into a text field.
- Interrupt a dependency during an approved test.

Document important findings so they can be repeated.

## 7. Expected result versus actual result

The expected result comes from approved requirements, acceptance criteria or agreed design. The actual result is what the tester observes.

| Expected result | Actual result | Evaluation |
|---|---|---|
| Valid application is saved | Saved and reference shown | Pass |
| Invalid email is rejected | Invalid email accepted | Fail |
| Unauthorized user is denied | User sees another customer's record | Fail; serious security concern |
| Notification is sent | Notification service unavailable | Blocked or failed according to test conditions |

A test is not passed merely because the page did not crash. Compare the complete observed business outcome with the expected result.

## 8. Test execution and status

| Status | Meaning |
|---|---|
| Not Run | Test has not been executed |
| In Progress | Execution has started but is incomplete |
| Pass | Actual result meets expected result |
| Fail | Actual result differs from expected result |
| Blocked | Test cannot proceed because of an external condition |
| Not Applicable | Test is excluded with an approved reason |
| Retest Required | A fix or change needs verification |

Define status meanings before execution. A blocked case must include the blocker, owner and next action. Never report it as passed.

### Example execution record

| Test ID | Expected result | Actual result | Status | Defect |
|---|---|---|---|---|
| TC-001 | Valid application saved | Saved; reference displayed | Pass | — |
| TC-002 | Blank name rejected | Required message shown | Pass | — |
| TC-003 | Invalid email rejected | Application submitted | Fail | DEF-001 |
| TC-004 | Duplicate prevented | Duplicate warning displayed | Pass | — |
| TC-005 | Notification sent | Notification service unavailable | Blocked | ENV-002 |

## 9. What is a defect?

A defect is a flaw that causes product behaviour or output to differ from an agreed requirement, specification or expected result.

Examples:
- Invalid email is accepted despite an approved validation rule.
- A discount is calculated incorrectly.
- A user can view another customer's information.
- A report omits approved transactions.
- A submitted application is not saved.
- A notification is sent to the wrong recipient.

A defect report should contain reproducible information wherever possible.

### 9.1 Defect versus requirement change

| Defect | Requirement change |
|---|---|
| Agreed behaviour is not delivered correctly | Business wants to change or add expected behaviour |
| Approved email validation is missing | Business now wants an additional document field |
| Usually handled through defect management | Usually handled through change control or backlog refinement |

If the original requirement is unclear or incomplete, the team may need clarification or a controlled requirement change rather than treating the issue as a straightforward coding defect.

## 10. Defect report structure

| Field | Description |
|---|---|
| Defect ID | Unique identifier |
| Title | Short, precise description |
| Related requirement/test case | Traceability |
| Environment/build | Where and in which version it occurred |
| Preconditions | Required setup |
| Steps to reproduce | Exact actions |
| Expected result | Approved behaviour |
| Actual result | Observed behaviour |
| Severity | Impact of the defect |
| Priority | Urgency of fixing it |
| Evidence | Screenshot, log, reference or recording |
| Reporter/assignee | Ownership |
| Status | Lifecycle state |
| Workaround | Temporary alternative, if any |

**Weak title:** Registration issue.

**Better title:** Registration accepts an invalid email address and creates an application.

### Example reproduction steps
1. Sign in using an approved UAT customer account.
2. Open New Application.
3. Enter a valid name and phone number.
4. Enter asha.example.com in the email field.
5. Complete other mandatory fields.
6. Select Submit.
7. Observe the confirmation page and application record.

**Expected:** The system rejects the invalid email, displays a clear message and does not create an application.

**Actual:** The system creates an application and displays a success reference.

**Evidence:** Approved UAT screenshot and application reference, with sensitive information masked.

## 11. Severity versus priority

**Severity** describes how seriously a defect affects the product, users, data or business operations.

| Severity | Example |
|---|---|
| Critical | Major security exposure, data corruption or complete outage |
| High | Important business process cannot be completed |
| Medium | Function is impaired but a reasonable workaround exists |
| Low | Minor visual or wording issue with limited impact |

**Priority** describes how urgently the defect should be addressed, considering business urgency, release plans, dependencies and risk.

| Priority | Typical meaning |
|---|---|
| P1 | Fix immediately or before critical release activity |
| P2 | Fix in the near-term planned delivery |
| P3 | Schedule when capacity permits |
| P4 | Low urgency; consider for future improvement |

Example: A spelling error on a highly visible regulatory notice might have low technical severity but high business priority. A rarely used cosmetic issue may have low severity and priority. A security exposure may be critical and urgent.

Severity and priority definitions vary by organization. Agree the scale and decision authority at project start.

## 12. Defect lifecycle and triage

A common lifecycle is:

~~~text
New -> Triaged -> Assigned -> In Progress -> Fixed
                                               |
                                               v
                                         Ready for Retest
                                          /          \
                                    Pass /            \ Fail
                                        v              v
                                      Closed        Reopened
~~~

Other possible states:
- Rejected: Not a valid defect, with explanation.
- Duplicate: Same issue already exists.
- Deferred: Fix postponed with an approved reason.
- Cannot Reproduce: Team cannot reproduce using supplied information.
- On Hold: Investigation or fix is waiting for a dependency.

**Triage** is the review used to understand and decide how to handle a reported defect.

The team may:
1. Confirm reproducibility.
2. Check the requirement and expected result.
3. Identify business impact.
4. Agree severity and priority.
5. Check for duplicates.
6. Assign an owner.
7. Agree a target resolution or documented decision.

The BA contributes business context and requirement traceability. Technical diagnosis and code fixes belong to the relevant engineering team.

## 13. Retesting versus regression testing

**Retesting** checks whether a specific reported defect has been fixed.

Example:
- DEF-001 reported that invalid email was accepted.
- Developer changes validation.
- Tester repeats TC-003.
- If invalid email is rejected as expected, the defect may be closed.

**Regression testing** checks whether the change has affected other existing behaviour.

After changing email validation, related checks may include:
- Valid registration still works.
- Existing customer login still works.
- Profile updates still work.
- Notifications still use the correct email address.

| Retesting | Regression testing |
|---|---|
| Checks the specific fix | Checks for unintended side effects |
| Focuses on the failed behaviour | Covers related or previously working behaviour |
| Repeats the failed test | Runs selected existing tests |

Do not close a defect just because a developer says it is fixed. Follow the agreed verification process and retain evidence.

## 14. Acceptance criteria and acceptance validation

Acceptance criteria are specific conditions that a solution or feature must satisfy to be accepted.

Good criteria are clear, testable, relevant to the business objective, unambiguous and agreed with stakeholders.

**Weak:** The customer form should be user-friendly.

**Stronger:**
- The form identifies all mandatory fields.
- If a mandatory field is empty, submission is prevented.
- A clear message identifies the field that needs attention.
- Valid data can be submitted successfully.
- The customer receives a unique application reference after successful submission.

### 14.1 Given–When–Then format

~~~text
Given: A customer is on the registration page
And: All required fields are available

When: The customer enters valid details and submits the form

Then: The application is saved
And: A unique application reference is generated
And: A confirmation message is displayed
~~~

Negative example:

~~~text
Given: A customer is on the registration page

When: The customer leaves the email field blank and submits

Then: The application is not created
And: A clear required-field message is displayed
~~~

This format is often used with Behaviour-Driven Development (BDD). It makes expectations easier for business users, testers and developers to discuss.

### 14.2 Acceptance validation checklist

For each acceptance criterion, confirm:
1. Is it linked to a requirement?
2. Is there a suitable test case?
3. Is the expected result explicit?
4. Was the test executed in the correct environment?
5. Is the actual result recorded?
6. Is evidence available?
7. Are failures linked to defects or decisions?
8. Have required fixes been retested?
9. Are related regression checks complete?
10. Has the authorized business representative reviewed the outcome?

### 14.3 Acceptance decision

A business acceptance decision should consider:
- Critical business journeys.
- Acceptance criteria results.
- Failed and blocked tests.
- Open defects and their severity.
- Workarounds and operational impact.
- Outstanding risks and dependencies.
- Compliance and security obligations.
- Agreed exit criteria.

Possible outcomes:
- Accepted.
- Accepted with documented conditions.
- Not accepted.
- Deferred pending more evidence or fixes.

The authorized business owner makes or approves the decision according to project governance. The BA prepares accurate evidence and supports the decision.

## 15. Requirement traceability and test coverage

Traceability connects requirements to scenarios, test cases, execution results and defects.

~~~text
Requirement
    |
    v
Acceptance criterion
    |
    v
Scenario
    |
    v
Test case
    |
    v
Execution result
    |
    +---- Pass
    |
    +---- Fail -> Defect -> Fix -> Retest
~~~

### 15.1 Traceability matrix example

| Requirement | Acceptance criterion | Test case | Result | Defect |
|---|---|---|---|---|
| BR-01: Submit application | Valid details create application | TC-001 | Pass | — |
| BR-02: Validate email | Invalid email is rejected | TC-003 | Fail | DEF-001 |
| BR-03: Prevent duplicates | Existing email cannot create unintended duplicate | TC-005 | Pass | — |
| BR-04: Save draft | Draft can be resumed | TC-008 | Not Run | — |
| BR-05: Generate reference | Successful submission shows unique reference | TC-001 | Pass | — |
| BR-06: Reviewer approval | Authorized reviewer can approve eligible application | TC-010 | Blocked | ENV-002 |

This matrix shows BR-04 has not yet been tested and BR-06 is blocked. Those gaps should be visible in the UAT report.

### 15.2 Useful coverage measures

**Requirement coverage** = requirements with at least one mapped test case ÷ total in-scope requirements × 100.

**Execution completion** = test cases executed ÷ total planned test cases × 100. Define whether blocked cases count as executed.

**Pass rate** = passed test cases ÷ executed test cases × 100. State clearly how failed and blocked cases are treated.

These measures explain progress but do not independently determine acceptance. Criticality and business risk matter.

## 16. Defect prioritization example

Imagine a customer onboarding portal has these findings:

| Defect | Issue | Severity | Suggested priority | Business impact |
|---|---|---|---|---|
| DEF-001 | Invalid email accepted | High | P1/P2 after triage | Incorrect customer data |
| DEF-002 | Customer can view another customer's application | Critical | P1 | Confidentiality breach |
| DEF-003 | Button text slightly misaligned | Low | P3/P4 | Minor usability issue |
| DEF-004 | Application reference not generated | High | P1 | Users cannot reliably track submission |

Priority examples are illustrative. Use the agreed policy and consider release timing, exposure and workarounds.

## 17. Mini-project: UAT Test Case Repository

<badge color="success">Day 38 practical project</badge>

### Project brief
Continue the customer onboarding portal project from Day 37. Create a structured repository of detailed UAT test cases, execution results, defects and acceptance validation.

### Deliverable A: Test case repository

Create at least 15 test cases covering:
1. Valid application submission.
2. Missing customer name.
3. Missing email.
4. Invalid email format.
5. Invalid phone format.
6. Duplicate customer.
7. Minimum and maximum permitted input length.
8. Save draft.
9. Resume draft.
10. Successful application reference generation.
11. Authorized reviewer approval.
12. Reviewer rejection with a reason.
13. Customer notification.
14. Unauthorized application access.
15. Repeated submission or double-click.

For each case include:
- Test Case ID, Scenario ID and Requirement ID.
- Title and objective.
- Preconditions and test data.
- Numbered steps.
- Expected and actual results.
- Execution status.
- Evidence reference.
- Tester and date.
- Defect ID, if applicable.

Do not assume every listed capability is an approved requirement. If a rule is unconfirmed, record it as an assumption or open question and obtain stakeholder clarification before final execution.

### Deliverable B: Defect log

Create at least five sample defect records. Label fictional training records as examples.

Include:
- Defect ID and title.
- Related requirement and test case.
- Environment and build.
- Reproduction steps.
- Expected and actual result.
- Severity and priority.
- Evidence.
- Owner and status.
- Workaround or decision.

Include examples of a high-impact business defect, security/access-control defect, cosmetic defect, environment blocker and duplicate or non-reproducible finding.

### Deliverable C: Defect lifecycle tracker

Track:
- Defect ID and current status.
- Assigned owner.
- Date raised and last updated.
- Target resolution date.
- Retest result.
- Closure evidence.

Demonstrate one defect moving through New, Triaged, Assigned, In Progress, Fixed, Ready for Retest and Closed. Include another example where a failed retest reopens the defect.

### Deliverable D: Traceability matrix

Map every in-scope requirement to:
- Acceptance criteria.
- Scenario ID.
- Test case ID.
- Execution status.
- Defect ID, if applicable.

Identify requirements with no test case, tests without requirement links, failed tests, blocked tests and critical requirements not yet validated.

### Deliverable E: Acceptance validation report

Include:
- Scope and build.
- Planned and executed test cases.
- Pass, fail, blocked and not-run counts.
- Requirement coverage.
- Critical open defects.
- Retest and regression results.
- Outstanding risks.
- Recommended business decision.
- Authorized decision-maker and sign-off date.

### Suggested repository structure

~~~text
UAT_Test_Case_Repository/
|
+-- 01_UAT_Scope_and_Plan.md
+-- 02_Test_Case_Register.xlsx
+-- 03_Test_Execution_Log.xlsx
+-- 04_Defect_Log.xlsx
+-- 05_Requirement_Traceability_Matrix.xlsx
+-- 06_Acceptance_Validation_Report.md
+-- 07_Evidence/
    +-- TC-001/
    +-- TC-002/
    +-- DEF-001/
~~~

For a learning portfolio, Markdown or a spreadsheet is acceptable. Use synthetic data and sample evidence only.

### Sample test case template

~~~text
TEST CASE

Test Case ID:
Scenario ID:
Requirement ID:
Title:
Objective:
Priority:
Tester:

PRECONDITIONS
1.
2.

TEST DATA
Field:
Value:

TEST STEPS
1.
2.
3.

EXPECTED RESULT
1.
2.

ACTUAL RESULT:

STATUS: Not Run / Pass / Fail / Blocked

EVIDENCE:
DEFECT ID:
EXECUTED BY:
EXECUTION DATE:
COMMENTS:
~~~

### Sample defect template

~~~text
DEFECT REPORT

Defect ID:
Title:
Related requirement:
Related test case:
Environment/build:

PRECONDITIONS:

STEPS TO REPRODUCE
1.
2.
3.

EXPECTED RESULT:

ACTUAL RESULT:

BUSINESS IMPACT:
SEVERITY:
PRIORITY:
EVIDENCE:
ASSIGNEE:
STATUS:
WORKAROUND:
RETEST RESULT:
~~~

### Evaluation rubric

| Assessment area | Weight |
|---|---:|
| Test case clarity and repeatability | 20% |
| Requirement and scenario traceability | 15% |
| Positive, negative and boundary coverage | 15% |
| Expected and actual result quality | 10% |
| Defect report completeness | 15% |
| Severity, priority and lifecycle understanding | 10% |
| Acceptance validation and reporting | 15% |
| **Total** | **100%** |

## 18. Common mistakes to avoid

1. Writing vague expected results such as works correctly.
2. Omitting preconditions or test data.
3. Combining unrelated validations into one case.
4. Forgetting to link test cases to requirements.
5. Marking a blocked case as passed.
6. Recording a defect without reproduction steps.
7. Confusing severity with priority.
8. Closing a defect without retesting.
9. Retesting a fix but ignoring regression impact.
10. Treating a requirement change as a defect.
11. Using unapproved personal or production data.
12. Reporting only pass percentage without critical risk information.
13. Allowing a BA to sign off without delegated business authority.
14. Leaving open defects and acceptance conditions undocumented.

## 19. Knowledge check

**Q1. What is the main difference between a test scenario and a test case?**

A. They always mean exactly the same thing  
B. A scenario is a high-level situation; a test case contains detailed execution information  
C. A test case is only a project plan  
D. A scenario contains source code

**Answer: B.** Scenarios describe what business situation to validate; test cases explain how to execute and evaluate it.

**Q2. What should an expected result be based on?**

A. A tester's personal preference  
B. Approved requirements and acceptance criteria  
C. A random guess  
D. The colour of the application

**Answer: B.** Expected results should reflect agreed requirements and business rules.

**Q3. What is the difference between severity and priority?**

A. Severity is impact; priority is urgency of fixing  
B. Severity is the developer's name; priority is the tester's name  
C. They are always identical  
D. Priority measures screen size

**Answer: A.** Severity describes impact; priority describes how urgently the issue should be addressed.

**Q4. What is retesting?**

A. Testing unrelated features  
B. Checking whether a specific defect has been fixed  
C. Rewriting all requirements  
D. Closing every defect

**Answer: B.** Retesting repeats the failed check to verify the fix.

**Q5. What is regression testing?**

A. Checking existing behaviour for unintended effects after a change  
B. Checking only the specific fixed line of code  
C. Approving the project budget  
D. Replacing acceptance criteria

**Answer: A.** Regression testing checks for side effects in previously working behaviour.

**Q6. A test cannot proceed because the test environment is unavailable. What status is most suitable?**

A. Pass  
B. Blocked  
C. Closed  
D. Accepted

**Answer: B.** The test cannot be evaluated until the environment is available.

**Q7. Which information is most useful in a defect report?**

A. Only It failed  
B. Reproduction steps, expected result, actual result, environment and evidence  
C. Only the developer's name  
D. An unrelated screenshot

**Answer: B.** These details help the team reproduce, investigate and resolve the issue.

**Q8. Can a requirement change be treated automatically as a defect?**

A. Yes, always  
B. No; a change to agreed scope should follow change control  
C. Only if the BA is absent  
D. Only after production release

**Answer: B.** A defect is a failure to meet an agreed expectation; a new or changed expectation needs the appropriate change process.

**Q9. Why use a traceability matrix?**

A. To connect requirements, test cases and results  
B. To replace all testing  
C. To hide failed tests  
D. To assign salaries

**Answer: A.** Traceability demonstrates coverage and highlights unvalidated requirements.

**Q10. Who should authorize business acceptance?**

A. Any person who executes a test  
B. The authorized business owner or delegate  
C. The person who created the spreadsheet  
D. An automated test script

**Answer: B.** Acceptance authority should be defined by project governance.

## 20. Business Analyst interview questions and sample answers

### 1. How do you write a test case?
I start with the approved requirement and acceptance criteria. I identify the scenario, user role, preconditions and test data. Then I write clear steps and observable expected results, assign an ID and link it to the requirement. During execution, I record actual results, status and evidence.

### 2. What is the difference between expected and actual results?
Expected results describe behaviour defined by the approved requirement or acceptance criteria. Actual results describe what happened when the test was executed. Comparing them determines whether the test passed or failed.

### 3. What is a defect?
A defect is a problem where the delivered product behaves differently from an agreed requirement or expected result. A useful defect report includes reproduction steps, expected and actual behaviour, environment, business impact and evidence.

### 4. Explain severity and priority with an example.
Severity measures how much a defect affects the system or business. Priority indicates how urgently it should be fixed. An access-control defect exposing another customer's data may be critical severity and urgent priority. A minor alignment issue may have low severity and lower priority.

### 5. What happens after a developer fixes a defect?
The defect is made available for retesting. The tester repeats the original steps and checks the expected result. If it passes, the defect can be closed according to the process. Related regression tests are also performed to check that the change did not break other functionality.

### 6. How do you ensure requirements are fully tested?
I maintain traceability between requirements, acceptance criteria, scenarios and test cases. I review the matrix for requirements with no tests, tests without requirement links and critical requirements that have not been validated. I also review execution results and outstanding defects.

### 7. What would you do if the requirement is unclear during testing?
I would pause the affected validation, document the ambiguity and its impact, and consult the requirement owner or business stakeholder. I would record the agreed interpretation or change, update the requirement and acceptance criteria, and ensure related test cases are updated before proceeding.

### 8. What is acceptance validation?
Acceptance validation checks whether the solution satisfies agreed acceptance criteria and business needs. It uses test results, evidence, defect status and risk information to support a decision by the authorized business representative.

## 21. Quick revision sheet

| Term | Remember |
|---|---|
| Requirement | Business need or expected capability |
| Acceptance criterion | Condition that must be satisfied |
| Test scenario | High-level business situation |
| Test case | Detailed instructions and expected result |
| Preconditions | Conditions before execution |
| Test data | Input values and records |
| Expected result | Agreed intended behaviour |
| Actual result | Observed behaviour |
| Pass | Actual matches expected |
| Fail | Actual differs from expected |
| Blocked | Test cannot proceed |
| Defect | Product differs from agreed expectation |
| Severity | Impact of defect |
| Priority | Urgency of fixing defect |
| Triage | Review and decide defect handling |
| Retesting | Verify a specific fix |
| Regression | Check for unintended side effects |
| Traceability | Connect requirements and tests |
| Acceptance validation | Evaluate evidence against acceptance criteria |

## 22. Day 38 completion checklist

- [ ] I can distinguish a scenario from a test case.
- [ ] I can write a test case with all essential fields.
- [ ] I can write measurable expected results.
- [ ] I can design positive and negative test cases.
- [ ] I can apply equivalence partitioning and boundary value analysis.
- [ ] I can use decision tables and state transitions.
- [ ] I understand test execution statuses.
- [ ] I can write a reproducible defect report.
- [ ] I can distinguish severity from priority.
- [ ] I understand defect triage and lifecycle.
- [ ] I can explain retesting versus regression testing.
- [ ] I can map requirements to test cases and results.
- [ ] I can validate acceptance criteria using evidence.
- [ ] I have prepared the UAT Test Case Repository mini-project.

## 23. Official learning references

- ISTQB — Certified Tester Foundation Level: https://www.istqb.org/certifications/certified-tester-foundation-level
- ISTQB glossary: https://glossary.istqb.org/
- Atlassian — Bug tracking and issue management: https://www.atlassian.com/agile/project-management/bug-tracking
- Atlassian — Acceptance criteria: https://www.atlassian.com/work-management/project-management/acceptance-criteria
- Microsoft Learn — Azure Test Plans documentation: https://learn.microsoft.com/en-us/azure/devops/test/overview
- Cucumber — Behaviour-Driven Development and Gherkin: https://cucumber.io/docs/gherkin/

Use these resources for additional learning. The project's approved test strategy, defect policy and acceptance governance take precedence.

---

**Day 38 outcome:** You can turn requirements and UAT scenarios into repeatable test cases, record and track defects, distinguish severity from priority, verify fixes and support evidence-based business acceptance. Day 39 focuses on requirement reviews, stakeholder communication and sign-off.
