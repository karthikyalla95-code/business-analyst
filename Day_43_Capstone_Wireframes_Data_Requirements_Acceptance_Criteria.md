# Day 43: Capstone — Wireframes, Data Requirements and Acceptance Criteria

**Phase:** 7 — End-to-end Business Analysis Capstone  
**Estimated time:** 2–3 hours  
**Difficulty:** Intermediate  
**Prerequisites:** Day 40 business problem, stakeholder map and scope; Day 41 elicitation, user stories and functional requirements; Day 42 AS-IS and TO-BE workflows and gap analysis.  
**Approved independent mini-project:** **Solution prototype**

---

## 1. Why this day matters

A requirement document explains what a solution must do. A process model explains how work should happen. But stakeholders often need to see how a person will actually use the proposed solution.

A Business Analyst connects these views by preparing a solution concept:

- Wireframes show the structure of screens.
- Screen flows show how a user moves between screens.
- Data requirements define what information the solution must capture, store, validate and display.
- Acceptance criteria describe the observable conditions that prove a requirement is satisfied.
- A traceability link connects each screen element and data field to an approved requirement.

**Scenario used throughout this lesson:** A service company receives customer onboarding requests through email and spreadsheets. Staff manually check documents, enter customer details into multiple places and send status updates. The capstone proposes a customer onboarding portal where customers submit information, upload documents and track progress.

The proposed design is a learning example, not a claim about a real company's systems.

## 2. Learning objectives

By the end of this lesson, you should be able to:

1. Explain the difference between a wireframe, mockup and prototype.
2. Convert functional requirements and TO-BE process steps into screen layouts.
3. Draw a screen flow with clear navigation and decision points.
4. Identify data entities, fields, types, mandatory rules and validation rules.
5. Write acceptance criteria that can be tested objectively.
6. Link requirements, screens, data fields and acceptance tests using traceability IDs.
7. Review a prototype with stakeholders and record assumptions and open questions.

---

## 3. Words you need

| Term | Plain-English meaning | Example |
|---|---|---|
| Solution concept | A high-level explanation of how the proposed solution addresses the business need | Customer portal with submission and tracking |
| Wireframe | A simple layout showing where content and controls appear | Boxes for a name field, upload area and Submit button |
| Mockup | A more visual design showing colours, typography and appearance | A polished portal screen |
| Prototype | A model that demonstrates how screens or interactions may work | Clicking Continue opens the next screen |
| Screen flow | The sequence and conditions that connect screens | Login → Dashboard → Application |
| UI | User interface: what a person sees and interacts with | Buttons, forms, labels and messages |
| UX | User experience: how easy and understandable the interaction is | Clear instructions and useful error messages |
| Field | One piece of information captured or displayed | Email address |
| Data type | The kind of value a field can hold | Text, date, number, Boolean |
| Entity | A business object about which the system stores information | Customer, Application, Document |
| Attribute | A property of an entity | Customer email or application status |
| Validation | A rule that checks whether supplied information is acceptable | Email must follow an accepted format |
| Mandatory field | A field that must be completed before a defined action | Customer name |
| Acceptance criteria | Conditions that must be true for a requirement to be accepted | A valid application receives a reference number |
| Empty state | What a screen displays when there is no data yet | “You have no applications” |
| Error state | What the user sees when an action cannot be completed | “File type is not supported” |
| Traceability | The ability to follow an item from its source requirement to design and test evidence | REQ-04 → SCR-03 → DATA-07 → UAT-12 |

### Wireframe versus mockup versus prototype

| Artifact | Main question it answers | Typical detail |
|---|---|---|
| Wireframe | What belongs on the screen and where? | Low |
| Mockup | What should the screen look like? | Visual |
| Prototype | How will the user move and interact? | Interaction |
| Production UI | What is actually built and released? | Complete implementation |

A wireframe is not a final product design. It is a communication and analysis artifact.

---

## 4. Start from requirements, not from decoration

A common beginner mistake is opening a design tool and drawing attractive screens before understanding the requirements.

Use this order:

1. Read the approved business objective and scope.
2. Review the user stories and functional requirements from Day 41.
3. Review the TO-BE workflow and identified gaps from Day 42.
4. Identify the user roles and tasks.
5. Decide which screens are necessary to complete those tasks.
6. Define the data each screen needs.
7. Write acceptance criteria.
8. Build the wireframe and screen flow.
9. Check traceability and unresolved questions.

### 4.1 Revisit the business outcome

Example business objective:

> Reduce avoidable manual follow-up during customer onboarding by giving customers a consistent way to submit information and view application progress.

This is an outcome, not a screen requirement.

Possible measurable indicators, to be agreed with stakeholders:

- Average time from submission to initial review.
- Percentage of applications submitted with all required information.
- Number of status-related support enquiries.
- Percentage of applications returned because of missing documents.

Do not invent a target such as “reduce delays by 50%” unless the business has approved that target and a baseline exists.

### 4.2 Convert a process step into a user task

| TO-BE process step | User task | Possible screen |
|---|---|---|
| Customer starts onboarding | Start a new application | Dashboard |
| Customer enters details | Provide personal and contact details | Customer Details |
| Customer supplies evidence | Upload required documents | Document Upload |
| System records submission | Review and submit | Review & Submit |
| Staff reviews application | View application and its status | Application Tracking |
| Staff requests missing information | See request and provide missing item | Action Required |

One screen may support several tasks. One task may require multiple screens. Do not assume one process step always equals one screen.

---

## 5. Identify users, goals and permissions

Different users may need different screens and actions.

