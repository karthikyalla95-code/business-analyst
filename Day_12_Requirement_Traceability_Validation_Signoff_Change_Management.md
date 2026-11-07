# TechPhile.ai --- Business Analyst Career Pathway

# Day 12: Requirement Traceability, Validation, Sign-off and Change Management

**Phase:** 2 --- Requirements Engineering\
**Approved syllabus topic:** Requirement traceability, validation,
sign-off and change management\
**Learning level:** Beginner to Intermediate\
**Estimated study time:** 2--3 hours\
**Prerequisites:** Days 6--11 --- Requirement types; elicitation;
requirement analysis and prioritization; user stories and acceptance
criteria; use cases and alternate scenarios.

------------------------------------------------------------------------

## Learning objectives

By the end of this lesson, you should be able to:

1.  Explain requirement traceability and why it matters throughout a
    project.
2.  Build and interpret a Requirements Traceability Matrix (RTM).
3.  Trace requirements backward to business needs and forward to design,
    development and testing.
4.  Explain requirement verification versus requirement validation.
5.  Review requirements for completeness, consistency, clarity,
    feasibility and testability.
6.  Understand stakeholder reviews, approval and formal sign-off.
7.  Explain how requirement changes are requested, analyzed, approved,
    documented and communicated.
8.  Distinguish a change request from a defect, clarification and scope
    change.
9.  Identify the impact of a proposed change on scope, schedule, cost,
    quality, risks and dependencies.
10. Maintain traceability and documentation when requirements change.

------------------------------------------------------------------------

# 1. Why traceability, validation and change management matter

Imagine a college is building an online admission portal. During
discussions, the admissions team requests that applicants should be able
to submit applications online. The BA documents the requirement, and the
delivery team builds the feature.

Later, someone asks:

-   Which business objective does this feature support?
-   Which user story describes it?
-   Which acceptance criteria must pass?
-   Which test cases verify it?
-   Has the admissions manager approved the requirement?
-   If the fee-payment rule changes, which requirements, screens and
    tests are affected?

If the team cannot answer these questions, it may be difficult to prove
that the solution meets the business need or to understand the impact of
a change.

This is why four connected practices are important:

  -----------------------------------------------------------------------
  Practice                            Main question it answers
  ----------------------------------- -----------------------------------
  Requirement traceability            Where did this requirement come
                                      from, and where is it implemented
                                      and tested?

  Requirement validation              Are these the right requirements
                                      for the business need?

  Sign-off                            Have the authorized stakeholders
                                      reviewed and approved the agreed
                                      requirements or deliverable?

  Change management                   How do we evaluate, approve and
                                      control changes after requirements
                                      have been agreed?
  -----------------------------------------------------------------------

### Simple lifecycle

``` text
Business need
    |
    v
Business objective
    |
    v
Requirement
    |
    v
User story / use case / specification
    |
    v
Design and implementation
    |
    v
Test case and test result
    |
    v
Validated solution
    |
    v
Stakeholder review and sign-off

A proposed change can enter the process at any suitable point:
Change request -> impact analysis -> decision -> update linked artifacts
```

These activities are connected. A requirement that changes should be
traced to its related stories, specifications, designs and tests. A
requirement that has not been validated may be complete in a document
but still fail to solve the actual business problem.

------------------------------------------------------------------------

# 2. Requirement traceability

## 2.1 What is requirement traceability?

Requirement traceability is the ability to follow a requirement through
its origin, related requirements, solution components and verification
evidence.

It helps answer:

-   Why does this requirement exist?
-   Which stakeholder or business need requested it?
-   Which objective does it support?
-   Where is it represented in the solution?
-   How will we test it?
-   Has it been implemented and verified?
-   What else could be affected if it changes?

### Example

Business need:

> Reduce manual work in the college admission process.

Business requirement:

> The admission portal must allow applicants to submit applications
> online.

Functional requirement:

> The portal must allow an authenticated applicant to complete and
> submit an application for an open program.

User story:

> As an applicant, I want to submit my application online so that I can
> apply without visiting the admissions office.

Acceptance criterion:

> Given an authenticated applicant has completed all mandatory fields
> and supplied the required documents, when the applicant confirms
> submission, then the portal records the application and displays a
> unique reference.

Test case:

> Submit a complete application using valid details and documents, then
> verify that the application is stored and a unique reference is
> displayed.

Traceability links these artifacts so the team can see that the test
case checks a requirement that supports a real business need.

## 2.2 Why traceability is useful

1.  **Coverage:** Helps identify requirements that have no corresponding
    design, implementation or test.
2.  **Accountability:** Shows the source and reason for each
    requirement.
3.  **Change impact:** Helps identify related artifacts when a
    requirement changes.
4.  **Testing:** Helps testers derive test cases from agreed
    requirements.
5.  **Audit and compliance:** Provides evidence of decisions, approvals
    and verification where required.
6.  **Scope control:** Helps identify work that is not linked to an
    agreed requirement or objective.
7.  **Communication:** Gives stakeholders and delivery teams a shared
    view of progress.

Traceability is particularly useful when a system has many requirements,
multiple teams, dependencies, frequent changes or formal approval needs.

------------------------------------------------------------------------

# 3. Types and directions of traceability

## 3.1 Forward traceability

Forward traceability follows a requirement toward the solution and its
verification.

``` text
Requirement
    |
    v
User story / specification
    |
    v
Design element
    |
    v
Development item
    |
    v
Test case
    |
    v
Test result
```

It helps answer:

-   Has every approved requirement been considered in the solution?
-   Has every requirement been tested?
-   Is there any requirement that has not been implemented or verified?

**Example:** Requirement REQ-014 says the portal must display an
application reference after submission. Forward traceability helps
locate the related story, confirmation screen, implementation item and
test case.

## 3.2 Backward traceability

Backward traceability starts with a solution artifact and follows it
back to an approved requirement or business need.

It helps answer:

-   Why are we building this feature?
-   Is this design element supported by an approved requirement?
-   Is this test checking an agreed requirement?
-   Has unapproved scope entered the solution?

**Example:** A developer finds a request to add a second notification
screen. Backward traceability checks which requirement or approved
change justifies that work.

## 3.3 Bidirectional traceability

Bidirectional traceability means being able to follow the links both
forward and backward.

