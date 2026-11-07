# Day 44: Capstone — UAT Plan, Test Cases and Traceability

**Phase:** 7 — End-to-end Business Analysis Capstone  
**Estimated time:** 2–3 hours  
**Difficulty:** Intermediate  
**Prerequisites:** Day 37 software testing and UAT; Day 38 test cases, expected results and defects; Day 39 requirement reviews and sign-off; Day 41 requirements specification; Day 42 process model and improvement plan; Day 43 solution prototype, data dictionary and acceptance criteria.  
**Approved independent mini-project:** **Solution validation pack**

---

## 1. Why this day matters

A prototype can look correct and a requirement document can be well written, but neither proves that a delivered solution works for business users.

User Acceptance Testing (UAT) checks whether the solution supports agreed business tasks and meets approved requirements. The Business Analyst helps translate business needs into testable scenarios, coordinate business participation, connect tests to requirements, record defects and prepare evidence for an acceptance decision.

In this lesson, continue the Customer Onboarding and Service Improvement System from Days 40–43.

A customer should be able to:
1. Start an application.
2. Enter customer details.
3. Upload required documents.
4. Review and submit the application.
5. Track its status.
6. Respond when a reviewer requests more information.

An operations reviewer should be able to:
1. Find an application requiring review.
2. Review submitted information and documents.
3. Request missing information with a clear reason.
4. Record a decision permitted by the business process.

The goal is not to test whether a button merely responds to a click. The goal is to establish whether the agreed business process works, including important alternate and failure paths.

## 2. Learning objectives

By the end of this lesson, you should be able to:

- Explain the purpose, scope and participants of UAT.
- Distinguish test strategy, test plan, test scenario, test case and test evidence.
- Prepare UAT scope, entry criteria, exit criteria, roles and schedule.
- Convert requirements and acceptance criteria into positive, negative and boundary test cases.
- Prepare realistic test data without exposing real customer information.
- Maintain requirement-to-test traceability.
- Record, classify, retest and close defects.
- Summarize test execution and support a documented business acceptance decision.

---

## 3. Words you need

| Term | Plain-English meaning | Example |
|---|---|---|
| UAT | User Acceptance Testing: business users check whether the solution supports their needs | Operations user reviews an application |
| Test strategy | High-level approach for how testing will be organized | Which test levels, methods and environments are used |
| Test plan | Project-specific document describing what will be tested, by whom, when and how | Onboarding portal UAT plan |
| Test scenario | A business situation or journey to validate | Customer submits an application |
| Test case | Detailed steps, data and expected result for a particular check | Submit with one required document missing |
| Test data | Values used during a test | Synthetic customer name and sample document |
| Test environment | A controlled system where tests are performed | UAT environment separate from production |
| Test execution | Performing a test and recording its actual result | Run UAT-04 and record Pass |
| Test evidence | Proof of what happened during execution | Screenshot, log reference or approved record |
| Defect | A difference between expected and actual behaviour | System accepts submission without a required document |
| Severity | How seriously a defect affects the system or business | Critical, high, medium or low |
| Priority | How urgently a defect should be addressed | Immediate, high, normal or low |
| Retest | Run the failed test again after a fix | Repeat UAT-04 after deployment to UAT |
| Regression testing | Check that a change has not broken previously working behaviour | Recheck upload and submission after a status fix |
| Entry criteria | Conditions required before testing can begin | Build available and test data prepared |
| Exit criteria | Conditions used to decide whether testing can finish | Critical tests passed and blockers resolved or formally accepted |
| Sign-off | Recorded acceptance or decision by an authorized stakeholder | Business owner approves release subject to agreed conditions |
| Traceability | Links requirements to test scenarios, cases and results | FR-04 → TS-03 → UAT-07 → execution evidence |

### 3.1 UAT versus other testing

| Testing type | Main question | Typical owner |
|---|---|---|
| Unit testing | Does an individual component work? | Developer |
| Integration testing | Do connected components exchange information correctly? | Developers / QA |
| System testing | Does the complete system meet technical and functional expectations? | QA / test team |
| UAT | Does the solution meet business needs and support real user tasks? | Business users, supported by BA and QA |

These activities can overlap in a delivery lifecycle, but they are not interchangeable. UAT should not be used as a substitute for basic developer and QA testing.

### 3.2 Who does what?

| Role | Typical responsibility |
|---|---|
| Business owner / sponsor | Confirms business outcomes and makes or delegates acceptance decision |
| Business users | Execute realistic business scenarios and judge usability and process fit |
| Business Analyst | Clarifies requirements, prepares scenarios, supports execution, analyzes gaps and maintains traceability |
| QA / test lead | Coordinates test approach, execution discipline, defect workflow and reporting |
| Developer | Investigates and fixes technical defects |
| Product owner | Clarifies priorities and scope decisions |
| Project manager / delivery lead | Coordinates schedule, dependencies and resources |
| Environment / support team | Maintains test environment, access and relevant test data |

The BA facilitates evidence-based decisions. The BA should not approve on behalf of a business owner unless that authority has explicitly been delegated.

---

## 4. UAT planning: decide what success means

A UAT plan makes the testing activity understandable and repeatable.

### 4.1 Purpose and objectives

Example purpose:

> Confirm that the Customer Onboarding Portal supports the approved customer and operations workflows, captures required information, handles document submission correctly and displays application status according to approved business rules.

Possible objectives:

- Verify critical customer journeys.
- Verify reviewer actions and status changes.
- Confirm required fields and business validations.
- Confirm important error and alternate paths.
- Confirm role-based access expectations.
- Record defects and outstanding risks.
- Provide evidence for a business acceptance decision.

### 4.2 Define scope

**In scope — example**