| User role | Main goal | Example permissions |
|---|---|---|
| Customer | Submit and track own application | Create, view own, edit when allowed, upload |
| Operations reviewer | Review submitted applications | View assigned applications, request information, update review status |
| Administrator | Manage access and reference settings | Manage users and approved configuration |
| Support agent | Help resolve customer questions | View permitted customer and application information |

### 5.1 Role-based access questions

Ask stakeholders:

- Can a customer see another customer's application?
- Can a customer edit an application after submission?
- Who can request additional documents?
- Can a reviewer approve an application?
- Who can change a status?
- Which actions need an audit record?
- Can support staff view uploaded documents, or only status information?

**Important:** Do not assume a role has permission merely because it would be convenient. Record the decision and obtain approval.

### 5.2 Screen inventory

Before drawing, create a screen inventory.

| Screen ID | Screen name | Primary user | Purpose | Requirement link |
|---|---|---|---|---|
| SCR-01 | Sign In | Customer | Access the portal | FR-01 |
| SCR-02 | Dashboard | Customer | View applications and start a new one | FR-02 |
| SCR-03 | Customer Details | Customer | Enter contact information | FR-03 |
| SCR-04 | Document Upload | Customer | Upload required evidence | FR-04 |
| SCR-05 | Review & Submit | Customer | Check details and submit | FR-05 |
| SCR-06 | Application Tracking | Customer | View status and requested actions | FR-06 |
| SCR-07 | Reviewer Queue | Operations reviewer | Find applications requiring review | FR-07 |
| SCR-08 | Application Review | Operations reviewer | Review details and request missing information | FR-08 |

This is a proposed screen inventory. Confirm the actual scope with stakeholders.

---

## 6. Wireframe fundamentals

### 6.1 What a useful wireframe contains

A wireframe should communicate:

- Screen title and purpose.
- Main content areas.
- Field labels and input controls.
- Primary and secondary actions.
- Navigation.
- Help text and validation messages.
- Loading, empty, success and error states where relevant.
- Permission-dependent actions where relevant.

It does not need final colours, logos, animations or production-quality styling.

### 6.2 Common interface elements

| Element | What it does | BA question |
|---|---|---|
| Text input | Accepts short text | What format and length are valid? |
| Dropdown | Lets user choose from a list | Are values fixed or configurable? |
| Radio button | Selects one option from a small group | Is only one choice allowed? |
| Checkbox | Selects or confirms an option | Can several choices be selected? |
| Date picker | Captures a date | What date range is valid? |
| File upload | Accepts a document | Which formats and size limits apply? |
| Button | Starts an action | What happens after clicking it? |
| Table/list | Shows multiple records | What columns, sorting and filtering are needed? |
| Status badge | Communicates a state | Which statuses are valid and what do they mean? |
| Alert/message | Communicates feedback | Is the message understandable and actionable? |

### 6.3 Example wireframe: Customer Details

The following is a text wireframe. It is intentionally low fidelity.

~~~text
+------------------------------------------------------+
| CUSTOMER ONBOARDING PORTAL                 Help  Sign out
+------------------------------------------------------+
| Step 1 of 3: Customer details                        |
| [1 Details] ---- [2 Documents] ---- [3 Review]        |
|                                                      |
| Full name *                                          |
| [____________________________________________]       |
|                                                      |
| Email address *                                      |
| [____________________________________________]       |
|                                                      |
| Mobile number *                                      |
| [____________________________________________]       |
|                                                      |
| Preferred contact method                             |
| ( ) Email       ( ) Phone                            |
|                                                      |
| [Save and continue]             [Cancel]              |
|                                                      |
| * Required fields                                    |
+------------------------------------------------------+
~~~

### 6.4 Annotate the wireframe

| Label | Element | Behaviour to clarify |
|---|---|---|
| 1 | Step indicator | Shows progress through the application |
| 2 | Full name | Required text field; define accepted characters and length |
| 3 | Email address | Required field; validate format and uniqueness only if required |
| 4 | Mobile number | Required; confirm country code and accepted format |
| 5 | Contact method | One selection; define default or require explicit selection |
| 6 | Save and continue | Validate fields, save data and move to Documents |
| 7 | Cancel | Confirm whether data is saved as draft or discarded |

Do not write “validate properly” as a requirement. Specify the actual rule, error message and expected behaviour.

### 6.5 Design all important states

A screen is not fully analysed if only its successful state is considered.

For the Customer Details screen, consider:

| State | Example behaviour |
|---|---|
| Initial | Fields are blank and required markers are visible |
| Partially completed | Entered values remain visible when validation fails |
| Validation error | Missing required field is highlighted with a clear message |
| Saving | The action is disabled or shows progress to prevent duplicate submission |
| Saved | A clear confirmation appears and the next step opens |
| Network failure | Entered data is not silently lost; user receives recovery guidance |
| Read-only | Fields cannot be edited if the application is locked after submission |

Confirm the exact behaviour with product, design and engineering stakeholders.

---

## 7. Screen flow and navigation

A screen flow shows how a user moves through a solution. It should show both normal and alternate paths.

### 7.1 Customer journey example

~~~text
[Sign In]
    |
    v
[Dashboard] ---- No existing application ----> [Start Application]
    |                                               |
    | Existing application                          v
    v                                        [Customer Details]
[Application Tracking]                            |
    |                                               v
    | Action required                       [Document Upload]
    v                                               |
[Provide Missing Information]                       v
    |                                         [Review & Submit]
    +---------------------------------------------->|
                                                    v
                                             [Confirmation]
                                                    |
                                                    v
                                          [Application Tracking]
~~~

### 7.2 Add decision rules

A diagram should not hide important business decisions.

Examples:

- If authentication fails, remain on Sign In and show an appropriate error.
- If mandatory customer details are missing, do not continue to Documents.
- If a required document is missing, do not allow final submission unless an approved exception exists.
- If submission succeeds, generate or display a unique application reference.
- If the reviewer requests more information, the customer sees an action-required state.
- If the application is approved or rejected, display the approved outcome and next steps.

### 7.3 Navigation questions for stakeholder review

1. Can users return to an earlier step?
2. Are saved drafts available after sign-out?
3. What happens if the browser is closed halfway through?
4. Can users submit more than one application?
5. Can a customer edit information after submission?
6. How does the user know which action is next?
7. What happens if a session expires?
8. Is the portal usable on a mobile device?

### 7.4 Screen-flow review checklist

- Every screen has a clear purpose.
- Every entry point has a valid destination.
- Every important decision has labelled outcomes.
- Back, cancel and exit behaviour are defined.
- Error paths are included.
- User permissions are respected.
- No screen is unreachable.
- No critical action ends without feedback.

---

## 8. Data requirements

A screen tells us what the user sees. Data requirements tell us what information the solution must handle.

Data analysis begins by asking:

- What information is required?
- Why is it needed?
- Who provides it?
- Where does it come from?
- What format and allowed values apply?
- Is it mandatory?
- Who can view or change it?
- How long should it be retained?
- Does it contain personal or sensitive information?
- What happens when it is missing, invalid or changed?

### 8.1 Entity and attribute example

An entity is a business object. An attribute describes it.

| Entity | Example attributes |
|---|---|
| Customer | customer_id, full_name, email, mobile_number |
| Application | application_id, customer_id, submitted_at, status |
| Document | document_id, application_id, document_type, file_name, upload_status |
| Review | review_id, application_id, reviewer_id, decision, comments, reviewed_at |
| StatusHistory | history_id, application_id, old_status, new_status, changed_at |

These are conceptual examples. A real design may use different entities and structures.

### 8.2 Field-level data dictionary

A data dictionary documents each field consistently.

| Field ID | Entity | Field | Type | Required? | Example rule |
|---|---|---|---|---|---|
| DATA-01 | Customer | customer_id | Identifier | Yes | Unique, system-generated |
| DATA-02 | Customer | full_name | Text | Yes | 1–100 characters, agreed character policy |
| DATA-03 | Customer | email | Text | Yes | Must match accepted email format |
| DATA-04 | Customer | mobile_number | Text | Yes | Accepted country code and number format |
| DATA-05 | Application | application_id | Identifier | Yes | Unique reference |
| DATA-06 | Application | status | Controlled value | Yes | Draft, Submitted, Under Review, Action Required, Approved, Rejected |
| DATA-07 | Document | document_type | Controlled value | Yes | Must match configured required document types |
| DATA-08 | Document | file_name | Text | Yes | Store safe display name; do not trust file extension alone |
| DATA-09 | Document | uploaded_at | Date/time | Yes after upload | Timestamp recorded by system |
| DATA-10 | Review | reviewer_comments | Text | Conditional | Required when requesting information or recording a defined exception |

### 8.3 Define field rules precisely

Weak rule:

> Mobile number should be valid.

Better rule:

> The mobile number field must accept the country code and number format approved for the launch market. The system must reject values that do not meet the agreed format and display a corrective message without removing other valid entries.

The second version is more testable, but the exact pattern and length still need stakeholder confirmation.

### 8.4 Data types and formats

| Type | Example | Questions to ask |
|---|---|---|
| Text/string | Customer name | Minimum/maximum length? Allowed characters? |
| Integer | Number of dependants | Can it be negative? Is zero valid? |
| Decimal | Invoice amount | Precision? Currency? Rounding? |
| Date | Date of birth | Accepted range? Display format? |
| Date/time | Submitted timestamp | Which time zone is displayed? |
| Boolean | Consent provided | Is true/false enough, or is evidence also needed? |
| Identifier | Application reference | Who generates it? Is it unique? |
| Enumeration | Application status | Which values are allowed? Who can change them? |
| File | Identity document | Format, size, malware scanning and retention? |

**Important:** Phone numbers, postal codes and identifiers are usually stored as text rather than numbers. They may contain leading zeros, plus signs or letters and are not used for arithmetic.

### 8.5 Mandatory, optional and conditional fields

- **Mandatory:** must be supplied for the defined action.
- **Optional:** may be left blank.
- **Conditional:** required only when a specific condition is true.

Example:

| Field | Requirement |
|---|---|
| Full name | Mandatory |
| Alternate phone | Optional |
| Rejection reason | Conditional: required when rejecting an application |
| Additional document | Conditional: required when reviewer requests it |

### 8.6 Validation categories

| Validation | Meaning | Example |
|---|---|---|
| Presence | Is a required value supplied? | Name cannot be blank |
| Format | Does the value follow a format? | Email format |
| Length | Is it within allowed limits? | Name up to 100 characters |
| Range | Is the value within a permitted range? | Date is not in the future where prohibited |
| Allowed values | Is it one of the approved choices? | Status belongs to the status list |
| Cross-field | Do two or more fields agree? | End date is not earlier than start date |
| Uniqueness | Does the value duplicate an item that must be unique? | Application reference |
| Business rule | Does the value satisfy a business condition? | Required document must exist before submission |

A format check does not prove that an email address belongs to the customer. A successful upload does not prove that a document is genuine. Distinguish technical validation from business verification.

### 8.7 File upload requirements

For each upload, agree:

- Allowed file formats.
- Maximum file size.
- Maximum number of files.
- Whether multiple documents of the same type are permitted.
- Whether a document can be replaced.
- Whether users can preview or delete a file.
- Whether the system scans files for malware.
- How upload failures are handled.
- Whether upload completion is confirmed.
- Who can access the file.
- Retention and deletion policy.