It supports both coverage and scope control.

  -----------------------------------------------------------------------
  Direction         Starting point    Destination       Main purpose
  ----------------- ----------------- ----------------- -----------------
  Forward           Business need or  Design,           Check that
                    requirement       implementation    requirements are
                                      and tests         addressed

  Backward          Design,           Approved          Check that
                    implementation or requirement or    solution work is
                    test              business need     justified

  Bidirectional     Either side       Related artifacts Maintain complete
                                      in both           relationships
                                      directions        
  -----------------------------------------------------------------------

**Memory aid:** Forward asks, "Did we build and test what was
requested?" Backward asks, "Why does this solution item exist?"

------------------------------------------------------------------------

# 4. Requirements Traceability Matrix (RTM)

## 4.1 What is an RTM?

A Requirements Traceability Matrix (RTM) is a table used to connect
requirements with their sources and related delivery artifacts.

An RTM can include:

-   Requirement ID
-   Requirement description
-   Business objective or source
-   Stakeholder or owner
-   Priority
-   User story or use-case reference
-   Design or specification reference
-   Development status
-   Test case ID
-   Test result
-   Approval status
-   Change/version information

An RTM may be maintained in Excel, Google Sheets, a requirements
management platform or a project tool. The tool is less important than
keeping the links accurate and current.

## 4.2 Example RTM

The following is an illustrative example for an admission portal. IDs
and status values are sample data, not universal standards.

  ------------------------------------------------------------------------------
  Requirement   Requirement   Source /       Story or    Test case   Status
  ID                          objective      use case                
  ------------- ------------- -------------- ----------- ----------- -----------
  REQ-001       Applicant can Applicant      US-001 /    TC-001,     Tested
                create an     access         UC-01       TC-002      
                account                                              

  REQ-002       Applicant can Reduce         US-002 /    TC-003,     Tested
                save an       repeated data  UC-02       TC-004      
                application   entry                                  
                draft                                                

  REQ-003       Applicant can Enable online  US-003 /    TC-005,     In testing
                submit a      applications   UC-03       TC-006      
                complete                                             
                application                                          

  REQ-004       Portal        Application    US-004 /    TC-007      Not tested
                generates a   tracking       UC-03                   
                unique                                               
                reference                                            
                after                                                
                successful                                           
                submission                                           

  REQ-005       Applicant can Reduce status  US-005 /    TC-008,     Not started
                view current  enquiries      UC-04       TC-009      
                application                                          
                status                                               
  ------------------------------------------------------------------------------

This table lets the BA quickly identify that REQ-004 and REQ-005 still
need test execution.

## 4.3 How to create an RTM step by step

**Step 1 --- Collect approved requirements**

Collect the current, agreed requirements from the requirements document,
backlog, user stories, use cases or other approved source.

Do not mix unconfirmed ideas into the approved requirement list without
marking their status.

**Step 2 --- Assign unique IDs**

Give each requirement a stable identifier.

Examples: - BR-001: Business requirement - FR-001: Functional
requirement - NFR-001: Non-functional requirement - US-001: User story -
TC-001: Test case

A project should choose a consistent naming convention. These prefixes
are examples only.

**Step 3 --- Record the source**

Capture where the requirement came from: - Stakeholder interview -
Workshop - Business policy - Existing process document - Regulatory
obligation - Approved business objective

**Step 4 --- Link related artifacts**

Connect each requirement to: - Related business objective - User story
or use case - Business rule - Design or specification - Development
item, if tracked - Test case and result

**Step 5 --- Record status**

Use agreed status values, such as: - Proposed - Under review -
Approved - In progress - Implemented - Ready for testing - Tested -
Rejected - Deferred

Do not invent status meanings. Define them for the project so that all
team members interpret them consistently.

**Step 6 --- Review for gaps**

Look for: - Requirements without a source - Requirements without
acceptance criteria - Requirements without design or implementation
links - Requirements without test cases - Test cases that do not map to
an approved requirement - Requirements whose approval or current version
is unclear

**Step 7 --- Update it when things change**

When a requirement is revised, record the change and update its linked
artifacts. Do not silently overwrite a previous agreed version if the
project needs change history.

## 4.4 RTM example with coverage gaps

  ---------------------------------------------------------------------------
  Requirement    Story linked?  Test linked?   Test passed?   Observation
  -------------- -------------- -------------- -------------- ---------------
  REQ-001        Yes            Yes            Yes            Covered

  REQ-002        Yes            Yes            No             Test failed;
                                                              investigate

  REQ-003        Yes            No             ---            Test coverage
                                                              missing

  REQ-004        No             No             ---            Requirement
                                                              needs
                                                              decomposition
                                                              or
                                                              clarification
  ---------------------------------------------------------------------------

This simple review reveals different problems:

-   REQ-002 has test coverage, but the test did not pass.
-   REQ-003 has a story but no test case.
-   REQ-004 is not linked to a story or test.

A blank test link does not always mean the requirement is wrong; it
means the traceability record is incomplete and needs attention.

## 4.5 Coverage calculations

A team may use simple coverage measures, provided it defines what is
counted.

**Requirement test coverage:**

`Requirements with at least one linked test case / Total approved testable requirements × 100`

Example:

-   Total approved testable requirements = 20
-   Requirements with at least one linked test = 18
-   Coverage = 18 / 20 × 100 = 90%

This does not mean 90% of the requirements have passed. It only means
90% have at least one linked test case.

**Test pass rate:**

`Passed executed test cases / Total executed test cases × 100`

Example:

-   Executed test cases = 40
-   Passed test cases = 36
-   Pass rate = 36 / 40 × 100 = 90%

Do not confuse test coverage with test pass rate.

## 4.6 Common RTM mistakes

  -----------------------------------------------------------------------
  Mistake                 Why it is a problem     Better practice
  ----------------------- ----------------------- -----------------------
  Reusing requirement IDs Links can point to the  Keep IDs unique and
                          wrong item              stable

  Recording only          Source and test         Add source and related
  requirement             coverage remain unclear artifact links
  descriptions                                    

  Forgetting to update    RTM becomes misleading  Update links and
  after changes                                   version information

  Treating a linked test  Coverage and result are Record test status
  as a passed test        different               separately

  Linking every test to   Hides missing           Map tests to the
  one generic requirement requirement-level       specific behavior they
                          coverage                verify

  Keeping obsolete        Teams may build         Mark superseded,
  requirements as active  outdated scope          rejected or retired
                                                  items

  Using vague status      Team members interpret  Define project status
  labels                  them differently        meanings
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 5. Requirement validation