- Customer starts an application.
- Customer enters required details.
- Customer uploads approved document types.
- Customer reviews and submits.
- Customer sees permitted application status.
- Reviewer views assigned application information.
- Reviewer requests missing information.
- Customer responds to an information request.
- Key validation and access-control behaviours are checked.

**Out of scope — example unless separately approved**

- Real payment processing.
- Production identity verification.
- External government or banking integrations.
- Load and performance certification.
- Full security penetration testing.
- Actual production data migration.

Out-of-scope does not mean unimportant. It means the item is not covered by this particular UAT pack and must have another owner or validation activity where necessary.

### 4.3 Entry criteria

Testing should begin only when the agreed readiness conditions are met.

Example entry checklist:

- [ ] Approved requirements and acceptance criteria are available.
- [ ] UAT build is deployed to the agreed environment.
- [ ] Required user roles and test accounts are available.
- [ ] Test data is prepared and approved.
- [ ] Main workflows are available for execution.
- [ ] Known critical defects are resolved or explicitly assessed.
- [ ] Test cases have been reviewed.
- [ ] Business users know their responsibilities and schedule.
- [ ] Defect reporting channel is agreed.
- [ ] Environment limitations are documented.

A project may define additional entry conditions. Do not start simply because a calendar invitation exists.

### 4.4 Exit criteria

Exit criteria define what evidence is needed before UAT can be considered complete.

Example:

- All planned critical business scenarios have been executed.
- All critical and high-priority tests have a recorded result.
- No unresolved defect violates an agreed release-blocking condition.
- Failed tests have linked defects and owners.
- Fixed defects have been retested.
- Relevant regression tests have been run.
- Deferred defects have documented impact, workaround, owner and approval.
- Business owner has reviewed the summary and made an acceptance decision.

Do not automatically set “100% of every test passed” as the only exit rule. A test may be blocked by an environment issue, or a lower-impact defect may be accepted with a documented decision. The organization must approve the actual exit criteria.

### 4.5 Test environment

A UAT environment should be controlled and separate from production.

Record:

| Item | Example entry |
|---|---|
| Environment | Onboarding UAT |
| Build/version | Record actual deployed version |
| URL | Approved internal UAT address |
| Browser/device | Agreed supported browser and device |
| User roles | Customer, Operations Reviewer |
| Test data | Synthetic customer and application records |
| Integrations | Mocked or test endpoints, as approved |
| Known limitations | List current restrictions |
| Support contact | Named team or approved support channel |

Never invent a real environment URL or use production credentials in a learning exercise.

### 4.6 UAT schedule example

| Activity | Example duration | Owner |
|---|---:|---|
| Readiness review | 30 minutes | BA / QA / delivery lead |
| Tester briefing | 30 minutes | BA / QA |
| Customer journey execution | 1–2 hours | Business users |
| Reviewer journey execution | 1 hour | Operations users |
| Defect triage | 30 minutes daily | BA / QA / development |
| Retest and regression | Based on fixes | Business users / QA |
| Results review | 30–60 minutes | Business owner and team |
| Acceptance decision | Agreed meeting | Authorized business owner |

The schedule is illustrative. Use actual availability, complexity and project commitments.

---

## 5. Convert requirements into test scenarios

A test scenario describes a business journey or condition. It is broader than an individual test case.

### 5.1 Scenario inventory

| Scenario ID | Scenario | User role | Related requirement |
|---|---|---|---|
| TS-01 | Customer starts a new application | Customer | FR-02 |
| TS-02 | Customer saves and resumes a draft | Customer | FR-03 |
| TS-03 | Customer uploads required documents | Customer | FR-04 |
| TS-04 | Customer submits a complete application | Customer | FR-05 |
| TS-05 | Customer attempts submission with missing information | Customer | FR-03, FR-04, FR-05 |
| TS-06 | Customer tracks application status | Customer | FR-06 |
| TS-07 | Reviewer requests additional information | Reviewer | FR-08 |
| TS-08 | Customer responds to an information request | Customer | FR-06, FR-08 |
| TS-09 | Unauthorized user attempts to view an application | Unauthorized user | Access requirement |
| TS-10 | User experiences an upload or network failure | Customer | FR-04 |

### 5.2 Scenario versus test case

Scenario:

> Customer submits a complete application.

Test cases derived from it:

- Submit with all required details and documents.
- Submit with one required document missing.
- Submit after a required field becomes invalid.
- Double-click Submit.
- Lose network connection during submission.
- Refresh the page after successful submission.

One scenario can produce many test cases because different conditions may change the outcome.

### 5.3 Positive, negative and boundary testing

| Test category | Meaning | Example |
|---|---|---|
| Positive | Valid input and expected successful action | Submit a complete application |
| Negative | Invalid input or prohibited action | Submit without a required document |
| Boundary | Values at or near an allowed limit | Enter a name at the maximum permitted length |
| Alternate path | A valid but different business route | Reviewer requests more information |
| Permission | Check whether a role can perform an action | Customer attempts to open another customer's record |
| Recovery | Check behaviour after interruption | Retry an upload after network failure |

A strong UAT pack includes more than happy-path tests.

---

## 6. Write detailed test cases

A test case should be repeatable by another tester who has not written it.

### 6.1 Standard test case fields

| Field | What to record |
|---|---|
| Test case ID | Unique identifier such as UAT-001 |
| Test title | Short description of what is verified |
| Requirement ID | Source requirement |
| Scenario ID | Parent business scenario |
| Preconditions | State that must exist before execution |
| Test data | Specific synthetic values or data reference |
| Steps | Ordered actions |
| Expected result | Observable result for each important action |
| Actual result | What happened during execution |
| Status | Not Run, Pass, Fail, Blocked or Not Applicable |
| Evidence | Screenshot, log or record reference |
| Defect ID | Linked defect if the test fails |
| Tester and date | Who executed it and when |