Never invent a file size limit or approved format. Record it as an open decision until the relevant stakeholder confirms it.

### 8.8 Data privacy and security questions

Customer onboarding may involve personal information. The BA should document business needs and involve the privacy, security and legal specialists.

Ask:

- What is the minimum information needed?
- What is the lawful and approved purpose for collecting it?
- Is consent or another approved notice required?
- Which roles can view each field and document?
- Should sensitive values be masked in lists?
- Is access logged?
- How long is data retained?
- How is deletion or correction handled?
- Are data transfers and storage protected under the organization's security standards?
- Are test environments using synthetic or properly protected data?

Do not copy real customer data into a learning project or public repository.

---

## 9. Connect screens to data

A useful BA artifact maps each field to the screen where it appears and the underlying business data.

| Screen ID | UI label | Field ID | Source/entity | Behaviour |
|---|---|---|---|---|
| SCR-03 | Full name | DATA-02 | Customer.full_name | Capture and validate |
| SCR-03 | Email address | DATA-03 | Customer.email | Capture and validate |
| SCR-03 | Mobile number | DATA-04 | Customer.mobile_number | Capture and validate |
| SCR-04 | Document type | DATA-07 | Document.document_type | Select allowed type |
| SCR-04 | Choose file | DATA-08 | Document.file_name | Upload and show result |
| SCR-06 | Application status | DATA-06 | Application.status | Display read-only status |
| SCR-08 | Reviewer comments | DATA-10 | Review.reviewer_comments | Capture when required |

This mapping helps developers understand what information a screen uses and helps testers identify which fields need coverage.

### 9.1 Data ownership and source

For each important field, record:

- System of record: the approved source that owns the value.
- Data owner: business role accountable for its definition and quality.
- Data creator: user or system that first supplies it.
- Data updater: role or process allowed to change it.
- Consumers: screens, reports or integrations that use it.

Example: the application status may be owned by the onboarding workflow, changed by authorized workflow actions and displayed to the customer as read-only.

### 9.2 Data lifecycle

~~~text
Capture
  |
  v
Validate
  |
  v
Save as Draft
  |
  v
Submit
  |
  v
Review / Update Status
  |
  v
Retain according to policy
  |
  v
Archive or delete according to approved rules
~~~

The actual lifecycle, retention period and deletion rules must be confirmed by the organization.

---

## 10. Acceptance criteria

Acceptance criteria define the conditions that must be satisfied for a user story or requirement to be accepted.

They should be:

- Clear and unambiguous.
- Observable.
- Testable.
- Relevant to the business outcome.
- Consistent with approved scope and rules.

### 10.1 Weak versus strong criteria

Weak:

> The customer should be able to upload documents easily.

Stronger:

> Given a customer is on the Document Upload screen, when the customer selects a file that meets the approved file rules and uploads it successfully, then the document appears in the application with its document type and upload status.

The stronger criterion identifies a starting condition, action and expected result.

### 10.2 Given–When–Then format

- **Given:** the context or starting condition.
- **When:** the action or event.
- **Then:** the expected observable outcome.

Example:

**Story:** As a customer, I want to save my application as a draft so that I can complete it later.

Acceptance criteria:

1. Given the customer has entered valid information, when they select Save Draft, then the system saves the entered information against the draft application.
2. Given the draft is saved, when the customer returns to the dashboard, then the draft appears in the customer's application list.
3. Given the customer reopens the draft, when the details screen loads, then previously saved values are displayed.
4. Given the save operation fails, when the system receives the failure, then it displays a clear message and does not falsely indicate that the draft was saved.

### 10.3 Example criteria by feature

**Feature: Customer details**

- Given required fields are blank, when the customer selects Save and Continue, then the system identifies the missing fields and prevents progression.
- Given all required fields satisfy the approved rules, when the customer selects Save and Continue, then the information is saved and the Documents step opens.
- Given an invalid email format is entered, when validation runs, then the system displays an actionable message beside the email field.

**Feature: Document upload**

- Given the selected file meets approved upload rules, when upload completes, then the document is shown as uploaded.
- Given the selected file violates an approved rule, when the customer attempts upload, then the system rejects it and explains the applicable issue.
- Given an upload fails because of a network problem, when the failure is detected, then the customer receives a retry option and the interface does not show a false success state.

**Feature: Application tracking**

- Given a customer owns an application, when the customer opens its tracking page, then the current permitted status is displayed.
- Given the reviewer requests more information, when the status is updated, then the customer sees the action required and the requested next step.
- Given a customer attempts to access an application they do not own, then the system denies access according to the approved access-control design.

### 10.4 Acceptance criteria versus test cases

| Acceptance criteria | Test case |
|---|---|
| States what must be true | Describes exact test steps and data |
| Agreed during requirement/design work | Prepared for validation and testing |
| Usually concise and business-focused | More detailed and execution-focused |
| Can lead to several test cases | Verifies one or more criteria |

Example:

Criterion: A customer cannot submit an application without all required documents.

Possible test cases:
1. Submit with no documents.
2. Submit with one of two required documents.
3. Submit with all required documents.
4. Remove a document immediately before submission.
5. Attempt submission after an upload failure.

---

## 11. Traceability: requirements to prototype and tests

Traceability ensures that the proposed solution has not drifted away from the agreed need.

Use stable IDs. Do not rely on row numbers that change when a spreadsheet is sorted.

### 11.1 Example traceability matrix