## 5.1 What is requirement validation?

Requirement validation checks whether the documented requirements
represent the actual business need and stakeholder expectations.

It asks:

> Are we defining the right solution and the right requirements?

For example, a college may request an online application portal because
staff spend time handling paper forms. If the documented requirements
focus only on changing the form's colors, the requirements may be clear
but do not adequately address the business need.

Validation helps confirm that the requirements are relevant, complete
enough, agreed, feasible and aligned with the desired outcome.

## 5.2 Verification versus validation

These terms are often confused.

  -----------------------------------------------------------------------
  Verification                        Validation
  ----------------------------------- -----------------------------------
  Checks whether requirements are     Checks whether the requirements
  documented correctly and meet       represent the real business need
  quality standards                   

  Focuses on the quality of the       Focuses on suitability and
  requirement specification           stakeholder expectations

  "Are we writing the requirements    "Are we writing the right
  right?"                             requirements?"

  Example: Is the requirement clear   Example: Does it solve the
  and testable?                       applicant's actual problem?
  -----------------------------------------------------------------------

Both are necessary.

A requirement can be written perfectly and still describe the wrong
feature. Conversely, a requirement can represent a real need but be
written so vaguely that developers and testers cannot use it.

## 5.3 Requirement quality criteria

A good requirement should be reviewed against the following
characteristics:

  -----------------------------------------------------------------------
  Characteristic    Meaning           Weak example      Improved example
  ----------------- ----------------- ----------------- -----------------
  Clear             Has one           The portal should The application
                    understandable    be fast           status page
                    meaning                             should load
                                                        within the agreed
                                                        response-time
                                                        target

  Complete          Contains enough   User can pay      The portal must
                    information to                      show the payment
                    understand the                      result after
                    expected behavior                   receiving the
                                                        payment service
                                                        response

  Consistent        Does not conflict One requirement   Define which
                    with another      allows edits      fields can be
                    requirement       after submission; edited and under
                                      another prohibits what conditions
                                      all edits         

  Feasible          Can reasonably be Support every     Support the
                    delivered within  file type         approved list of
                    constraints                         file formats

  Testable          Can be checked    The portal should The portal must
                    objectively       be user-friendly  meet agreed
                                                        usability
                                                        acceptance
                                                        criteria

  Necessary         Supports a        Add an unrelated  Link the
                    business need or  animation         requirement to an
                    obligation                          objective or
                                                        justified
                                                        stakeholder need

  Unambiguous       Avoids unclear    Process quickly   State a
                    terms                               measurable time
                                                        target

  Traceable         Has an            Unreferenced      Link it to a
                    identifiable      feature           business
                    source and                          objective and
                    related artifacts                   source

  Prioritized       Has an agreed     Everything is     Assign a priority
                    relative          critical          using the
                    importance                          project's agreed
                                                        method

  Modifiable        Can be updated    Several unrelated Split distinct
                    without creating  rules in one      requirements and
                    unnecessary       paragraph         use stable IDs
                    confusion                           
  -----------------------------------------------------------------------

## 5.4 Requirement validation techniques

### A. Stakeholder review

Share requirements with the people who understand, own or use the
process.

Ask: - Does this reflect the actual business need? - Is any important
behavior missing? - Are any statements incorrect? - Are the assumptions
valid? - Are the priorities correct?

### B. Requirement walkthrough

A walkthrough is a structured session in which the BA takes stakeholders
and relevant team members through the requirements.

Typical sequence: 1. Explain the business objective. 2. Review scope and
boundaries. 3. Walk through requirements in a logical order. 4. Review
important user stories, use cases and acceptance criteria. 5. Discuss
exceptions, business rules and open questions. 6. Record corrections,
decisions and owners. 7. Confirm the next review or approval step.

### C. Prototyping

A prototype is an early representation of a proposed interface or
interaction. It helps stakeholders react to something concrete.

Example: - The BA shows a draft application form. - The admissions team
notices that the applicant must select a program before entering
academic details. - The BA records the feedback and updates the
requirements.

A prototype can help validate understanding, but a screen alone does not
prove that all business rules or system behavior have been defined.

### D. Scenario-based review

Walk through realistic situations: - A normal successful application -
Missing mandatory information - Invalid document upload - Failed
payment - Expired application deadline - Applicant returning to edit a
draft

This reveals missing conditions and unclear outcomes.

### E. Testability review

Ask whether a tester could determine whether the requirement has been
met.

If the requirement says "The portal should be easy to use," a tester
cannot objectively pass or fail it without measurable criteria.

### F. Data and process review

Where appropriate, compare requirements with: - Current process
documentation - Existing operational data - Business policies -
Regulations or contractual obligations - Actual user workflows

Do not assume that a stakeholder's first description captures every part
of the real process.

## 5.5 A practical validation checklist

Before requesting approval, check:

-   [ ] Each requirement supports a business need, objective or valid
    obligation.
-   [ ] The scope is clear.
-   [ ] Terms are defined consistently.
-   [ ] Functional behavior is understandable.
-   [ ] Non-functional requirements include measurable criteria where
    possible.
-   [ ] Business rules and exceptions are documented.
-   [ ] Requirements do not conflict.
-   [ ] Assumptions and unresolved questions are visible.
-   [ ] Priorities are agreed or clearly marked as provisional.
-   [ ] Requirements are feasible or have a documented feasibility
    concern.
-   [ ] Acceptance criteria or verification approach exists where
    appropriate.
-   [ ] Relevant stakeholders have reviewed the requirements.
-   [ ] Traceability links are recorded.

------------------------------------------------------------------------

# 6. Requirement review and validation meeting

A requirement review is a planned discussion to examine requirements and
capture feedback, decisions and unresolved issues.

## 6.1 Who may participate?

Depending on the project, participants can include:

-   Business owner or sponsor
-   Process owner
-   End users
-   Business Analyst
-   Product owner
-   Developers or solution architects
-   Testers or QA representatives
-   Security, compliance or operations representatives

Invite people who can provide relevant information or make the decisions
required. Not every stakeholder needs to attend every review.

## 6.2 BA preparation

Before the meeting:

1.  Share the latest requirements version.
2.  State the meeting objective.
3.  Identify the requirements requiring review.
4.  Share relevant process diagrams, stories, use cases or prototypes.
5.  List known assumptions and open questions.
6.  Identify decisions that need an authorized owner.
7.  Prepare a way to record comments, owners and due dates.