### 6.2 Test case example: successful application submission

**Test Case ID:** UAT-004  
**Title:** Customer submits a complete application  
**Requirement:** FR-05  
**Scenario:** TS-04

**Preconditions**
- Customer is signed in to the UAT environment.
- Customer has a saved application.
- Required customer details are valid.
- All required documents are uploaded successfully.
- Test application is in a state that permits submission.

**Test data**
- Use a synthetic customer record.
- Use approved sample documents.
- Use a unique test application reference.

**Steps and expected results**

| Step | Action | Expected result |
|---:|---|---|
| 1 | Open the saved application | Correct application details appear |
| 2 | Navigate to Review and Submit | Summary and required information appear |
| 3 | Check details and documents | Values and document statuses are correct |
| 4 | Select Submit | Submission is processed once |
| 5 | View confirmation | Confirmation and application reference appear |
| 6 | Open Application Tracking | Current permitted status appears |

**Actual result:** Record during execution.  
**Status:** Not Run until tested.  
**Evidence:** Record approved evidence location or reference.

### 6.3 Test case example: missing document

**Test Case ID:** UAT-005  
**Title:** Customer cannot submit when a required document is missing  
**Requirement:** FR-04, FR-05  
**Scenario:** TS-05

**Preconditions**
- Customer is signed in.
- Application contains valid customer details.
- One required document has not been uploaded.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Open Review and Submit | Missing required document is identified |
| 2 | Select Submit | Submission is prevented |
| 3 | Review the message | User is told which document is missing |
| 4 | Navigate to Document Upload | Customer can provide the missing document |
| 5 | Upload the required document successfully | Document status changes to uploaded |
| 6 | Return to Review and Submit | Application can proceed if all other conditions are satisfied |

### 6.4 Test case example: role access

**Test Case ID:** UAT-009  
**Title:** Customer cannot view another customer's application  
**Requirement:** Access-control requirement  
**Scenario:** TS-09

**Preconditions**
- Customer A and Customer B are separate synthetic test accounts.
- Each account has an application.
- Tester is signed in as Customer A.

| Step | Action | Expected result |
|---:|---|---|
| 1 | Open Customer A's application | Customer A's permitted record is displayed |
| 2 | Attempt to open Customer B's application using an unauthorized reference or route | Access is denied according to the approved design |
| 3 | Return to Customer A's dashboard | Customer A's permitted data remains available |

Do not expose sensitive details in the error message. Confirm the exact expected access-denial behaviour with security and product stakeholders.

---

## 7. Test data preparation

Good tests need controlled, relevant data. Poor test data can create false failures or hide real defects.

### 7.1 Use synthetic data

Example:

| Test record | Customer name | Email | Application status |
|---|---|---|---|
| CUST-T001 | Test Customer One | test.one@example.invalid | Draft |
| CUST-T002 | Test Customer Two | test.two@example.invalid | Submitted |
| CUST-T003 | Test Customer Three | test.three@example.invalid | Action Required |

The .invalid domain is reserved for invalid example addresses and should not be treated as a deliverable email address.

Use synthetic documents created for testing. Do not upload actual identity documents, bank statements or other personal records into a public learning repository.

### 7.2 Data coverage matrix

| Data condition | Example test |
|---|---|
| All required fields populated | Complete application |
| Required field blank | Missing full name |
| Invalid format | Invalid email structure |
| Maximum allowed length | Longest permitted field value |
| Disallowed file type | Upload an unsupported file |
| File exceeds configured limit | Upload a file above approved limit |
| Duplicate submission attempt | Select Submit twice |
| Missing document | Leave one required item absent |
| Different application statuses | Draft, Submitted, Action Required |
| Unauthorized account | Attempt to view another customer's application |

The exact limits and allowed values must come from approved requirements or configuration, not assumptions.

### 7.3 Test data management rules

- Use approved synthetic data.
- Keep data separate from production.
- Avoid real names, phone numbers, identity numbers and account details.
- Do not reuse sensitive data from screenshots or support tickets.
- Record which test data supports which test case.
- Reset or clean up data according to environment rules.
- Avoid shared accounts that make test ownership unclear.
- Protect credentials and access tokens.
- Record test data limitations.

---

## 8. Requirement traceability matrix

Traceability connects the original requirement to validation evidence.

### 8.1 Forward and backward traceability

**Forward traceability:** Start from a requirement and find the scenarios, test cases and results that verify it.

**Backward traceability:** Start from a test case or design element and identify the requirement that justifies it.

Both help identify:
- Requirements that have not been tested.
- Tests that do not support an approved requirement.
- Requirements whose tests failed.
- Changes that require additional test coverage.

### 8.2 Example traceability matrix

| Requirement | Scenario | Test case | Expected coverage |
|---|---|---|---|
| FR-02 Start application | TS-01 | UAT-001 | Customer can start application |
| FR-03 Enter details | TS-02 | UAT-002, UAT-003 | Valid and invalid details |
| FR-04 Upload documents | TS-03, TS-10 | UAT-006, UAT-007 | Successful and failed upload |
| FR-05 Submit application | TS-04, TS-05 | UAT-004, UAT-005 | Complete and incomplete submission |
| FR-06 Track status | TS-06, TS-08 | UAT-008, UAT-010 | Status display and action required |
| FR-08 Reviewer request | TS-07 | UAT-011 | Reviewer requests missing information |
| Access requirement | TS-09 | UAT-009 | Unauthorized access denied |

Use the actual approved requirement IDs from Day 41. The IDs above are illustrative and must be reconciled with the capstone's current specification.