| Requirement ID | Requirement | Screen | Data fields | Acceptance criterion |
|---|---|---|---|---|
| FR-01 | Customer can sign in | SCR-01 | Account identifier | AC-01 |
| FR-02 | Customer can start an application | SCR-02 | DATA-01, DATA-05 | AC-02 |
| FR-03 | Customer can enter details | SCR-03 | DATA-02, DATA-03, DATA-04 | AC-03 to AC-05 |
| FR-04 | Customer can upload documents | SCR-04 | DATA-07, DATA-08, DATA-09 | AC-06 to AC-08 |
| FR-05 | Customer can review and submit | SCR-05 | Application and document references | AC-09 |
| FR-06 | Customer can track status | SCR-06 | DATA-05, DATA-06 | AC-10 to AC-12 |
| FR-08 | Reviewer can request information | SCR-08 | DATA-10, status history | AC-13 |

### 11.2 Traceability questions

- Does every in-scope requirement have a design location?
- Does every screen element support an approved requirement or clearly marked design decision?
- Does every captured data field have a business purpose?
- Does each requirement have at least one acceptance criterion?
- Can each acceptance criterion be tested?
- Are out-of-scope features clearly marked?
- Are unresolved assumptions visible?

A screen element without a requirement may still be a necessary usability or technical design decision. Record its rationale rather than silently adding business scope.

---

## 12. Tool tour: Figma for a low-fidelity prototype

Figma is a collaborative interface-design tool. Use it to create screens and connect them into a clickable prototype. The interface may change over time, so treat the steps below as a general workflow rather than a guarantee that every button has the same position.

### 12.1 Getting started

1. Open the official Figma website: https://www.figma.com/
2. Create or sign in to an account using an account you control.
3. Create a new design file.
4. Rename it: Customer Onboarding — Capstone Prototype.
5. Create a page called Wireframes.
6. Create a second page called Screen Flow.
7. Create frames for the screens listed in your screen inventory.
8. Use simple rectangles, text and lines to represent fields, buttons and navigation.
9. Name frames with their screen IDs, for example SCR-03 Customer Details.
10. Use the prototype connection controls to connect actions to destination frames.
11. Preview the prototype and test every path.
12. Share access only with intended reviewers.

If the interface or free-plan limits differ, use the current Figma help centre: https://help.figma.com/

### 12.2 Organize the design file

Suggested pages:

- 00 — Read Me: purpose, scope, version and open questions.
- 01 — Screen Flow: end-to-end journey.
- 02 — Customer Wireframes: customer-facing screens.
- 03 — Reviewer Wireframes: staff screens.
- 04 — Components: repeated buttons, labels and status indicators.
- 05 — Notes: assumptions and feedback.

### 12.3 Consistent naming

Use clear frame names:

- SCR-01 Sign In
- SCR-02 Dashboard
- SCR-03 Customer Details
- SCR-04 Document Upload
- SCR-05 Review and Submit
- SCR-06 Application Tracking
- SCR-07 Reviewer Queue
- SCR-08 Application Review

Name interactive elements by purpose, such as BTN-Save-Draft or LNK-View-Application, if detailed naming helps the team.

### 12.4 Prototype interaction examples

| Control | Trigger | Destination or response |
|---|---|---|
| Start Application | Click | SCR-03 Customer Details |
| Save and Continue | Click | SCR-04 Document Upload, after required fields are valid |
| Back | Click | Previous step |
| Submit Application | Click | SCR-06 Application Tracking or confirmation state |
| View Application | Click | Selected application details |
| Request Information | Click | Reviewer action state with required comment |

A clickable prototype may simulate an action. It does not prove that the real backend, database, authentication or file storage exists.

### 12.5 Prototype review

Ask a reviewer to complete a task without coaching:

> Sign in, start a new application, enter customer details, upload the required documents, review the information and submit.

Observe:

- Where does the reviewer hesitate?
- Which labels are misunderstood?
- Can they identify the next action?
- Are errors understandable?
- Can they return and correct information?
- Do they understand the application status?

Record observed behaviour separately from your interpretation. One person's feedback is useful evidence, but not necessarily proof of a universal usability problem.

---

## 13. Follow-along: build a small prototype

Create a simple three-screen customer journey.

### Step 1 — Create the Dashboard

Add:

- Screen title: Customer Dashboard.
- Button: Start New Application.
- Section: My Applications.
- Empty state: You have no applications yet.

Expected result: a customer can understand how to start or find an application.

### Step 2 — Create Customer Details

Add:

- Full name.
- Email address.
- Mobile number.
- Preferred contact method.
- Save and Continue.
- Cancel.

Expected result: the form labels and required fields are clear.

### Step 3 — Create Document Upload

Add:

- Required document list.
- Upload control placeholder.
- Upload status.
- Remove or replace action, if approved.
- Back.
- Continue to Review.

Expected result: the customer can understand which evidence is needed and whether each upload succeeded.

### Step 4 — Connect the screens

- Dashboard Start New Application → Customer Details.
- Customer Details Save and Continue → Document Upload.
- Document Upload Back → Customer Details.

Expected result: all three screens are connected and navigation is understandable.

### Step 5 — Add one validation state

Create a version of Customer Details with the email field invalid.

Show:
- The field highlighted.
- A clear message explaining the expected correction.
- Other valid values retained.

Expected result: the user knows what to fix without losing unrelated information.

### Step 6 — Test the prototype

Run the journey from the Dashboard. Try both the normal path and the invalid-email path. Record any missing screen, broken connection or unclear label.

---

## 14. Worked example: from requirement to acceptance test

Requirement FR-04:

> The customer must be able to upload the documents required for their application.

**Step 1 — Clarify the requirement**

Questions:
- Which document types are required?
- Are different document types required for different customer categories?
- What formats and file sizes are permitted?
- Can a document be replaced?
- What happens if upload fails?
- Does the system verify the document or only store it?