## 6.3 During the meeting

1.  Restate the business objective and scope.
2.  Confirm the correct document version.
3.  Review requirements in a logical sequence.
4.  Ask stakeholders to confirm or correct the content.
5.  Discuss conflicts and dependencies.
6.  Separate confirmed decisions from suggestions.
7.  Record action items, owners and due dates.
8.  Summarize what is approved, what remains open and what happens next.

## 6.4 After the meeting

-   Update the requirement document and RTM.
-   Record review comments and decisions.
-   Resolve or assign open questions.
-   Share meeting notes.
-   Circulate the revised version where required.
-   Request formal approval if the project's process requires it.

**Important:** Attendance at a meeting does not automatically mean that
every participant approved every requirement. Record explicit decisions
and approval evidence.

------------------------------------------------------------------------

# 7. Requirement sign-off

## 7.1 What is sign-off?

Sign-off is an explicit confirmation by an authorized stakeholder that a
defined set of requirements, document or deliverable has been reviewed
and accepted according to the project's approval process.

Sign-off creates a shared understanding of what has been agreed at a
particular point in time.

It does not mean that requirements can never change. It means that
changes should follow the agreed change-control process.

## 7.2 Why sign-off matters

-   Confirms that the relevant stakeholders have reviewed the
    requirements.
-   Reduces disagreement about what was agreed.
-   Establishes a baseline for delivery planning.
-   Helps manage scope and change requests.
-   Provides an approval record.
-   Clarifies accountability and decision ownership.

## 7.3 What should be included in an approval record?

An approval record may contain:

  -----------------------------------------------------------------------
  Field                               Example
  ----------------------------------- -----------------------------------
  Document name                       Admission Portal Requirements
                                      Specification

  Document/version                    Version 1.2

  Approval scope                      Functional requirements for
                                      application submission

  Approver                            Authorized admissions process owner

  Decision                            Approved / Rejected / Approved with
                                      conditions

  Date                                Date of decision

  Comments                            Conditions or requested corrections

  Evidence                            Recorded workflow approval, signed
                                      document or approved email

  Outstanding items                   Open issues not included in this
                                      approval
  -----------------------------------------------------------------------

Use the approval method required by the organization. A signature,
workflow action or email may be accepted in one organization and
insufficient in another.

## 7.4 Common approval statuses

-   **Approved:** The defined item is accepted.
-   **Rejected:** The item is not accepted and needs further work or a
    different decision.
-   **Approved with conditions:** Approval is given subject to clearly
    recorded conditions.
-   **Pending:** A decision has not yet been made.
-   **Deferred:** The decision is postponed.

Define what each status means in the project.

## 7.5 What if a stakeholder refuses to sign off?

A BA should not pressure someone into approval or mark a document
approved without authorization.

Instead:

1.  Ask which specific requirements or sections are not accepted.
2.  Record the concern in clear language.
3.  Determine whether the issue is a misunderstanding, missing
    information, conflicting expectation, feasibility issue or
    unresolved business decision.
4.  Identify the person authorized to resolve the issue.
5.  Update the requirements where an agreed correction is needed.
6.  Re-circulate the revised version.
7.  Record the final decision and any remaining conditions.

### Sign-off is not the same as UAT sign-off

  -----------------------------------------------------------------------
  Requirement sign-off                UAT sign-off
  ----------------------------------- -----------------------------------
  Confirms agreement on defined       Confirms acceptance of the solution
  requirements or scope               based on agreed user acceptance
                                      criteria

  Usually happens during requirements Usually happens after solution
  definition or baseline approval     validation and UAT execution

  Focuses on what is expected         Focuses on whether the delivered
                                      solution meets agreed expectations

  Example: Admissions manager         Example: Authorized business user
  approves application requirements   accepts tested application workflow
  -----------------------------------------------------------------------

The exact timing and approval gates vary by project methodology and
organizational policy.

------------------------------------------------------------------------

# 8. Requirement baseline

A requirement baseline is an agreed and controlled version of the
requirements used as a reference for planning and change evaluation.

A baseline can include: - Approved requirements - Version number and
date - Scope covered - Approval evidence - Known exclusions - Open items
and conditions

### Why a baseline matters

Suppose the approved requirement says:

> Applicants may edit a saved draft until they submit it.

Later, a stakeholder asks for applicants to edit submitted applications
too.

Without a baseline, the team may not know whether this is: - A new
requirement - A clarification of an existing requirement - A defect in
the current implementation - A change to the agreed business policy

The baseline provides the reference point for evaluating the request.

A baseline does not prevent change. It helps the team identify and
control change.

------------------------------------------------------------------------

# 9. Change management

## 9.1 What is requirement change management?

Requirement change management is the controlled process of handling
proposed changes to agreed requirements.

It ensures that a change is: - Clearly described - Properly justified -
Analyzed for impact - Reviewed by the appropriate people - Approved or
rejected by an authorized decision-maker - Reflected in the relevant
documents and delivery artifacts - Communicated to affected stakeholders

### Why requirements change

Requirements may change because of: - New business priorities - Updated
policies or regulations - Stakeholder feedback - New information
discovered during analysis - Technical or operational constraints -
Market or customer needs - Defects or gaps found during testing -
Dependencies on other systems or teams

Change is normal. Uncontrolled change is the problem.

## 9.2 Change request

A change request is a documented proposal to add, remove or modify an
agreed requirement, scope item, business rule or solution behavior.

Example:

> The admissions team requests that applicants should be allowed to edit
> their contact details after submitting an application.

This is a proposal. It should not automatically be treated as approved
work.

## 9.3 What should a change request contain?

  -----------------------------------------------------------------------
  Field                               Purpose
  ----------------------------------- -----------------------------------
  Change request ID                   Unique reference

  Request title                       Short description

  Requester                           Person or role raising it

  Date raised                         When it was submitted

  Current behavior                    What happens today

  Proposed change                     What should be different

  Business reason                     Why the change is needed

  Expected benefit                    Value expected from the change

  Priority / urgency                  How important and time-sensitive it
                                      is

  Affected requirements               Related requirement IDs

  Impact assessment                   Effects on scope, cost, schedule,
                                      quality, risk and dependencies

  Options                             Possible ways to address the need

  Recommendation                      BA/team recommendation, where
                                      requested

  Decision                            Approved, rejected, deferred or
                                      more information required

  Approver                            Authorized decision-maker

  Implementation status               Tracking after approval
  -----------------------------------------------------------------------