### 8.3 Coverage calculation

A simple requirement coverage measure is:

\[
\text{Requirement coverage} =
\frac{\text{Requirements with at least one mapped test}}
{\text{Total in-scope testable requirements}}
\times 100
\]

Example:
- In-scope testable requirements = 20.
- Requirements mapped to at least one test = 18.

\[
\frac{18}{20}\times100=90\%
\]

This is mapping coverage, not proof that the requirements passed. Report execution and pass rates separately.

### 8.4 Test execution measures

| Measure | Formula | What it tells you |
|---|---|---|
| Execution progress | Executed tests ÷ planned tests × 100 | How much planned testing has been run |
| Pass rate | Passed tests ÷ executed tests × 100 | Share of executed tests that passed |
| Fail rate | Failed tests ÷ executed tests × 100 | Share of executed tests that failed |
| Blocked rate | Blocked tests ÷ planned tests × 100 | Share unable to run |
| Open defect count | Count of defects not closed | Remaining known issues |

Always state the denominator and reporting date. Excluding blocked or not-run tests can change the interpretation of a percentage.

---

## 9. Execute tests and record evidence

A test case is not complete because it was written. It must be executed in the agreed environment and its result recorded.

### 9.1 Execution workflow

~~~text
Confirm environment and test data
             |
             v
Check preconditions
             |
             v
Perform test steps
             |
             v
Compare actual with expected
             |
       +-----+-----+
       |           |
      Match      Mismatch
       |           |
       v           v
     PASS        FAIL
                   |
                   v
             Record defect
                   |
                   v
             Fix and deploy
                   |
                   v
                Retest
                   |
             +-----+-----+
             |           |
           Pass        Fail
             |           |
             v           v
           Close     Reopen / investigate
~~~

### 9.2 Execution status definitions

| Status | Meaning |
|---|---|
| Not Run | Test has not been executed |
| Pass | Actual result meets expected result |
| Fail | Actual result does not meet expected result |
| Blocked | Test cannot proceed because of a dependency or environment issue |
| Not Applicable | Test is not relevant to the agreed scope, with a reason recorded |

Do not mark a test Pass because the tester expects it to work. Compare actual behaviour with the expected result.

### 9.3 Evidence quality

Useful evidence may include:
- Screenshot showing the relevant result.
- Application or transaction reference.
- Timestamp and environment/build version.
- Relevant application log reference, where access is authorized.
- Defect ID and linked test case.
- Tester name or role.

Evidence should:
- Prove the result without unnecessary personal data.
- Be linked to a test case.
- Be captured from the correct environment.
- Include enough context to understand the outcome.
- Follow the organization's storage and retention rules.

A screenshot alone may not prove a backend event or data persistence. Use appropriate system evidence where required.

---

## 10. Defect management during UAT

A defect is a mismatch between expected and actual behaviour. A good defect report helps the team reproduce, understand, prioritize and fix the issue.

### 10.1 Defect report template

| Field | Example |
|---|---|
| Defect ID | DEF-001 |
| Summary | Application can be submitted without required document |
| Related requirement | FR-04 / FR-05 |
| Test case | UAT-005 |
| Environment/build | Record actual UAT build |
| Preconditions | Customer has valid details and one required document missing |
| Steps to reproduce | Open review page; select Submit |
| Expected result | Submission is prevented and missing document is identified |
| Actual result | Application is submitted |
| Severity | High or critical, based on agreed impact |
| Priority | Set by triage team |
| Evidence | Approved screenshot/log reference |
| Owner | Assigned development team |
| Status | New |

### 10.2 Severity versus priority

**Severity** describes the impact of the defect.

**Priority** describes how urgently the team should address it.

| Example | Possible severity | Possible priority |
|---|---|---|
| Customer can access another customer's record | Critical | Immediate |
| Required document rule is bypassed | High | High |
| Minor text alignment issue | Low | Low |
| Rare report formatting issue before a major reporting deadline | Medium | High |

These are examples. The project should define its own severity and priority scales.

### 10.3 Defect lifecycle

~~~text
New
 |
 v
Triaged
 |
 +-------> Rejected / Duplicate / Deferred
 |
 v
Assigned
 |
 v
In Progress
 |
 v
Fixed
 |
 v
Ready for Retest
 |
 +-------> Retest Failed -> Reopened
 |
 v
Retest Passed
 |
 v
Closed
~~~

A defect may have a different workflow in Jira or another tracking tool. Follow the project's configured workflow.

### 10.4 Defect triage questions

- Can the issue be reproduced?
- Which requirement and test case are affected?
- Is it a product defect, test-data issue or environment issue?
- How many users or business processes are affected?
- Is there a workaround?
- Does it create financial, privacy, security or compliance risk?
- Does it block a critical business journey?
- What is the release impact?
- Who owns the decision to fix, defer or accept the risk?

### 10.5 Retest and regression

- **Retest:** repeat the failed test to confirm the reported defect is fixed.
- **Regression:** run related previously passing tests to check that the change did not break other behaviour.

Example: A fix changes application submission validation. Retest the missing-document scenario and run regression tests for valid submission, draft saving and application tracking where relevant.

---

## 11. UAT results and reporting

A useful report tells stakeholders what was tested, what passed, what failed, what remains uncertain and what decision is needed.

### 11.1 Example execution summary

Suppose a test cycle contains:
- 20 planned test cases.
- 15 passed.
- 3 failed.
- 1 blocked.
- 1 not run.

Execution progress:

\[
\frac{19}{20}\times100=95\%
\]

Pass rate among executed tests:

\[
\frac{15}{19}\times100\approx78.95\%
\]

Fail rate among executed tests:

\[
\frac{3}{19}\times100\approx15.79\%
\]