**Step 2 — Identify screen**

SCR-04 Document Upload.

**Step 3 — Identify data**

- application_id
- document_type
- file_name
- uploaded_at
- upload_status
- storage_reference (technical design field; confirm with engineering)

**Step 4 — Define acceptance criteria**

- Required document types are shown to the customer.
- A file that meets the approved upload rules can be uploaded.
- A successful upload is displayed with a clear status.
- An invalid file is rejected with an actionable explanation.
- A failed upload is not displayed as successful.
- The application cannot be submitted until the approved document-completeness rule is satisfied.

**Step 5 — Derive tests**

| Test ID | Test | Expected result |
|---|---|---|
| UAT-01 | Open upload screen | Required document types appear |
| UAT-02 | Upload an allowed file | Upload success is displayed |
| UAT-03 | Upload a disallowed file | File is rejected with a message |
| UAT-04 | Interrupt upload | Failure is shown; no false success |
| UAT-05 | Submit with a required document missing | Submission is prevented with guidance |
| UAT-06 | Upload all required documents and submit | User can proceed if all other rules are met |

**Step 6 — Record unresolved decisions**

Do not guess the file size, format list, retention period or document verification method. Record each as an open question with an owner and due date.

---

## 15. Common mistakes and fixes

| Mistake | Why it is a problem | Better approach |
|---|---|---|
| Designing screens before reading requirements | The prototype may solve the wrong problem | Start with approved requirements and process |
| Making the wireframe too decorative | Stakeholders focus on colours instead of behaviour | Begin with structure and content |
| Showing only the happy path | Errors and exceptions remain undefined | Include empty, error, loading and alternate states |
| Using unclear field labels | Users may enter the wrong information | Use language customers understand |
| Writing “field should be valid” | Cannot be tested objectively | Specify format, range and error behaviour |
| Collecting unnecessary data | Increases user effort and privacy risk | Confirm business purpose and data minimization |
| Treating a prototype as a working application | Creates false expectations | Label simulated behaviour clearly |
| Forgetting access permissions | Users may see or change unauthorized data | Define role-based access |
| Adding fields without traceability | Scope can grow without approval | Link fields to requirements or documented decisions |
| Omitting mobile layout considerations | Screens may be difficult on smaller devices | Confirm supported devices and responsive behaviour |
| Assuming upload means verification | A stored file may still be incorrect or fraudulent | Separate upload, validation and business review |
| Not documenting open questions | Teams may implement assumptions as facts | Maintain an issue and decision log |

---

## 16. Industry scenario exercise

A customer reports that they submitted an application but cannot tell whether the company received the required documents. Operations staff say they often send follow-up emails asking customers to upload missing items.

Do not immediately conclude that the portal needs more status labels. Investigate the actual problem.

### Your analysis tasks

1. Identify the customer and operations user goals.
2. Find the relevant TO-BE process step from Day 42.
3. Identify the screen where the customer should see document status.
4. Define the data required to display that status.
5. Write two acceptance criteria:
   - One for successful upload.
   - One for failed upload.
6. Identify one security or privacy question.
7. Add the requirement, screen and data field to a traceability matrix.

### Example reasoning

- Business need: customers need reliable confirmation of document receipt.
- Screen: Document Upload and Application Tracking.
- Data: document type, upload status and upload timestamp.
- Acceptance: a successful upload is shown as received; a failed upload is not shown as received.
- Security question: which customer and staff roles may view or download the document?

The proposed design should be reviewed with users and technical stakeholders before being treated as approved.

---

## 17. Independent mini-project: Solution prototype

**Approved title:** Solution prototype

### 17.1 Objective

Build a low-fidelity prototype for the Customer Onboarding and Service Improvement System. Your prototype must demonstrate the customer journey, the important reviewer interaction, required data and testable acceptance criteria.

### 17.2 Scope

Create at least these six screens:

1. Customer Dashboard.
2. Customer Details.
3. Document Upload.
4. Review and Submit.
5. Application Tracking.
6. Reviewer Application Review.

Optional: add Sign In, Reviewer Queue and Action Required screens if time permits.

### 17.3 Required deliverables

Create a project folder with these files:

~~~text
day_43_solution_prototype/
|
|-- README.md
|-- screen_inventory.md
|-- screen_flow.md
|-- wireframe_notes.md
|-- data_dictionary.csv
|-- acceptance_criteria.md
|-- traceability_matrix.csv
|-- open_questions.md
|-- prototype_evidence/
    |-- dashboard.png
    |-- customer_details.png
    |-- document_upload.png
    |-- review_submit.png
    |-- application_tracking.png
    |-- reviewer_review.png
    |-- prototype_flow.png
~~~

Use screenshots or exported images from your own prototype. Do not include real customer information.

### 17.4 Task A — Screen inventory

For each screen, record:
- Screen ID.
- Screen name.
- User role.
- Screen purpose.
- Entry point.
- Main actions.
- Exit or next screen.
- Requirement ID.

Minimum: six screens.

### 17.5 Task B — Screen flow

Create a flow showing:
- Customer starts an application.
- Customer enters details.
- Customer uploads documents.
- Customer reviews and submits.
- Customer tracks status.
- Reviewer requests missing information.
- Customer returns to provide the requested information.

Include at least two alternate paths, such as validation failure and upload failure.

### 17.6 Task C — Wireframes

For each of the six required screens:
- Add a clear title.
- Add field labels and controls.
- Show primary and secondary actions.
- Include useful helper text.
- Show relevant status or validation states.
- Keep layout consistent.
- Mark simulated behaviour as prototype-only.

