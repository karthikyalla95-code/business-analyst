# TechPhile.ai — Business Analyst Career Pathway

# Day 19: Functional Specifications, Business Rules and Documentation Standards

**Phase:** 3 — Business Process Analysis and Improvement  
**Estimated learning time:** 2–3 hours  
**Difficulty:** Beginner to Intermediate  
**Prerequisites:** Days 13–18: requirements, use cases, BPMN, AS-IS/TO-BE, gap analysis and root-cause analysis.

## Learning objectives

By the end of this lesson, you will be able to:
1. Explain the purpose and structure of a Functional Specification Document (FSD).
2. Convert a business requirement into clear, testable functional requirements.
3. Write business rules with conditions, actions and exceptions.
4. Distinguish functional requirements, non-functional requirements, assumptions and constraints.
5. Maintain traceability between business needs, requirements and acceptance criteria.
6. Review a specification for ambiguity, completeness and testability.

## 1. Why this matters in a BA job

A stakeholder may say: “Customers should be able to book an appointment online.” That sentence describes a need, but it does not tell developers what screens to build, what information to collect, what happens when a slot is full, or how testers should verify the feature.

A Business Analyst turns that broad need into an agreed description of system behaviour. The FSD becomes a shared reference for business stakeholders, designers, developers and testers.

**Workplace scenario:** A clinic wants an appointment-booking feature. The BA documents who can book, what data is required, how availability is checked, what happens after confirmation, and which errors must be shown.

## 2. Key terms

| Term | Meaning | Example |
|---|---|---|
| Business requirement | Outcome the business needs | Reduce phone-based appointment booking |
| Functional requirement (FR) | Behaviour the system must provide | The system shall let a patient select an available slot |
| Non-functional requirement (NFR) | Quality or operating condition | Search results should load within 3 seconds under normal load |
| Business rule | Policy that controls a decision or process | A patient cannot hold two appointments at the same time |
| Assumption | Belief treated as true until confirmed | Patients have a valid mobile number |
| Constraint | Limitation the solution must obey | The first release supports only one clinic |
| Acceptance criterion | Condition that proves a requirement is satisfied | Given an available slot, when the patient confirms, then the booking is saved |
| Traceability | Ability to follow a need through design, build and testing | BR-01 → FR-03 → TC-07 |
| Exception flow | Behaviour when the normal path cannot continue | Selected slot was taken by another patient |

**Functional vs non-functional:** “The user can reset a password” is functional. “The reset link expires after 15 minutes” is a business/security rule or functional constraint depending on the specification structure. “The page responds within 2 seconds” is a performance NFR.

## 3. Anatomy of a useful Functional Specification

A practical FSD usually contains:

1. Document control: title, owner, version, date and status.
2. Purpose and scope: why the feature exists and what is included/excluded.
3. Stakeholders and users: who is affected and who approves.
4. Business context: problem, objective and current process.
5. Functional requirements: uniquely identified, testable system behaviours.
6. Business rules: policies and decision logic.
7. Data requirements: fields, formats, validation and source.
8. Process or screen flows: happy path and exception paths.
9. Non-functional requirements: performance, security, accessibility and availability.
10. Assumptions, dependencies and constraints.
11. Acceptance criteria and traceability.
12. Open questions, approvals and change history.

The exact template varies by organisation. Consistency and clarity matter more than a particular document layout.

## 4. Write requirements that can be tested

Use the pattern: **ID + actor/system + shall + one observable behaviour + condition**.

Weak: “The booking page should be user-friendly.”  
Better: “FR-04: The system shall display available appointment slots for the selected clinic and date.”

Weak: “The system should send messages quickly.”  
Better: “FR-08: After a booking is confirmed, the system shall send a confirmation SMS to the mobile number stored in the patient profile.”

A requirement should be:
- Clear: one interpretation.
- Complete: enough information to implement and test.
- Consistent: does not conflict with another requirement.
- Feasible: possible within the agreed constraints.
- Necessary: supports a real business need.
- Verifiable: a tester can determine pass or fail.
- Traceable: has a unique ID and source.

Avoid vague words such as *fast, easy, normally, suitable, user-friendly, as soon as possible* unless they are defined with measurable criteria.

### Worked example: turn a request into requirements

Stakeholder statement: “Patients should book appointments online and avoid double-booking.”