## 9.4 Change management workflow

``` text
1. Change request raised
          |
          v
2. Request logged and acknowledged
          |
          v
3. Clarify the requested change
          |
          v
4. Analyze impact and options
          |
          v
5. Review with decision-makers
          |
          v
6. Approve / reject / defer / request more information
          |
          v
7. Update requirement baseline and traceability
          |
          v
8. Update stories, use cases, designs and tests
          |
          v
9. Communicate the decision and revised scope
          |
          v
10. Track implementation and verify the change
```

The exact workflow may be lighter in an Agile team or more formal in a
regulated or contract-driven project. The principles remain: record the
request, understand its impact, obtain the right decision and keep
linked artifacts current.

------------------------------------------------------------------------

# 10. Change impact analysis

## 10.1 What is impact analysis?

Impact analysis identifies what could be affected if a proposed change
is accepted.

The BA should not look only at the requirement text. A change can affect
processes, people, data, interfaces, tests, timelines and other
requirements.

### Main impact areas

  -----------------------------------------------------------------------
  Area                                Questions to ask
  ----------------------------------- -----------------------------------
  Business scope                      Does the change add, remove or
                                      alter agreed functionality?

  Business process                    Do process steps, roles or
                                      approvals change?

  Requirements                        Which requirement IDs must be
                                      updated?

  User experience                     Are screens, messages or navigation
                                      affected?

  Data                                Are new fields, validations,
                                      retention or access rules needed?

  Integrations                        Do external systems or APIs need
                                      changes?

  Schedule                            Will delivery dates or dependencies
                                      change?

  Cost and resources                  Is additional effort, staffing or
                                      budget required?

  Quality and testing                 What new or revised test cases are
                                      needed?

  Security and privacy                Does the change affect access,
                                      sensitive data or permissions?

  Operations                          Are support procedures, training or
                                      monitoring affected?

  Risk                                Does the change introduce or
                                      increase a project or business
                                      risk?
  -----------------------------------------------------------------------

## 10.2 Worked impact analysis

**Current approved requirement:**

REQ-014: Applicants may edit application details while the application
is in Draft status.

**Proposed change:**

Allow applicants to edit their contact number after submitting an
application.

### Step 1 --- Clarify the request

Ask: - Can all submitted applications be edited? - Is only the contact
number editable? - Does the applicant need to verify the new number? -
Should the admissions team be notified? - Should the old number remain
in the audit history? - Can the number be changed after admission
decisions are made?

### Step 2 --- Identify affected artifacts

  -----------------------------------------------------------------------
  Artifact                            Possible impact
  ----------------------------------- -----------------------------------
  REQ-014                             Needs clarification or revision

  New requirement                     May be needed for post-submission
                                      contact updates

  Use case UC-04                      Add an edit-contact-details flow

  User story                          Add or revise a story for contact
                                      updates

  Acceptance criteria                 Define eligibility, validation and
                                      confirmation

  Screen design                       Add an edit action and verification
                                      flow

  Data rules                          Define validation and history
                                      requirements

  Notification process                May need an admissions-team
                                      notification

  Test cases                          Add authorized, unauthorized and
                                      invalid-number scenarios

  User guidance                       Update instructions and support
                                      material
  -----------------------------------------------------------------------

### Step 3 --- Assess delivery impact

The team estimates the additional design, development, testing and
operational work. The BA records known dependencies and uncertainties.

Do not invent effort estimates. Ask the responsible delivery team for
estimates.

### Step 4 --- Present options

Possible options might include: - Allow contact-number edits only before
a defined admissions milestone. - Allow edits at any time but require
verification. - Require an admissions officer to approve the change.

These are options to evaluate, not decisions the BA should make without
the relevant business owner.

### Step 5 --- Obtain a decision

The authorized decision-maker approves, rejects, defers or requests more
information.

### Step 6 --- Update traceability and documentation

If approved: - Update the requirement and its version. - Add or revise
related stories and use cases. - Update acceptance criteria and
designs. - Add or revise test cases. - Update the RTM and communicate
the decision.

If rejected or deferred, record the decision and rationale. Do not
silently remove the request from the record.

------------------------------------------------------------------------

# 11. Change request versus defect, clarification and scope creep

Not every new discussion is the same kind of change.

  -----------------------------------------------------------------------
  Item                    Meaning                 Example
  ----------------------- ----------------------- -----------------------
  Change request          Proposal to change an   Allow editing a
                          agreed requirement or   submitted application
                          scope                   

  Defect                  Delivered behavior does Portal fails to
                          not meet an agreed      generate the required
                          requirement             application reference

  Clarification           Request to explain an   Confirm what "valid
                          existing requirement    document" means
                          without necessarily     
                          changing its intent     

  Scope creep             Uncontrolled expansion  Team adds an unapproved
                          of scope without proper document-verification
                          review or approval      feature

  Enhancement             Proposed improvement to Add a progress
                          existing behavior       indicator to the
                                                  application form

  New requirement         A newly identified need Add a requirement for
                                                  SMS notifications
  -----------------------------------------------------------------------

A clarification may reveal that the requirement needs to be updated. A
defect may lead to a change request if the expected behavior itself
needs to change. Classify the issue based on the agreed baseline and the
actual situation.

## 11.1 Example: Is it a defect or a change request?

Approved requirement:

> After successful submission, the portal displays a unique application
> reference.

Observed behavior:

> The portal submits the application but displays no reference.

This is likely a defect because the delivered solution does not meet the
agreed requirement.

Now consider:

> The admissions team wants the portal to send the reference through SMS
> as well as display it on screen.

If SMS delivery was not part of the agreed requirement, this is likely a
new requirement or change request.

The difference is the agreed expectation, not simply whether someone has
asked for something new.

------------------------------------------------------------------------

# 12. Version control and change history

When requirements change, the team needs to know what changed and why.

A simple document version history can contain:

  --------------------------------------------------------------------------
  Version        Date           Change summary Updated by     Reviewed /
                                                              approved by
  -------------- -------------- -------------- -------------- --------------
  1.0            01-Nov         Initial        BA             Admissions
                                approved                      owner
                                requirements                  

  1.1            04-Nov         Clarified      BA             Process owner
                                document                      
                                upload rules                  

  1.2            07-Nov         Added approved BA             Authorized
                                contact update                approver
                                behavior                      
  --------------------------------------------------------------------------