Do not spend time on final branding or detailed visual styling.

### 17.7 Task D — Data dictionary

Document at least 12 fields. Include:
- Field ID.
- Entity.
- Field name.
- Description.
- Data type.
- Mandatory/optional/conditional.
- Validation rule.
- Source or owner.
- Screen usage.
- Privacy/access note where relevant.

### 17.8 Task E — Acceptance criteria

Write at least 10 acceptance criteria across:
- Customer details.
- Document upload.
- Submission.
- Application tracking.
- Reviewer action.

Use Given–When–Then for at least six criteria. Ensure every criterion is testable.

### 17.9 Task F — Traceability

Link at least six functional requirements to:
- One or more screens.
- Relevant data fields.
- Acceptance criteria.

Identify any design element that is not directly tied to a functional requirement and explain why it is needed.

### 17.10 Task G — Open questions

Create a decision log:

| ID | Question or decision | Why it matters | Owner | Status |
|---|---|---|---|---|
| OQ-01 | Which file types are permitted? | Upload validation | Product/security | Open |
| OQ-02 | What is the maximum file size? | Upload design | Product/engineering | Open |
| OQ-03 | Can a customer edit after submission? | Screen behaviour | Business owner | Open |
| OQ-04 | Which statuses are customer-visible? | Tracking screen | Operations | Open |
| OQ-05 | How long are documents retained? | Privacy and compliance | Legal/privacy | Open |

The owner roles are examples. Assign real owners only after stakeholder agreement.

### 17.11 Implementation plan

| Order | Task | Evidence |
|---:|---|---|
| 1 | Read Day 41 requirements and Day 42 process model | Requirement and process references |
| 2 | Prepare screen inventory | screen_inventory.md |
| 3 | Map customer and reviewer journeys | screen_flow.md |
| 4 | Create six wireframes | Prototype frames |
| 5 | Document field-level data needs | data_dictionary.csv |
| 6 | Write acceptance criteria | acceptance_criteria.md |
| 7 | Link requirements, screens, fields and criteria | traceability_matrix.csv |
| 8 | Record unknowns and assumptions | open_questions.md |
| 9 | Test the clickable flow | prototype_evidence |
| 10 | Review and revise | Updated files and review notes |

### 17.12 Expected results

Your final prototype should allow a reviewer to understand:

- How a customer starts onboarding.
- What information the customer must provide.
- Which documents are needed.
- How the customer reviews and submits.
- How the customer sees application status.
- How a reviewer requests missing information.
- What data is captured and how it is validated.
- Which requirements and acceptance criteria each screen supports.

### 17.13 Validation checklist

- [ ] Six required screens exist.
- [ ] Each screen has a unique ID and purpose.
- [ ] Customer and reviewer roles are distinguished.
- [ ] The main customer journey is connected.
- [ ] At least two alternate/error paths are documented.
- [ ] Every required field has a data definition.
- [ ] Mandatory and conditional fields are distinguished.
- [ ] Upload rules are documented or marked open.
- [ ] At least ten acceptance criteria are written.
- [ ] At least six criteria use Given–When–Then.
- [ ] At least six requirements are traceable to screens, data and criteria.
- [ ] Open questions have owners or proposed owner roles.
- [ ] No real customer data appears in evidence.
- [ ] Prototype-only interactions are clearly labelled.
- [ ] A reviewer can complete the main journey without explanation.

### 17.14 Stuck ladder

If you are stuck, use these steps in order:

1. Re-read Sections 4–5 to identify user tasks and screens.
2. Re-read Section 6 and copy the Customer Details wireframe structure as a starting point.
3. Use the screen inventory in Section 5.2.
4. Use the data dictionary example in Section 8.2.
5. Use the Given–When–Then examples in Section 10.
6. Check the traceability example in Section 11.
7. Reduce the prototype to the six required screens; do not add optional screens until the core flow works.

### 17.15 Self-review rubric

| Dimension | Marks |
|---|---:|
| Screen inventory and role clarity | 10 |
| Wireframe completeness and usability | 20 |
| Screen flow and alternate paths | 15 |
| Data dictionary and validation | 15 |
| Acceptance criteria quality | 15 |
| Requirement traceability | 15 |
| Open questions, privacy and evidence | 10 |
| **Total** | **100** |

Suggested self-assessment:
- 90–100: strong, well-connected prototype and analysis artifacts.
- 75–89: good; fix gaps in traceability or edge cases.
- 60–74: core idea is present; improve field rules and acceptance criteria.
- Below 60: revisit requirements and rebuild the main flow before adding visual detail.

---

## 18. Knowledge check

Try answering before reading the answer key.

**Q1.** What is the primary purpose of a wireframe?

A. To implement database tables  
B. To show screen structure and content  
C. To deploy the application  
D. To approve the project budget

**Q2.** Which item best describes a screen flow?

A. A list of database columns  
B. A colour palette  
C. The sequence and conditions connecting screens  
D. A project cost report

**Q3.** A phone number may contain a leading zero or plus sign. Which data type is usually most suitable?

A. Integer  
B. Decimal  
C. Text/string  
D. Boolean

**Q4.** Which is the strongest acceptance criterion?

A. The page should look good.  
B. Upload should be easy.  
C. Given an allowed file is selected, when upload succeeds, then the file appears with a successful upload status.  
D. The system should be modern.

**Q5.** What does traceability help a BA verify?

A. That every screen uses the same colour  
B. That requirements connect to design, data and validation evidence  
C. That all users have administrator access  
D. That a prototype is production-ready

### Answer key and explanations