Clarifying questions:
- Who can book: registered patients, guests or staff?
- What information is mandatory?
- Can a patient cancel or reschedule?
- How long is a slot held before confirmation?
- What happens if two users select the same slot?
- Which channels send confirmation?

Example requirements:

| ID | Functional requirement | Verification |
|---|---|---|
| FR-01 | The system shall allow an authenticated patient to view clinics | Clinic list is visible after sign-in |
| FR-02 | The system shall display available slots for a selected clinic and date | Only open slots are displayed |
| FR-03 | The system shall require patient, clinic, date and slot before submission | Missing fields show validation |
| FR-04 | The system shall re-check slot availability at confirmation | A slot taken by another user cannot be booked |
| FR-05 | The system shall create one booking record for a successful confirmation | Booking ID and details are stored |
| FR-06 | The system shall display a confirmation reference after success | Reference appears on confirmation page |

## 5. Business rules: make policy explicit

A business rule expresses a policy, calculation, eligibility condition or restriction. Give each rule an ID and write it so it can be checked.

| Rule ID | Rule | Example |
|---|---|---|
| BR-01 | A patient may have at most one active appointment per doctor at a given time | Two overlapping bookings with the same doctor are blocked |
| BR-02 | A slot is bookable only when its status is Available | Booked or blocked slots cannot be selected |
| BR-03 | A booking must be confirmed before the slot hold expires | Expired holds return the slot to Available |
| BR-04 | Cancellation is allowed until 2 hours before the appointment | A request 1 hour before is rejected |

These are illustrative policies. A real BA must confirm them with the business owner; do not invent policy and present it as approved.

### Decision table

Suppose a patient can book only if they are signed in, the slot is available and the required details are complete.

| Signed in? | Slot available? | Details complete? | Outcome |
|---|---|---|---|
| No | Yes | Yes | Ask user to sign in |
| Yes | No | Yes | Show unavailable slot |
| Yes | Yes | No | Highlight missing details |
| Yes | Yes | Yes | Allow confirmation |

A decision table is useful when several conditions combine. It helps expose missing combinations.

## 6. Data requirements and validation

A field definition should describe its name, purpose, type, mandatory status, allowed format and validation.

| Field | Type | Required? | Validation |
|---|---|---|---|
| patient_id | Identifier | Yes | Must refer to an existing patient |
| clinic_id | Identifier | Yes | Must refer to an active clinic |
| appointment_date | Date | Yes | Must be a permitted booking date |
| slot_id | Identifier | Yes | Must be available at confirmation |
| mobile_number | Text | Yes | Must match the agreed country-specific format |

Do not store a phone number as a numeric value: leading zeroes and the plus sign may matter. Confirm data retention, privacy and access rules with the relevant stakeholders.

## 7. Process flow and exception handling

Happy path:
1. Patient signs in.
2. Patient chooses clinic and date.
3. System displays available slots.
4. Patient selects a slot and confirms details.
5. System checks availability again.
6. System creates booking and displays confirmation.

Exception paths:
- Patient is not signed in → request sign-in.
- No slots are available → show another date option.
- Slot becomes unavailable during confirmation → explain and refresh availability.
- Required details are missing → identify the fields.
- Confirmation service fails → show a safe message and avoid duplicate booking creation.

A good specification documents both the normal flow and important exceptions.

## 8. Follow-along: create a traceability chain

Use this simple chain:

Business need → Business requirement → Functional requirement → Acceptance criterion → Test case

Example:
- BN-01: Reduce calls to reception.
- BRQ-01: Patients must be able to self-book appointments.
- FR-02: The system shall show available slots for a chosen clinic and date.
- AC-02: Given a clinic and date with open slots, when the patient opens availability, then all bookable slots are displayed.
- TC-02: Select a clinic/date with 3 open slots; verify that exactly those 3 slots appear.

**Expected result:** Every requirement has a reason, an observable behaviour and a way to verify it.

## 9. Complete worked example

**Feature:** Appointment booking.

**Scope:** Authenticated patients can view available slots and create a booking. Online payments and doctor video calls are out of scope.

**Actors:** Patient, receptionist, booking system, notification service.

**Preconditions:** Patient account exists; clinic is active; booking calendar is configured.

**Main success scenario:** Patient signs in → selects clinic/date → selects slot → confirms details → system rechecks slot → booking is saved → confirmation is displayed and notification is requested.

**Postcondition:** One booking exists with a unique booking reference and Confirmed status.