Dates and names above are illustrative.

### Good version-control practices

-   Use unique requirement IDs.
-   Keep a clear version number for controlled documents.
-   Record the date and summary of each meaningful change.
-   Identify who made and approved the change.
-   Mark superseded requirements clearly.
-   Keep links to the current stories, use cases and test cases.
-   Ensure team members know which version is current.
-   Follow the organization's document storage and access rules.

Do not create multiple uncontrolled copies such as `requirements_final`,
`requirements_final2` and `requirements_latest_final`. Use an agreed
shared location and versioning approach.

------------------------------------------------------------------------

# 13. Roles and responsibilities

Responsibilities vary by organization, but a common division is:

  -----------------------------------------------------------------------
  Role                                Typical responsibility
  ----------------------------------- -----------------------------------
  Business Analyst                    Elicits, analyzes, documents,
                                      traces and validates requirements;
                                      coordinates reviews and impact
                                      analysis

  Business owner / sponsor            Confirms business priorities and
                                      makes decisions within their
                                      authority

  Process owner                       Confirms how the business process
                                      should work

  Product owner                       Prioritizes product backlog items
                                      and makes product decisions within
                                      their authority

  Developer / solution architect      Assesses solution and technical
                                      impact

  Tester / QA analyst                 Reviews testability, creates or
                                      executes tests and reports results

  Project manager / delivery lead     Assesses delivery, schedule,
                                      resource and governance impacts

  End user / representative           Confirms user needs and validates
                                      practical usability

  Change authority / governance group Reviews and decides changes where
                                      the project requires formal control
  -----------------------------------------------------------------------

A BA supports decisions by providing analysis. The BA does not
automatically have authority to approve business scope, budget or policy
changes.

------------------------------------------------------------------------

# 14. Practical BA workflow: from requirement to approved change

Use this sequence when working on a real project.

### Before requirements approval

1.  Identify the business need and its source.
2.  Assign unique requirement IDs.
3.  Document functional and non-functional requirements.
4.  Link requirements to stories, use cases and acceptance criteria.
5.  Review quality and testability.
6.  Conduct stakeholder validation.
7.  Resolve or record open questions.
8.  Obtain the required sign-off.
9.  Save the approved version as the project baseline.

### During delivery

1.  Maintain the RTM as design and implementation progress.
2.  Link requirements to relevant development and test artifacts.
3.  Track implementation and test status.
4.  Identify gaps, failures and unapproved scope.
5.  Communicate relevant status and risks.

### When a change is proposed

1.  Log the request.
2.  Clarify the business reason and expected outcome.
3.  Identify affected requirement IDs and artifacts.
4.  Analyze process, data, integration, schedule, cost, risk and test
    impacts.
5.  Discuss options with the relevant team members.
6.  Obtain an authorized decision.
7.  Update the baseline and linked artifacts if approved.
8.  Communicate the outcome.
9.  Track implementation and verification.

------------------------------------------------------------------------

# 15. Worked industry scenario: Admission portal

A college is replacing its paper-based admission process with an online
portal.

## 15.1 Initial business objectives

-   Allow applicants to submit applications online.
-   Reduce manual handling of paper forms.
-   Provide applicants with a way to check application status.
-   Help admissions staff manage applications consistently.

## 15.2 Sample requirements

  -----------------------------------------------------------------------
  ID                                  Requirement
  ----------------------------------- -----------------------------------
  BR-001                              The college must support online
                                      admission applications.

  FR-001                              An authenticated applicant must be
                                      able to save an application as a
                                      draft.

  FR-002                              An applicant must be able to submit
                                      an application that meets the
                                      defined submission rules.

  FR-003                              The portal must generate a unique
                                      reference after successful
                                      submission.

  FR-004                              An applicant must be able to view
                                      the status of a submitted
                                      application.

  NFR-001                             The portal must meet the
                                      response-time target agreed by the
                                      business and technical teams.
  -----------------------------------------------------------------------

The response-time target is intentionally not assigned a number here;
the project team must agree and document a measurable value.

## 15.3 Traceability examples

  -----------------------------------------------------------------------
  Requirement       Source            Related story /   Test reference
                                      use case          
  ----------------- ----------------- ----------------- -----------------
  BR-001            Business          US-001            Business outcome
                    objective                           review

  FR-001            Applicant         US-002 / UC-02    TC-001, TC-002
                    interview                           

  FR-002            Admissions        US-003 / UC-03    TC-003, TC-004
                    workshop                            

  FR-003            Application       US-004 / UC-03    TC-005
                    tracking need                       

  FR-004            Applicant status  US-005 / UC-04    TC-006, TC-007
                    enquiries                           

  NFR-001           Operational       NFR specification Performance test
                    expectation                         references
  -----------------------------------------------------------------------

## 15.4 Validation findings

During a walkthrough, the admissions team identifies that: - Some
programs require an application fee. - Some programs do not require a
fee. - A submitted application should not be freely editable. -
Applicants may need to correct contact information through a controlled
process.

The BA records these as business rules or requirement clarifications and
confirms the details with the authorized process owner.

## 15.5 Sign-off

The admissions process owner reviews the requirements. The review
identifies one unresolved question about when payment is considered
complete.

The BA: 1. Records the question and owner. 2. Updates the document only
after the rule is confirmed. 3. Circulates the revised version. 4.
Records the approval decision and version.

## 15.6 Change request

After approval, the admissions team requests a new feature: applicants
should be able to download a submitted application as a PDF.

The BA: 1. Logs the request. 2. Clarifies whether the PDF must include
uploaded documents or only form details. 3. Identifies related
requirements, screens, access rules and tests. 4. Requests effort and
schedule input from the delivery team. 5. Presents the impact to the
decision-maker. 6. Records the approval or rejection. 7. Updates the RTM
and other artifacts if approved.

This scenario shows how traceability, validation, sign-off and change
management work together.

------------------------------------------------------------------------