1. **B** — A wireframe communicates the arrangement and content of a screen before detailed visual design.
2. **C** — A screen flow documents navigation and decision paths.
3. **C** — Text preserves leading zeros and symbols and avoids inappropriate numeric operations.
4. **C** — It specifies a context, action and observable result.
5. **B** — Traceability connects business needs to solution artifacts and evidence.

---

## 19. Business Analyst interview preparation

### Question 1: What is the difference between a wireframe and a prototype?

**Answer:** A wireframe is a low-fidelity representation of a screen's structure and content. A prototype demonstrates how screens or interactions may work. A prototype can be clickable without being connected to a real backend.

**Example:** A wireframe shows the Customer Details fields and buttons. A prototype lets a reviewer click Save and Continue to view the Document Upload screen.

**Follow-up:** Does a clickable prototype prove that the actual application works?

**Answer:** No. It demonstrates a proposed interaction. Functional implementation, integrations, security and data persistence must be built and tested separately.

### Question 2: How do you convert requirements into wireframes?

**Answer:** I first review the business objective, approved requirements and process model. I identify user roles and their tasks, prepare a screen inventory, map the screen flow and then create wireframes. I link screen elements to requirement IDs and review the design with stakeholders.

**Follow-up:** What if a stakeholder requests a new field during wireframe review?

**Answer:** I clarify the business reason, data purpose, validation, access and impact. I check whether it is already in scope. If it changes an approved requirement, I record and route it through the agreed change process.

### Question 3: What is a data dictionary?

**Answer:** A data dictionary documents the fields used by a solution, including their meaning, type, format, mandatory status, validation rules and ownership. It helps business, development and testing teams use consistent definitions.

**Follow-up:** Why should a phone number usually be text rather than an integer?

**Answer:** A phone number is an identifier, not a quantity. It can contain a plus sign and leading zeros, and arithmetic is not meaningful.

### Question 4: How do you write good acceptance criteria?

**Answer:** I make each criterion specific, observable and testable. I often use Given–When–Then to describe the starting context, action and expected result. I include relevant positive, negative and boundary scenarios.

**Follow-up:** Can one acceptance criterion have multiple test cases?

**Answer:** Yes. A criterion can be verified through different valid, invalid and boundary inputs.

### Question 5: How do you ensure a prototype meets requirements?

**Answer:** I maintain traceability from each requirement to relevant screens, data fields and acceptance criteria. I review the prototype with stakeholders, walk through the main and alternate paths, record feedback and update the artifacts after agreement.

**Follow-up:** What do you do when a requirement has no screen?

**Answer:** I investigate whether it is a backend, integration, reporting, security or process requirement. Not every requirement needs a visible screen, but every requirement needs an appropriate design and validation approach.

---

## 20. Quick revision sheet

| Concept | Remember |
|---|---|
| Wireframe | Structure and content of a screen |
| Mockup | Visual appearance |
| Prototype | Demonstration of screens and interactions |
| Screen inventory | List of screens, users and purposes |
| Screen flow | Navigation and decision paths |
| Entity | Business object |
| Attribute | Property of an entity |
| Data dictionary | Definitions and rules for fields |
| Validation | Checks whether supplied data meets rules |
| Acceptance criteria | Conditions for accepting a requirement |
| Given–When–Then | Context, action and expected result |
| Traceability | Connects requirement to design and evidence |
| Empty state | Screen before data exists |
| Error state | Screen when an action fails |
| Open question | Decision that still needs confirmation |

**Five questions to ask before approving a screen:**

1. Who uses it?
2. What task does it support?
3. What data does it capture or display?
4. What happens when the input or action fails?
5. Which requirement and acceptance criterion does it support?

---

## 21. References and further learning

Use official documentation for current tool behaviour and terminology.

- Figma: https://www.figma.com/
- Figma Help Center: https://help.figma.com/
- W3C Web Content Accessibility Guidelines (WCAG): https://www.w3.org/WAI/standards-guidelines/wcag/
- OWASP Application Security Verification Standard: https://owasp.org/www-project-application-security-verification-standard/
- IIBA — International Institute of Business Analysis: https://www.iiba.org/
- GOV.UK Service Manual — designing user journeys and services: https://www.gov.uk/service-manual

These references provide further guidance. The organization's approved policies, architecture and legal requirements take precedence for a real project.

---

## 22. Day 43 completion checklist

- [ ] I can explain wireframes, mockups and prototypes.
- [ ] I can turn user tasks into a screen inventory.
- [ ] I can draw a screen flow with alternate paths.
- [ ] I can identify entities, attributes and field-level rules.
- [ ] I can distinguish mandatory, optional and conditional data.
- [ ] I can explain data validation and privacy questions.
- [ ] I can write testable Given–When–Then acceptance criteria.
- [ ] I can connect requirements, screens, data and acceptance criteria.
- [ ] I completed the independent Solution prototype project.
- [ ] I tested the main flow and recorded open questions.
- [ ] I completed the quiz and reviewed incorrect answers.
- [ ] I practised at least two interview questions.
- [ ] I saved the evidence and can explain the design decisions.

**Day 43 is complete when the prototype and its supporting analysis artifacts are present, internally consistent and reviewable—not merely when the screens look attractive.**

## 23. Bridge to Day 44

Day 44 continues the same capstone. You will prepare the solution validation pack: UAT plan, test cases and traceability. The prototype and acceptance criteria from today become inputs to validation.

Carry forward:
- Approved requirement IDs from Day 41.
- AS-IS and TO-BE workflows from Day 42.
- Screen inventory and prototype from Day 43.
- Data dictionary and acceptance criteria from Day 43.
- Open questions and assumptions that need stakeholder decisions.

The next question is: **How will business users prove that the proposed solution satisfies the agreed requirements?**