**Acceptance criteria:**
1. Given a signed-in patient and an available slot, when all required details are valid and the patient confirms, then the system creates one confirmed booking.
2. Given a slot that has already been booked, when the patient attempts to confirm it, then the system rejects the booking and refreshes availability.
3. Given missing required information, when the patient submits, then the system identifies the missing field and does not create a booking.
4. Given a successful booking, when confirmation is displayed, then the booking reference and appointment details are visible.

## 10. Common mistakes and fixes

| Mistake | Why it is a problem | Fix |
|---|---|---|
| Writing solutions before understanding the need | May solve the wrong problem | Confirm the business objective first |
| Combining several behaviours in one requirement | Difficult to test and trace | Split into atomic requirements |
| Using vague language | Different readers interpret it differently | Add measurable conditions |
| Forgetting exception paths | Real users get stuck | Document alternate and failure flows |
| Treating assumptions as confirmed facts | Creates delivery risk | Label and validate assumptions |
| Missing requirement IDs | Change impact is hard to track | Use stable unique IDs |
| No acceptance criteria | “Done” becomes subjective | Define pass/fail outcomes |

## 11. Interview-ready revision

Remember:
- An FSD describes what the system should do and the rules it must follow.
- A business requirement explains the business need; a functional requirement describes system behaviour.
- An NFR describes quality attributes or operating conditions.
- Business rules express policy and decision logic.
- Acceptance criteria make completion testable.
- Traceability connects requirements to business goals and tests.
- Requirements should be clear, complete, consistent, feasible, necessary, verifiable and traceable.

### Interview questions

**Q1. What is a Functional Specification Document?**  
**Answer:** An FSD describes the expected behaviour of a system or feature in enough detail for stakeholders, developers and testers to share the same understanding. It commonly includes scope, actors, functional requirements, business rules, data validation, process flows, exceptions and acceptance criteria.  
**Example:** For appointment booking, it explains how patients view slots, confirm a booking and handle an unavailable slot.  
**Follow-up:** How is it different from a BRD? A BRD focuses on business needs and outcomes; an FSD gives more detail about system behaviour.

**Q2. How do you make a requirement testable?**  
**Answer:** I give it a unique ID, use precise language, state one observable behaviour and define the condition or expected outcome. I then add acceptance criteria that can be checked as pass or fail.  
**Example:** Replace “the page should load quickly” with a measurable response-time target agreed with stakeholders.  
**Follow-up:** Who confirms the target? The relevant business and technical stakeholders.

**Q3. What is requirement traceability and why is it useful?**  
**Answer:** Traceability links each requirement to its business source, design/build work and test evidence. It helps identify missing tests and understand which deliverables are affected by a change.  
**Example:** If cancellation policy BR-04 changes, the BA can identify the related functional requirement and test cases.

## 12. Mini-project — Functional Specification

**Approved project title:** Functional Specification  
**Time:** 45–75 minutes

### Problem
A small clinic currently accepts appointments by phone. Reception staff want a basic online booking feature. Your task is to write a concise, testable FSD for the first release.

### Workspace layout

Create this folder and files:

```text
Day_19_Functional_Specification/
├── README.md
├── inputs/
│   └── stakeholder_request.md
├── functional_specification.md
├── requirements_traceability.csv
├── acceptance_criteria.md
└── checker_checklist.md
```

Treat files under `inputs/` as read-only.

### Starter input — stakeholder_request.md

```text
We are a small clinic. Patients should sign in, choose a clinic date,
see available appointment slots, enter their details and confirm a booking.
We must not allow the same slot to be booked twice. Patients should see
a booking reference after successful confirmation.
For the first release, online payment is not required.
```

### Tasks

1. Write the purpose, scope and out-of-scope items.
2. Identify at least 2 actors and 1 external dependency.
3. Write at least 6 functional requirements with IDs FR-01 onward.
4. Write at least 4 business rules with IDs BR-01 onward. Mark any policy you need the clinic to confirm as **Pending confirmation**.
5. Define at least 5 data fields with type, mandatory status and validation.
6. Write the happy path and at least 3 exception paths.
7. Write at least 5 acceptance criteria in Given/When/Then format.
8. Create traceability rows linking business need → FR → acceptance criterion/test.

### Expected evidence