Blocked rate against planned tests:

\[
\frac{1}{20}\times100=5\%
\]

Do not say “95% passed.” The execution progress is 95%; the pass rate among executed tests is approximately 78.95%.

### 11.2 Sample UAT summary table

| Metric | Count |
|---|---:|
| Planned | 20 |
| Passed | 15 |
| Failed | 3 |
| Blocked | 1 |
| Not run | 1 |
| Executed | 19 |
| Open defects | 3, if all three failures created open defects |

These values are a worked example, not actual project results.

### 11.3 Management report structure

A concise UAT report should include:

1. Project and release/build identifier.
2. Test cycle dates and environment.
3. Scope tested and exclusions.
4. Test cases planned and executed.
5. Pass, fail, blocked and not-run counts.
6. Requirement coverage.
7. Open defects by severity and priority.
8. Critical business journeys not yet validated.
9. Known limitations and accepted risks.
10. Recommendation and decision required.
11. Evidence and defect log references.

### 11.4 Recommendation language

Avoid statements such as:

> Everything is perfect. The project is ready.

Use evidence-based wording:

> UAT execution is complete for the agreed scope. The critical customer submission journey passed in the tested build. Two medium-priority defects remain open and have documented workarounds. The business owner should review the residual risks and decide whether the release can be accepted under the agreed exit criteria.

A BA can recommend; the authorized decision-maker accepts or rejects the release.

---

## 12. Sign-off and acceptance decision

Sign-off is a recorded decision, not simply a meeting or verbal “looks good.”

### 12.1 Possible decision outcomes

| Decision | Meaning |
|---|---|
| Accepted | Agreed acceptance conditions are met |
| Accepted with conditions | Release may proceed with explicitly documented conditions and owners |
| Rejected / Not accepted | Significant issues prevent acceptance |
| Deferred | Decision postponed pending evidence, fixes or stakeholder review |

The exact labels and authority must follow project governance.

### 12.2 Sign-off record template

~~~text
PROJECT: Customer Onboarding and Service Improvement System
RELEASE / BUILD: [Record actual build]
UAT CYCLE: [Start date] to [End date]
ENVIRONMENT: [Approved UAT environment]

SCOPE TESTED:
[List the business journeys tested]

SUMMARY:
Planned:
Passed:
Failed:
Blocked:
Not run:
Open defects by severity:

KNOWN LIMITATIONS:
[List limitations and impact]

ACCEPTANCE DECISION:
[Accepted / Accepted with conditions / Not accepted / Deferred]

CONDITIONS OR EXCEPTIONS:
[List condition, owner and due date]

DECISION OWNER:
[Name or approved role]

DECISION DATE:
[Date]

EVIDENCE LOCATION:
[Approved evidence reference]
~~~

Do not invent names, signatures or approvals. Leave fields pending until the authorized person provides the decision.

---

## 13. Tool workflow: organize UAT in a spreadsheet

A spreadsheet is sufficient for a small learning project. Larger teams may use Jira, Azure DevOps or a dedicated test-management tool.

### 13.1 Create workbook tabs

Create a workbook called Solution_Validation_Pack.xlsx with these tabs:

1. UAT_Plan
2. Test_Scenarios
3. Test_Cases
4. Test_Execution
5. Defect_Log
6. Traceability
7. UAT_Summary
8. Signoff

### 13.2 Suggested Test_Cases columns

| Column | Example |
|---|---|
| Test_Case_ID | UAT-001 |
| Requirement_ID | FR-02 |
| Scenario_ID | TS-01 |
| Title | Start a new application |
| Preconditions | Customer is signed in |
| Test_Data_ID | DATASET-01 |
| Steps | Open dashboard; select Start |
| Expected_Result | New application is created |
| Priority | High |
| Status | Not Run |
| Defect_ID | Blank until needed |
| Evidence_Reference | Blank until executed |

### 13.3 Use controlled status values

Use a consistent list:
- Not Run
- Pass
- Fail
- Blocked
- Not Applicable

Do not use a mixture such as “Done”, “Okay”, “Success”, “Passed” and “Completed” for the same status.

### 13.4 Useful spreadsheet formulas

Assume the Status column in Test_Execution is J, rows 2 to 101.

Count passed tests:

~~~excel
=COUNTIF(J2:J101,"Pass")
~~~

Count failed tests:

~~~excel
=COUNTIF(J2:J101,"Fail")
~~~

Count blocked tests:

~~~excel
=COUNTIF(J2:J101,"Blocked")
~~~

Count not-run tests:

~~~excel
=COUNTIF(J2:J101,"Not Run")
~~~

Count executed tests (Pass + Fail):

~~~excel
=COUNTIF(J2:J101,"Pass")+COUNTIF(J2:J101,"Fail")
~~~

Pass rate among executed tests:

~~~excel
=IFERROR(COUNTIF(J2:J101,"Pass")/(COUNTIF(J2:J101,"Pass")+COUNTIF(J2:J101,"Fail")),0)
~~~

Format the pass-rate cell as a percentage. If your sheet uses another column, update the range.

**Important:** Decide how Blocked and Not Applicable cases are treated in each metric. State the definition in the report so readers can interpret it correctly.

### 13.5 Basic spreadsheet quality checks

- Use unique IDs.
- Freeze the header row.
- Enable filters.
- Use data validation for status and priority.
- Avoid merged cells in data tables.
- Keep one test case per row.
- Do not put multiple unrelated requirements into one cell if they need separate traceability.
- Protect formula cells if appropriate.
- Use a separate evidence reference rather than embedding confidential evidence in an uncontrolled workbook.

---

## 14. Worked example: one requirement through UAT

Requirement FR-06:

> The customer can view the current permitted status of their application.

**Step 1 — Clarify the rule**

Questions:
- Which statuses are visible to customers?
- Are internal review notes hidden?
- How quickly should status changes appear?
- What should happen if no application exists?
- What happens when a reviewer requests more information?

**Step 2 — Identify the scenario**

TS-06: Customer tracks application status.

**Step 3 — Derive test cases**

- UAT-008A: Customer views a submitted application.
- UAT-008B: Customer views an application in Action Required state.
- UAT-008C: Customer has no applications.
- UAT-008D: Customer attempts to view another customer's application.

**Step 4 — Define expected outcomes**

- The correct permitted status appears.
- The customer sees the next action when information is required.
- The empty state explains how to start an application.
- Unauthorized access is denied according to the approved design.

**Step 5 — Prepare test data**

Create synthetic records with each required status and distinct customer ownership.

**Step 6 — Execute and record**

Run each case in the agreed UAT build. Record actual results and evidence. Create a defect if actual behaviour differs from the expected result.

**Step 7 — Update traceability**

Link FR-06 → TS-06 → UAT-008A to UAT-008D → execution result and evidence.

**Step 8 — Report**

If one status is not displayed correctly, report the exact affected case and business impact. Do not mark the entire requirement as passed merely because another status worked.

---

## 15. Common mistakes and fixes

| Mistake | Why it is a problem | Better approach |
|---|---|---|
| Treating UAT as a demo | A demo may avoid failure paths and test evidence | Use repeatable test cases and record results |
| Testing only happy paths | Business risks remain undiscovered | Include negative, boundary, alternate and permission tests |
| Writing vague steps | Another tester cannot repeat the case | Use numbered actions and specific data |
| Expected result says “works” | It is not objectively verifiable | Describe the observable outcome |
| Using real customer information | Creates privacy and security risk | Use approved synthetic data |
| Starting without entry criteria | Environment or build problems waste time | Complete a readiness review |
| Marking blocked as passed | Hides incomplete validation | Keep separate statuses |
| Confusing execution progress with pass rate | Misleads decision-makers | Show formulas and denominators |
| Reporting a defect without reproduction steps | Developers may not reproduce it | Include preconditions, steps, actual and expected results |
| Closing a defect without retest | The fix may not work | Retest and record evidence |
| Skipping regression | A fix may break other features | Identify and run related regression tests |
| Treating severity and priority as identical | Impact and urgency are different | Record both and agree triage |
| Signing off without residual-risk review | Unresolved issues become invisible | Document exceptions and authorized decisions |
| Claiming a prototype is UAT evidence | A prototype does not prove production behaviour | Execute against the agreed test build |

---

## 16. Industry scenario exercise

A business user tests the onboarding portal and reports:

> “I uploaded the required document. The screen showed success, but after returning to the application the document is missing.”

### Your tasks

1. Identify the likely requirement and scenario affected.
2. Write reproducible preconditions.
3. Write numbered steps.
4. State the expected result.
5. State the actual result using only observed facts.
6. Suggest evidence to collect.
7. Classify the issue provisionally and explain what information is needed before final severity and priority are assigned.
8. Identify a retest and one regression test.

### Example analysis

- Likely requirement: document upload and persistence.
- Scenario: customer uploads required documents.
- Expected: uploaded document remains associated with the correct application and is shown with the approved status.
- Actual: upload success was displayed, but the document was absent after navigation.
- Evidence: test account reference, application reference, environment/build, timestamp, screenshot of upload confirmation and subsequent missing-document view.
- Retest: upload the same approved synthetic file after the fix and navigate away and back.
- Regression: verify the submission rule still blocks an application when a required document is genuinely absent.

Do not assert the cause. It could involve persistence, display refresh, a delayed process or test setup. Investigation is needed.

---

## 17. Independent mini-project: Solution validation pack

**Approved title:** Solution validation pack

### 17.1 Objective

Prepare a complete, reviewable UAT pack for the Customer Onboarding and Service Improvement System using the requirements, workflows, prototype and acceptance criteria from Days 40–43.

You are preparing the plan and test artifacts. Unless you have an approved UAT environment, do not claim that tests were executed or passed.

### 17.2 Required deliverables

Create this folder:

~~~text
day_44_solution_validation_pack/
|
|-- README.md
|-- uat_plan.md
|-- test_scenarios.csv
|-- test_cases.csv
|-- test_execution.csv
|-- test_data_catalog.csv
|-- defect_log.csv
|-- traceability_matrix.csv
|-- uat_summary.md
|-- signoff_record.md
|-- evidence/
    |-- README.md
~~~

### 17.3 Task A — UAT plan

Include:
- Purpose and objectives.
- Scope and exclusions.
- User roles.
- Environment requirements.
- Entry criteria.
- Exit criteria.
- Schedule.
- Responsibilities.
- Defect workflow.
- Evidence rules.
- Risks and assumptions.

### 17.4 Task B — Test scenarios

Create at least eight business scenarios covering:
- Starting an application.
- Entering and saving details.
- Uploading documents.
- Submitting a complete application.
- Attempting an incomplete submission.
- Tracking application status.
- Reviewer requesting additional information.
- Customer responding to an information request.

Add at least one access-control or recovery scenario.

### 17.5 Task C — Test cases

Create at least 12 detailed test cases.

Every test case must contain:
- Unique ID.
- Requirement and scenario IDs.
- Title.
- Preconditions.
- Synthetic test data.
- Numbered steps.
- Expected results.
- Priority.
- Initial status of Not Run.

Include positive, negative, boundary, alternate and permission coverage.

### 17.6 Task D — Test data catalog