# 16. Common mistakes and how to avoid them

  -----------------------------------------------------------------------
  Mistake                 Consequence             Better approach
  ----------------------- ----------------------- -----------------------
  Creating an RTM only at Missing links are       Start traceability
  the end                 discovered too late     during requirements
                                                  analysis

  Treating a linked test  Gives a false picture   Track coverage and test
  as a passed test        of quality              result separately

  Validating only with    Business needs may be   Include relevant
  the project team        misunderstood           business stakeholders

  Assuming silence means  Creates disputes about  Obtain explicit
  approval                what was agreed         approval evidence

  Treating sign-off as a  Prevents legitimate     Use controlled change
  permanent ban on change business changes        management

  Accepting every request Causes scope and        Analyze and obtain an
  immediately             schedule disruption     authorized decision

  Failing to assess       Related screens, data   Review all traceability
  downstream impact       or tests may be missed  links

  Updating the            Tests may verify        Update every affected
  requirement but not its outdated behavior       artifact
  tests                                           

  Confusing defects with  Work may be classified  Compare actual behavior
  new features            and prioritized         with the approved
                          incorrectly             baseline

  Keeping unclear         Teams may work from     Maintain one controlled
  versions                different requirements  current version

  Letting the BA approve  Decisions may exceed    Identify decision
  everything              the BA's authority      owners and approval
                                                  rules
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 17. Interview questions and answers

## Q1. What is requirement traceability?

**Answer:**\
Requirement traceability is the ability to follow a requirement from its
source and business objective through related solution artifacts and
testing evidence. It helps confirm that requirements are justified,
implemented and verified.

**Example:** A requirement for generating an application reference is
linked to the applicant story, confirmation flow and test case that
checks the reference.

**Follow-up:** What is bidirectional traceability?

It means being able to follow links both from a requirement to its
implementation and tests, and from a solution artifact back to the
requirement that justifies it.

## Q2. What is an RTM?

**Answer:**\
A Requirements Traceability Matrix is a structured table that maps
requirements to their sources and related artifacts, such as business
objectives, user stories, use cases, design items and test cases.

**Example:** An RTM can show that FR-003 is linked to US-004 and TC-005,
and whether the test has passed.

**Follow-up:** What would you do if a requirement has no linked test
case?

I would confirm whether it is testable and in scope, identify the
appropriate verification method, and coordinate with the test team to
create or link the required test coverage.

## Q3. What is the difference between verification and validation?

**Answer:**\
Verification checks whether requirements are documented correctly and
meet quality standards. Validation checks whether the requirements
represent the actual business need.

**Example:** Checking that a requirement is unambiguous is verification.
Confirming with admissions staff that the requirement solves their
application-processing problem is validation.

**Follow-up:** Can a requirement pass verification but fail validation?

Yes. It can be clearly written and testable but still describe the wrong
business capability.

## Q4. What makes a requirement testable?

**Answer:**\
A requirement is testable when its expected behavior or outcome can be
checked using clear, objective criteria. Vague words such as "fast,"
"easy" or "user-friendly" need measurable or otherwise agreed acceptance
criteria.

**Example:** Replace "The page should load quickly" with an agreed
response-time target and defined measurement conditions.

**Follow-up:** Who should help define non-functional targets?

Relevant business owners, users, architects, developers, testers and
operations or security specialists, depending on the requirement.

## Q5. What is requirement sign-off?

**Answer:**\
Sign-off is explicit approval by an authorized stakeholder for a defined
set of requirements or deliverables. It establishes what has been agreed
at that point in the project.

**Example:** The admissions process owner approves version 1.2 of the
application requirements.

**Follow-up:** Does sign-off mean requirements can never change?

No. It establishes an agreed baseline. Later changes should be evaluated
and approved through the project's change process.

## Q6. What is a requirement baseline?

**Answer:**\
A requirement baseline is an agreed, controlled version of requirements
used as a reference for planning and evaluating changes.

**Example:** Version 1.0 of the admission portal requirements is
approved and used to assess a later request for PDF downloads.

**Follow-up:** Why should the baseline have a version number?

It helps the team identify which requirements were agreed at a
particular time and compare later changes accurately.

## Q7. What is a change request?

**Answer:**\
A change request is a documented proposal to add, remove or modify an
agreed requirement, scope item or solution behavior. It should be
logged, analyzed and decided by the appropriate authority.

**Example:** Allow applicants to download a submitted application as a
PDF.

**Follow-up:** Should a BA immediately add an approved-looking request
to the backlog?

No. The BA should first clarify and record it, assess impact and follow
the team's approval and prioritization process.

## Q8. What is impact analysis?

**Answer:**\
Impact analysis identifies the requirements, processes, systems, data,
designs, tests, schedule, cost, resources, risks and stakeholders that
may be affected by a proposed change.

**Example:** Allowing contact-number edits after submission may affect
permissions, verification, audit history, notifications and test cases.

**Follow-up:** Which artifact helps identify affected requirements and
tests?

The RTM is a key starting point, supported by the requirement
repository, backlog, designs and test documentation.

## Q9. What is the difference between a defect and a change request?

**Answer:**\
A defect is when the delivered solution does not meet an agreed
requirement. A change request proposes changing or adding to the agreed
expectation.

**Example:** If the approved portal must display an application
reference but does not, that is likely a defect. Adding SMS delivery
when it was not agreed is likely a new requirement or change request.

**Follow-up:** What should you check before classifying an issue?

Compare the observed behavior with the current approved requirement and
its acceptance criteria.

## Q10. What would you do if stakeholders disagree during requirement validation?

**Answer:**\
I would document the differing expectations, identify the exact point of
disagreement, understand the business reasons and impacts, and involve
the authorized decision-maker. I would record the final decision and
update the requirements and traceability links.

**Follow-up:** Should the BA choose the option that is easiest to
develop?

Not without understanding business value and obtaining the appropriate
decision. Technical feasibility is one input, not the only decision
factor.

## Q11. How do you ensure requirements remain traceable after a change?

**Answer:**\
I would retain the requirement ID where appropriate, record the change
and version, update affected stories, use cases, designs and tests, and
review the RTM for missing or obsolete links. I would also communicate
the revised baseline to affected stakeholders.

**Follow-up:** Why should obsolete links be marked rather than silently
deleted?

The history helps explain earlier decisions and prevents confusion about
why a requirement or test changed.

## Q12. What is the BA's role in change management?

**Answer:**\
The BA clarifies the request, records its business reason, identifies
affected requirements and stakeholders, coordinates impact analysis,
presents options and updates documentation after a decision. The BA
supports the decision but does not automatically own approval authority.