- One complete `functional_specification.md`.
- At least 6 atomic and testable functional requirements.
- At least 4 clearly labelled business rules.
- At least 5 acceptance criteria.
- Traceability links with no orphan functional requirements.
- Explicit scope, assumptions, constraints and open questions.

### Self-check / checker checklist

Mark each item Yes/No:
- [ ] Scope and exclusions are stated.
- [ ] Every requirement has a unique ID.
- [ ] Each requirement describes one observable behaviour.
- [ ] Vague words are defined or removed.
- [ ] Business rules are separated from assumptions.
- [ ] Pending business decisions are labelled.
- [ ] Required data and validation are documented.
- [ ] Happy path and exception paths are included.
- [ ] Acceptance criteria are testable.
- [ ] Every FR links to a business need and a test/criterion.

**Checker messages:** If a requirement cannot be tested, rewrite it with an observable result. If a policy has no stakeholder approval, mark it Pending confirmation. If a requirement has no traceability link, identify its business reason or remove it after review.

### Debugging hints

- Ask “What would the tester do to prove this?”
- Split sentences containing “and” if they describe separate behaviours.
- Do not assume cancellation, rescheduling or reminder rules unless stated; record them as open questions.
- Re-check that the no-double-booking rule is enforced at confirmation, not only when slots are first displayed.

### Extension

Add a change request: “The clinic wants patients to cancel up to 2 hours before an appointment.” Update the affected business rule, functional requirement, acceptance criteria and traceability row. Record the change in a small version history.

## 13. Five-question knowledge check

Choose one answer for each question. Answers and explanations are below so you can review after attempting.

1. Which statement is a functional requirement?  
   A. The system shall display available slots for a selected date.  
   B. The system should be attractive.  
   C. The project should finish this quarter.  
   D. The team should communicate daily.

2. What is the main purpose of an acceptance criterion?  
   A. Assign salaries  
   B. Define a verifiable condition for accepting a requirement  
   C. Replace stakeholder interviews  
   D. Choose a programming language

3. Which is an example of a business rule?  
   A. Use a blue button  
   B. A patient cannot book an already occupied slot  
   C. The developer uses Java  
   D. The document has 10 pages

4. What does traceability help a BA do?  
   A. Hide requirement changes  
   B. Link requirements to their business source and tests  
   C. Avoid stakeholder review  
   D. Guarantee zero defects

5. Which requirement is most testable?  
   A. The page should be fast.  
   B. Users should be happy.  
   C. The system shall show a booking reference after a successful booking.  
   D. Booking should be simple.

**Answer key:** 1-A (observable system behaviour); 2-B (defines pass/fail acceptance); 3-B (policy governing eligibility); 4-B (connects need, requirement and verification); 5-C (specific observable outcome).

## 14. Daily assessment and completion criteria

You have completed Day 19 when you can explain the difference between a business requirement, functional requirement, NFR and business rule; write six testable requirements; create acceptance criteria; and submit the Functional Specification project with traceability.

**Bridge to Day 20:** Once requirements are documented, a BA needs to measure whether the solution improves the business. Next: business metrics, KPIs, dimensions and measures.


---

## Visual references to add manually

Add the following visuals at the matching headings. Save each image using the exact filename shown so it is easy to locate later.

### 1. Functional specification document structure
- **Filename:** `day_19_concept_01_functional_specification_structure.png`
- **Insert under heading:** `## 3. Anatomy of a useful Functional Specification`
- **What it should show:** A document-structure diagram covering purpose/scope, stakeholders, functional requirements, business rules, data, flows, NFRs, acceptance criteria and approvals.
- **Search phrase:** `functional specification document structure diagram requirements sections`
- **Reference:** [Software Requirements Specification structure visual](https://www.docuwriter.ai/posts/how-to-write-software-requirements-specifications)

### 2. Requirements traceability
- **Filename:** `day_19_concept_02_requirements_traceability_matrix.png`
- **Insert under heading:** `## 8. Follow-along: create a traceability chain`
- **What it should show:** Business need → business requirement → functional requirement → acceptance criterion → test case, preferably as a traceability matrix or flow.
- **Search phrase:** `requirements traceability matrix business requirement functional requirement test case diagram`
- **Reference:** [Texas Project Delivery Framework — requirements specification guidance](https://dir.texas.gov/sites/default/files/2025-07/Requirements%20Traceability%20Matrix%20Instructions_July2025.pdf)

*Image note: use the reference to find or create a clear visual; check the source's reuse terms before copying it into published notes.*