Create at least five synthetic test records. Include:
- Test data ID.
- Purpose.
- User role.
- Application state.
- Relevant data condition.
- Which test cases use it.
- Reset or cleanup note.

Never include real customer data or credentials.

### 17.7 Task E — Traceability matrix

Map each in-scope functional requirement to:
- Test scenario.
- Test case.
- Acceptance criterion.
- Execution result field.
- Evidence reference field.

Identify any requirement without coverage and explain whether it is out of scope, blocked or still needs a test.

### 17.8 Task F — Defect log

Create at least two sample defect records as **training examples**, clearly marked as hypothetical and not actual product defects.

Each should include:
- Defect ID.
- Summary.
- Requirement and test case.
- Preconditions and reproduction steps.
- Expected and actual result.
- Provisional severity and priority.
- Owner role.
- Status.
- Evidence reference.

### 17.9 Task G — UAT summary and sign-off

Create:
- A blank results dashboard or a clearly labelled sample with hypothetical values.
- Metric definitions and formulas.
- Open issue summary.
- Known limitations.
- Recommendation template.
- Sign-off record with decision fields left pending.

Do not fabricate actual execution, defect closure or business approval.

### 17.10 Implementation order

| Order | Task | Output |
|---:|---|---|
| 1 | Review Days 41–43 | Source requirement, workflow and prototype IDs |
| 2 | Define UAT purpose and scope | uat_plan.md |
| 3 | Define business scenarios | test_scenarios.csv |
| 4 | Write detailed test cases | test_cases.csv |
| 5 | Prepare synthetic data | test_data_catalog.csv |
| 6 | Map requirements to tests | traceability_matrix.csv |
| 7 | Prepare defect workflow and sample records | defect_log.csv |
| 8 | Prepare execution tracker | test_execution.csv |
| 9 | Prepare reporting and sign-off templates | uat_summary.md, signoff_record.md |
| 10 | Review completeness and consistency | README.md and evidence instructions |

### 17.11 Expected results

Your pack should make it possible for another person to understand:
- What business outcomes are being validated.
- Which user journeys are in scope.
- Who performs each test.
- Which environment and data are needed.
- Exactly how each test is performed.
- What result is expected.
- Which requirement each test verifies.
- How failures are recorded and retested.
- What evidence is needed for acceptance.

### 17.12 Validation checklist

- [ ] UAT purpose, scope and exclusions are clear.
- [ ] Entry and exit criteria are documented.
- [ ] Roles and responsibilities are identified.
- [ ] At least eight scenarios are documented.
- [ ] At least 12 detailed test cases are documented.
- [ ] Positive, negative, boundary and alternate paths are covered.
- [ ] Synthetic test data is documented.
- [ ] Each test case has expected results.
- [ ] Every in-scope testable requirement has mapped coverage or a documented gap.
- [ ] Execution statuses use controlled values.
- [ ] Defect records contain reproducible steps.
- [ ] Retest and regression approach is documented.
- [ ] Metrics distinguish execution progress from pass rate.
- [ ] Sample values are labelled hypothetical.
- [ ] Sign-off is pending until an authorized decision is recorded.
- [ ] No real personal data or credentials are included.

### 17.13 Stuck ladder

1. Re-read Day 37 for UAT purpose and roles.
2. Re-read Day 38 for test case and defect structure.
3. Re-read Day 39 for review and sign-off.
4. Use the scenario inventory in Section 5.1.
5. Copy the detailed test case structure from Section 6.
6. Use the traceability matrix in Section 8.2.
7. Start with the six customer journey steps and add alternate paths only after the main flow is covered.

### 17.14 Self-review rubric

| Dimension | Marks |
|---|---:|
| UAT plan and readiness criteria | 15 |
| Scenario coverage | 15 |
| Test case quality and repeatability | 20 |
| Test data and privacy | 10 |
| Requirement traceability | 15 |
| Defect and retest process | 10 |
| Reporting and sign-off readiness | 10 |
| Organization and evidence | 5 |
| **Total** | **100** |

Suggested interpretation:
- 90–100: complete and consistent validation pack.
- 75–89: good coverage; resolve traceability or edge-case gaps.
- 60–74: basic plan exists; improve repeatability and evidence.
- Below 60: revisit requirements and test design before presenting the pack.

---

## 18. Knowledge check

Attempt each question before reviewing the answers.

**Q1.** What is the main purpose of UAT?

A. To prove that source code follows a style guide  
B. To confirm that the solution supports agreed business needs  
C. To create the project budget  
D. To replace all developer testing

**Q2.** Which item is an entry criterion?

A. All test cases have already passed  
B. The UAT build and required test accounts are available  
C. The business owner has signed final acceptance  
D. All future enhancements are complete

**Q3.** What is the difference between a test scenario and a test case?

A. They mean exactly the same thing  
B. A scenario describes a business situation; a test case gives detailed steps and expected results  
C. A test case is always a diagram  
D. A scenario is only used by developers

**Q4.** A test could not run because the UAT environment was unavailable. What is the most accurate status?

A. Pass  
B. Fail  
C. Blocked  
D. Closed

**Q5.** What does retesting verify?

A. Whether a reported defect has been fixed  
B. Whether the project has enough budget  
C. Whether a new user story is approved  
D. Whether all users like the interface

### Answer key and explanations

1. **B** — UAT focuses on business suitability and agreed requirements.
2. **B** — A usable environment and test accounts are readiness conditions.
3. **B** — A scenario is a broader business journey; a case makes a particular check repeatable.
4. **C** — The test could not be executed due to a dependency, so it is blocked rather than passed or failed.
5. **A** — Retesting repeats the failed check after a fix. Regression checks related existing behaviour.

---

## 19. Business Analyst interview preparation

### Question 1: What is UAT and what is the BA's role?