**Follow-up:** Who approves a business scope change?

The person or governance body authorized by the organization's project
or product decision process.

------------------------------------------------------------------------

# 18. Knowledge check

Try answering before checking the suggested answers.

1.  What is requirement traceability?
2.  What is the difference between forward and backward traceability?
3.  What is the purpose of an RTM?
4.  A requirement has a linked test case, but the test has failed. Is
    the requirement fully verified?
5.  What is the difference between requirement verification and
    validation?
6.  Give three characteristics of a high-quality requirement.
7.  Why should a requirement review record open questions and action
    owners?
8.  What is requirement sign-off?
9.  Does sign-off mean that future changes are prohibited?
10. What is a requirement baseline?
11. List five areas to consider during change impact analysis.
12. A portal fails to display a reference that an approved requirement
    says must be displayed. Is this likely a defect or a new change
    request?
13. A stakeholder requests an additional SMS notification that was never
    included in the approved scope. How should it be handled?
14. Why must an RTM be updated after a requirement changes?
15. Does the BA always have authority to approve a change?

## Suggested answers

1.  The ability to follow a requirement from its source through related
    solution artifacts and verification evidence.
2.  Forward traceability follows a requirement toward design,
    implementation and tests. Backward traceability follows a solution
    artifact back to its approved requirement or business need.
3.  To map requirements to sources, objectives and related delivery and
    testing artifacts, helping identify coverage gaps and change
    impacts.
4.  No. The test is linked, so coverage exists, but the failed result
    indicates the expected behavior has not been verified successfully.
5.  Verification checks the quality and correctness of the requirement
    documentation. Validation checks whether the requirements represent
    the actual business need.
6.  Clear, complete and testable. Other valid answers include
    consistent, feasible, necessary, unambiguous and traceable.
7.  It makes unresolved work visible and establishes who is responsible
    for resolving each issue and by when.
8.  Explicit approval by an authorized stakeholder for a defined set of
    requirements or deliverables.
9.  No. Changes can still be proposed, but they should follow the agreed
    change-management process.
10. An agreed and controlled version of requirements used as a reference
    for planning and evaluating changes.
11. Any five of: scope, process, requirements, data, integrations,
    schedule, cost, resources, quality, testing, security, operations,
    risk and dependencies.
12. Likely a defect, because the delivered behavior does not meet the
    approved requirement.
13. Log it as a proposed change or new requirement, clarify the need,
    assess impact, obtain an authorized decision and update linked
    artifacts if approved.
14. To keep links, versions and test coverage accurate and to help the
    team understand the impact of the change.
15. No. The BA supports analysis and documentation; approval authority
    belongs to the designated decision-maker or governance process.

------------------------------------------------------------------------

# 19. Quick revision sheet

  -----------------------------------------------------------------------
  Concept                             Remember
  ----------------------------------- -----------------------------------
  Traceability                        Follow a requirement from source to
                                      solution and tests

  Forward traceability                Requirement → implementation and
                                      verification

  Backward traceability               Solution artifact → approved
                                      requirement

  Bidirectional traceability          Follow links in both directions

  RTM                                 Matrix connecting requirements to
                                      related artifacts

  Coverage                            Whether requirements have
                                      appropriate linked verification

  Test pass rate                      Proportion of executed tests that
                                      passed

  Verification                        Are the requirements written
                                      correctly?

  Validation                          Are these the right requirements?

  Requirement review                  Structured examination and feedback

  Sign-off                            Explicit approval by an authorized
                                      stakeholder

  Baseline                            Controlled, agreed version of
                                      requirements

  Change request                      Documented proposal to modify
                                      agreed scope or behavior

  Impact analysis                     Identify effects of a proposed
                                      change

  Defect                              Delivered behavior does not meet
                                      the agreed requirement

  Scope creep                         Uncontrolled expansion of scope
  -----------------------------------------------------------------------

### Key lifecycle to remember

``` text
1. Elicit and document requirements
             |
             v
2. Assign IDs and establish traceability
             |
             v
3. Verify requirement quality
             |
             v
4. Validate with stakeholders
             |
             v
5. Obtain required sign-off
             |
             v
6. Establish approved baseline
             |
             v
7. Maintain traceability during delivery
             |
             v
8. Log and analyze proposed changes
             |
             v
9. Obtain an authorized decision
             |
             v
10. Update linked artifacts and communicate
```

### Five interview-ready distinctions

1.  **Traceability vs validation:** Traceability follows relationships;
    validation checks whether requirements represent the business need.
2.  **Verification vs validation:** Verification checks whether
    requirements are written correctly; validation checks whether they
    are the right requirements.
3.  **Requirement sign-off vs UAT sign-off:** Requirement sign-off
    approves expectations; UAT sign-off accepts the tested solution
    against those expectations.
4.  **Defect vs change request:** A defect fails an agreed expectation;
    a change request proposes a new or altered expectation.
5.  **Coverage vs pass rate:** Coverage measures whether requirements
    have linked tests; pass rate measures how many executed tests
    passed.

------------------------------------------------------------------------

# 20. Day 12 completion checklist

-   [ ] I can explain requirement traceability in plain English.
-   [ ] I can distinguish forward, backward and bidirectional
    traceability.
-   [ ] I can explain the purpose and structure of an RTM.
-   [ ] I can create requirement IDs and link requirements to stories,
    use cases and tests.
-   [ ] I can identify missing traceability links.
-   [ ] I understand the difference between test coverage and test pass
    rate.
-   [ ] I can explain verification and validation with examples.
-   [ ] I can review requirements for clarity, completeness, consistency
    and testability.
-   [ ] I understand how a requirement walkthrough is conducted.
-   [ ] I can explain sign-off and requirement baselines.
-   [ ] I know why approval must be recorded explicitly.
-   [ ] I can describe the change-request workflow.
-   [ ] I can perform a basic impact analysis.
-   [ ] I can distinguish a defect, clarification and change request.
-   [ ] I understand how to update traceability after an approved
    change.
-   [ ] I can explain the BA's role and the decision-maker's role.
-   [ ] I can answer the interview questions in my own words.

------------------------------------------------------------------------

**Day 12 complete --- Requirement Traceability, Validation, Sign-off and
Change Management.**

**Phase 2 --- Requirements Engineering is complete.**

**Next syllabus topic --- Day 13: Business Process Modeling and Process
Discovery.**