**Answer:** UAT is testing performed by business users to confirm that a solution supports approved business needs. The BA helps clarify requirements, prepare business scenarios and acceptance criteria, support test data preparation, maintain traceability, facilitate execution, analyze defects and prepare results for the business acceptance decision.

**Example:** For an onboarding portal, the BA helps business users test a complete customer submission and a reviewer request for missing information.

**Follow-up:** Who owns the final acceptance decision?

**Answer:** The authorized business owner or delegated approver, according to project governance. The BA provides analysis and recommendation but should not assume approval authority.

### Question 2: What is the difference between a test scenario and a test case?

**Answer:** A test scenario describes a business situation to validate. A test case describes exact preconditions, data, steps and expected results for a particular check.

**Example:** “Customer submits an application” is a scenario. “Submit with one required document missing and verify that submission is blocked” is a test case.

**Follow-up:** Can one scenario have multiple test cases?

**Answer:** Yes. Different input conditions, roles and alternate paths can require separate cases.

### Question 3: How do you ensure requirements are fully tested?

**Answer:** I maintain a traceability matrix that maps each in-scope requirement to acceptance criteria, scenarios, test cases and execution evidence. I review uncovered requirements, failed tests and blocked cases before reporting coverage.

**Follow-up:** Does 100% requirement mapping mean the solution is accepted?

**Answer:** No. Mapping shows that requirements have test coverage. Execution results, defect impact, exit criteria and business approval are still needed.

### Question 4: How do you handle a defect found during UAT?

**Answer:** I help the tester record reproducible steps, expected and actual results, environment, evidence and related requirement. The team triages impact and urgency, assigns an owner, fixes the issue and performs retesting and relevant regression testing.

**Follow-up:** What if the developer says the behaviour is expected?

**Answer:** I return to the approved requirement and acceptance criteria, clarify the intended business rule with the owner and record the decision. If the requirement changes, it must follow change control rather than being silently reinterpreted.

### Question 5: What is the difference between severity and priority?

**Answer:** Severity describes the impact of the defect. Priority describes how urgently it should be addressed. A defect may have high business impact but a different delivery priority depending on the release context and agreed risk.

**Follow-up:** Who decides priority?

**Answer:** It is normally agreed through the project's defect triage process with product, business, QA and delivery stakeholders.

---

## 20. Quick revision sheet

| Concept | Remember |
|---|---|
| UAT | Business validation of the solution |
| Test plan | What, who, when, where and how |
| Test scenario | Business situation to validate |
| Test case | Preconditions, data, steps and expected result |
| Entry criteria | Conditions required to start |
| Exit criteria | Conditions required to finish |
| Test data | Controlled values used during testing |
| Evidence | Proof of actual execution |
| Pass | Actual matches expected |
| Fail | Actual differs from expected |
| Blocked | Test cannot proceed |
| Defect | Confirmed mismatch or issue |
| Severity | Impact |
| Priority | Urgency |
| Retest | Verify the fix |
| Regression | Check related behaviour remains correct |
| Traceability | Requirement → scenario → case → result |
| Sign-off | Recorded decision by authorized stakeholder |

**Five questions before declaring UAT complete:**

1. Have all critical business journeys been executed?
2. Are failures and blocked tests visible?
3. Are open defects understood and assigned?
4. Is the evidence linked to the relevant requirements?
5. Has the authorized business owner made and recorded the acceptance decision?

---

## 21. References and further learning

- ISTQB Foundation Level resources: https://www.istqb.org/
- IIBA — International Institute of Business Analysis: https://www.iiba.org/
- Atlassian — Testing and issue tracking guidance: https://www.atlassian.com/software/jira
- Microsoft Learn — Azure Test Plans documentation: https://learn.microsoft.com/en-us/azure/devops/test/overview
- OWASP Application Security Verification Standard: https://owasp.org/www-project-application-security-verification-standard/

Use the actual project's testing standards, defect workflow, security policy and approval process where they differ from these examples.

---

## 22. Day 44 completion checklist

- [ ] I can explain UAT and the BA's responsibilities.
- [ ] I can distinguish a test plan, scenario, case and evidence.
- [ ] I documented scope, exclusions, roles and environment.
- [ ] I defined entry and exit criteria.
- [ ] I created positive, negative, boundary and alternate scenarios.
- [ ] I wrote detailed test cases with repeatable steps.
- [ ] I prepared synthetic test data.
- [ ] I linked requirements to scenarios, cases and results.
- [ ] I can explain execution status and coverage measures.
- [ ] I can write a reproducible defect report.
- [ ] I understand severity, priority, retesting and regression.
- [ ] I prepared a UAT summary and sign-off template.
- [ ] I completed the independent Solution validation pack.
- [ ] I completed the quiz and reviewed incorrect answers.
- [ ] I practised at least two interview questions.

**Day 44 is complete when the validation pack is internally consistent and another person could use it to conduct UAT. Writing test cases alone does not mean UAT has been executed.**

## 23. Bridge to Day 45

Day 45 is the final capstone day. You will bring the entire analysis together into a portfolio-ready presentation and recommendation.

Carry forward:
- Day 40: business problem, stakeholder map and scope.
- Day 41: elicitation results, user stories and functional requirements.
- Day 42: AS-IS and TO-BE workflows and gap analysis.
- Day 43: wireframes, data dictionary, prototype and acceptance criteria.
- Day 44: UAT plan, test cases, traceability, defect log and validation summary.

The final task is to communicate the problem, evidence, proposed solution, expected value, risks and validation outcome in a way that helps stakeholders make a decision.

**A Business Analyst's work is not finished when the document is written. It is finished when stakeholders understand the analysis and can make an informed decision.**
