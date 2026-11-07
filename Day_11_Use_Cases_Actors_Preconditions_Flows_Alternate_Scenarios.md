# TechPhile.ai --- Business Analyst Career Pathway

# Day 11: Use Cases, Actors, Preconditions, Flows and Alternate Scenarios

**Phase:** 2 --- Requirements Engineering\
**Approved syllabus topic:** Use cases, actors, preconditions, flows and
alternate scenarios\
**Learning level:** Beginner to Intermediate\
**Estimated study time:** 2--3 hours\
**Prerequisites:** Days 6--10 --- Requirement types; elicitation,
interviews and questionnaires; workshops and other elicitation
techniques; requirement analysis and MoSCoW; user stories, acceptance
criteria and INVEST principles.

------------------------------------------------------------------------

## Learning objectives

By the end of this lesson, you should be able to:

1.  Explain what a use case is and why a BA documents one.
2.  Identify primary actors, supporting actors and external systems.
3.  Distinguish an actor from a stakeholder and from a user role.
4.  Define a use-case goal, trigger, preconditions and postconditions.
5.  Write a clear main success flow using numbered steps.
6.  Identify alternate flows, exception flows and failure conditions.
7.  Connect use cases with requirements, user stories and acceptance
    criteria.
8.  Review a use case for missing steps, unclear outcomes and unhandled
    scenarios.
9.  Document a use case in a consistent, readable format.

------------------------------------------------------------------------

# 1. Why use cases matter

Imagine a college is developing an online admission portal. A
requirement says:

> Applicants must be able to submit an admission application online.

This tells the team what capability is needed, but it does not explain
the complete interaction. The BA still needs to clarify:

-   Who starts the process?
-   What must the applicant do first?
-   What information must be entered?
-   Which fields are mandatory?
-   What happens if information is missing?
-   Does the applicant upload documents?
-   Is an application fee required?
-   How does the system confirm successful submission?
-   What happens if payment fails or the session expires?

A **use case** describes how an actor interacts with a system to achieve
a goal. It records the normal interaction and relevant alternative or
exception paths.

For example, the use case **Submit Admission Application** can describe
the interaction from the applicant opening the application form through
to receiving a submission reference.

A use case helps business stakeholders, analysts, designers, developers
and testers share the same understanding of a system capability.

### A simple view

``` text
Actor
  |
  | starts an interaction
  v
System responds
  |
  | actor provides information or makes a choice
  v
System validates and processes
  |
  +---- successful outcome
  |
  +---- alternative path
  |
  +---- exception / failure path
```

**Remember:** A use case describes a goal-oriented interaction. It is
not simply a list of screens, buttons or technical implementation tasks.

------------------------------------------------------------------------

# 2. Important terminology

  -----------------------------------------------------------------------
  Term                    Plain-English meaning   Example
  ----------------------- ----------------------- -----------------------
  Use case                Description of how an   Submit Admission
                          actor uses a system to  Application
                          achieve a goal          

  Actor                   A role or external      Applicant
                          system that interacts   
                          with the system         

  Primary actor           The actor who initiates Applicant
                          the use case to achieve 
                          a goal                  

  Supporting actor        An external role or     Payment gateway
                          system that helps the   
                          use case complete       

  Stakeholder             A person or group       Applicant, admissions
                          affected by or          manager
                          interested in the       
                          solution                

  System under            The system whose        Admission portal
  consideration           behavior is being       
                          described               

  Goal                    The result the actor    Submit a complete
                          wants to achieve        application

  Trigger                 The event that starts   Applicant selects
                          the use case            "Start application"

  Preconditions           Conditions that must be Applicant has signed in
                          true before the use     
                          case begins             

  Main success flow       The normal sequence     Enter details, upload
                          that achieves the goal  documents, submit

  Alternate flow          A valid variation from  Applicant saves a draft
                          the normal sequence     instead

  Exception flow          A path caused by an     Payment service is
                          error or condition that unavailable
                          prevents normal         
                          progress                

  Postconditions          Conditions or results   Application is recorded
                          expected after the use  with a reference
                          case ends               

  Include relationship    A reusable use case     Authenticate applicant
                          that is always required 
                          by another use case     

  Extend relationship     Additional or           Apply an optional
                          conditional behavior    discount
                          that may occur in a     
                          base use case           
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 3. What is a use case?

A use case is a structured description of interactions between an actor
and a system to achieve a specific goal.

It focuses on:

-   **Who** interacts with the system.
-   **Why** the actor interacts with it.
-   **What** the actor and system do.
-   **What conditions** must be satisfied.
-   **What happens** when the normal path changes.
-   **What outcome** exists when the interaction ends.

### Example

**Use case:** View Application Status

-   Primary actor: Applicant
-   Goal: Find out the current status of a submitted application.
-   Trigger: Applicant chooses "Application Status".
-   Preconditions: Applicant is signed in and has a submitted
    application.
-   Main success outcome: The portal displays the applicant's current
    application status.
-   Alternate outcome: If no application has been submitted, the portal
    explains that no submitted application is available.

### What a use case is not

  -----------------------------------------------------------------------
  It is not...            Why?                    Better description
  ----------------------- ----------------------- -----------------------
  A screen design         Screens show layout,    Use case plus wireframe
                          not the complete        where needed
                          interaction             

  A single user story     A story is a short      Use case describes
                          statement of need       interaction steps and
                                                  paths

  A task list for         Tasks describe          Use case describes
  developers              implementation work     observable system
                                                  behavior

  A flowchart by itself   A flowchart visualizes  Use case text documents
                          a process               actor-system
                                                  interaction

  A technical design      It does not prescribe   Keep implementation
                          internal code or        design separate unless
                          architecture            required
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 4. Actors

## 4.1 What is an actor?

An actor is a role played by a person, organization or external system
that interacts with the system being analyzed.

An actor is defined by its interaction with the system, not by the
person's name.

For example, "Applicant" is an actor. Karthik or any individual
applicant is not normally the actor name in a use-case model.

### Common actor examples

  -----------------------------------------------------------------------
  System                              Possible actors
  ----------------------------------- -----------------------------------
  College admission portal            Applicant, admissions officer,
                                      payment gateway

  Banking application                 Customer, bank employee, identity
                                      verification service

  E-commerce website                  Customer, warehouse system, payment
                                      gateway, delivery service

  Hospital appointment system         Patient, receptionist, doctor,
                                      notification service

  Employee leave system               Employee, manager, HR system
  -----------------------------------------------------------------------

## 4.2 Primary actor

The primary actor initiates the use case to achieve a goal.

Example:

A customer starts **Transfer Funds** because they want to move money
from one account to another.

The customer is the primary actor.

Ask: **Who starts this interaction because they want a result?**

## 4.3 Supporting actor

A supporting actor provides a service or information that helps the use
case complete.

Example:

During an online payment:

-   The applicant initiates the application submission.
-   The admission portal sends a payment request to a payment gateway.
-   The payment gateway returns a success or failure response.

The payment gateway is a supporting actor.

## 4.4 External system as an actor

An external system can be an actor when it interacts with the system
being described.

Examples:

-   Payment gateway
-   Email notification service
-   Identity verification service
-   Credit bureau
-   Inventory management system

The external system is outside the boundary of the system under
consideration.

## 4.5 Actor versus stakeholder

These terms are related but not identical.

  -----------------------------------------------------------------------
  Actor                               Stakeholder
  ----------------------------------- -----------------------------------
  Interacts directly with the system  Has an interest in, is affected by,
  in the use case                     or can influence the change

  Defined by interaction and role     Defined by interest, impact or
                                      responsibility

  May be a person or external system  Usually a person, group or
                                      organization

  Example: Applicant                  Example: College sponsor
  -----------------------------------------------------------------------

A college sponsor may be a stakeholder without directly using the
admission portal. An applicant is both a stakeholder and an actor when
using the portal.

## 4.6 How to identify actors

Use this practical method:

1.  Identify the system being analyzed.
2.  List people or external systems that interact with it.
3.  Ask who initiates each interaction.
4.  Ask which external services provide information or perform
    supporting actions.
5.  Group people by role rather than by individual name.
6.  Confirm the list with relevant stakeholders.

### Actor identification example: admission portal

  -----------------------------------------------------------------------
  Candidate               Actor?                  Reason
  ----------------------- ----------------------- -----------------------
  Applicant               Yes                     Enters and submits an
                                                  application

  Admissions officer      Yes                     Reviews applications in
                                                  the portal

  Payment gateway         Yes                     Exchanges payment
                                                  requests and responses

  College principal       Depends                 Actor only if they
                                                  interact with the
                                                  portal

  Portal database         Usually no              Internal component of
                                                  the system, not an
                                                  external actor

  Developer               Usually no              Builds the system; not
                                                  a business actor in
                                                  normal use
  -----------------------------------------------------------------------

**Important:** A database or internal software module is not
automatically an actor. The actor is normally outside the system
boundary.

------------------------------------------------------------------------

# 5. System boundary and use-case scope

The system boundary defines what is inside the system being described
and what is outside it.

For an admission portal:

**Inside the boundary:** - Application form management - Input
validation - Document upload - Application record creation - Application
status display

**Outside the boundary:** - Applicant - Payment gateway - External email
service - External identity verification provider

A clear boundary prevents confusion about which system is responsible
for each behavior.

### Boundary questions for a BA

-   Which product or application are we describing?
-   Which functions belong to this system?
-   Which services are external?
-   Which actions are performed manually by people?
-   Are we describing the entire organization or only one application?

Do not label internal components as external actors merely because they
are separate technical modules.

------------------------------------------------------------------------

# 6. Use-case goals and triggers

## 6.1 Goal

The goal is the meaningful result the actor wants.

Weak use-case names: - Click Submit - Open Page - Enter Details

Better use-case names: - Submit Admission Application - View Application
Status - Pay Application Fee - Review Submitted Application

A useful use-case name normally starts with a verb and describes an
outcome.

## 6.2 Trigger

A trigger is the event that starts the use case.

Examples:

  -----------------------------------------------------------------------
  Use case                            Trigger
  ----------------------------------- -----------------------------------
  Submit Admission Application        Applicant selects "Submit
                                      application"

  Reset Password                      User selects "Forgot password"

  Book Appointment                    Patient selects an available
                                      appointment slot

  Approve Leave Request               Manager opens a pending request and
                                      chooses "Approve"
  -----------------------------------------------------------------------

A trigger is not the same as a precondition.

-   Trigger: What starts the interaction?
-   Precondition: What must already be true before it starts?

------------------------------------------------------------------------

# 7. Preconditions and postconditions

## 7.1 Preconditions

A precondition is a condition that must be true before the use case
begins.

Examples: - Applicant is signed in. - Applicant has an active
application draft. - Customer has a valid account. - Manager is
authorized to approve leave requests.

A precondition should not describe a step that the use case itself
performs.

For example:

-   "Applicant is signed in" can be a precondition if authentication
    happens before this use case.
-   "Applicant enters username and password" is an interaction step, not
    a precondition, when login is part of the use case.

### How to write a precondition

Ask:

1.  What must already exist?
2.  What must already have happened?
3.  What permissions or status are necessary?
4.  What must be true before the first use-case step?

Avoid vague preconditions such as "The system is ready" unless "ready"
is defined.

## 7.2 Postconditions

Postconditions describe the state or result expected when the use case
ends.

Two useful categories:

-   **Success postcondition:** What is true when the goal is achieved?
-   **Minimal guarantee:** What must remain true even if the use case
    fails or ends early?

Example --- Submit Admission Application:

**Success postconditions** - The application is stored. - A unique
application reference is assigned. - The application status is set to
the agreed initial status. - A confirmation is displayed to the
applicant.

**Failure/minimal guarantee** - An incomplete or unsuccessful submission
is not incorrectly recorded as a successfully submitted application. -
Any entered draft information is retained only according to the agreed
save and recovery rules.

The BA should confirm data-retention behavior with stakeholders rather
than assume it.

## 7.3 Preconditions versus postconditions

  -----------------------------------------------------------------------
  Preconditions                       Postconditions
  ----------------------------------- -----------------------------------
  True before the use case starts     Expected after the use case ends

  Establish starting conditions       Establish resulting conditions

  Example: User is authenticated      Example: Password is reset

  Example: Application draft exists   Example: Application is submitted
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 8. Main success flow

The **main success flow** (also called the basic flow or happy path)
describes the normal sequence in which the actor achieves the goal
without errors or deviations.

A good flow alternates between actor actions and system responses where
appropriate.

### Example: Submit Admission Application

**Use case ID:** UC-01\
**Use case name:** Submit Admission Application\
**Primary actor:** Applicant\
**Supporting actor:** Payment gateway\
**Goal:** Submit a complete admission application.\
**Trigger:** Applicant selects "Submit application".\
**Preconditions:** 1. Applicant is signed in. 2. An active application
draft exists. 3. The selected admission program is open for
applications.

**Main success flow:**

  ------------------------------------------------------------------------
                          Step Actor action          System response
  ---------------------------- --------------------- ---------------------
                             1 Applicant opens the   Portal displays the
                               active application    saved application
                               draft.                details.

                             2 Applicant reviews     Portal displays the
                               personal and academic current values.
                               information.          

                             3 Applicant enters or   Portal accepts the
                               updates required      entered values.
                               information.          

                             4 Applicant uploads the Portal checks file
                               required documents.   type and size against
                                                     configured rules and
                                                     displays upload
                                                     status.

                             5 Applicant selects     Portal validates
                               "Continue".           required fields and
                                                     document presence.

                             6 Applicant reviews the Portal displays the
                               application summary.  information for final
                                                     confirmation.

                             7 Applicant confirms    Portal sends a
                               submission and        payment request to
                               proceeds to payment,  the payment gateway.
                               if a fee applies.     

                             8 Payment gateway       Portal records the
                               returns a successful  payment result and
                               payment response.     completes the
                                                     submission according
                                                     to the agreed
                                                     business rules.

                             9 Applicant views the   Portal displays the
                               confirmation.         application reference
                                                     and current status.
  ------------------------------------------------------------------------

**Success postconditions:** - The application has been recorded as
submitted. - The application has a unique reference. - The payment
result is recorded when payment is required. - The applicant can view
the confirmation.

**Documentation note:** This example assumes the program requires a fee
and that payment must succeed before submission is completed. If the
actual business policy differs, the BA must update the flow.

## 8.1 How to write good flow steps

A clear step should:

-   Describe one meaningful action or response.
-   Identify who performs it.
-   Use simple, observable language.
-   Avoid unnecessary technical implementation details.
-   Keep actor actions separate from system responses where useful.
-   Avoid combining several unrelated actions in one step.

Weak step:

> The system processes everything and completes the application.

Improved steps:

1.  The system validates mandatory fields.
2.  The system checks the uploaded documents against the configured file
    rules.
3.  The system creates the application record after all required
    conditions are satisfied.
4.  The system displays the application reference.

------------------------------------------------------------------------

# 9. Alternate flows

An alternate flow describes a valid variation from the main success
flow. It may still allow the actor to achieve the goal, or it may lead
to a different valid outcome.

Examples: - Applicant saves the application as a draft instead of
submitting. - Applicant chooses a different payment method. - Applicant
returns to edit details before final submission. - Applicant selects a
program with no application fee.

### Example: Save application as draft

**Related main flow step:** Step 6 --- Applicant reviews the application
summary.

1.  Applicant chooses "Save as draft" instead of "Submit".
2.  Portal validates the information required for saving a draft.
3.  Portal saves the current information as a draft.
4.  Portal displays a draft-saved confirmation.
5.  Use case ends without submitting the application.

**Outcome:** The application remains a draft. It is not treated as
submitted.

### Example: Applicant edits information

**Related main flow step:** Step 6 --- Applicant reviews the application
summary.

1.  Applicant identifies incorrect information.
2.  Applicant chooses "Edit".
3.  Portal returns the applicant to the relevant section.
4.  Applicant updates the information.
5.  Portal validates the updated values.
6.  Applicant returns to the summary and continues the main flow.

Alternate flows should be connected to the relevant main-flow step so
that readers understand where the variation occurs.

------------------------------------------------------------------------

# 10. Exception flows

An exception flow describes an error, failure or unexpected condition
that interrupts the normal path.

Examples: - Payment gateway does not respond. - Uploaded file is not an
allowed format. - Session expires before submission. - Application
deadline has passed. - The system cannot save the application.

### Example: Payment fails

**Related main flow step:** Step 8 --- Payment gateway returns a
successful response.

1.  Payment gateway returns a failed or declined payment response.
2.  Portal records the payment outcome according to the agreed
    payment-handling rules.
3.  Portal informs the applicant that payment was not successful.
4.  Portal does not display a successful payment confirmation.
5.  Portal provides the permitted next action, such as retrying or
    choosing another payment method.
6.  The use case resumes at the agreed payment step or ends with an
    unsuccessful payment outcome.

**Important:** The exact treatment of failed payments, retries,
duplicate payment attempts and refunds must be confirmed with the
business and payment teams.

### Example: Session expires

1.  Applicant remains inactive until the session expires.
2.  Portal ends the authenticated session.
3.  Portal informs the applicant that the session has expired.
4.  Portal asks the applicant to sign in again.
5.  After successful authentication, the applicant may resume only if
    the application recovery rules allow it.

### Alternate flow versus exception flow

  -----------------------------------------------------------------------
  Alternate flow                      Exception flow
  ----------------------------------- -----------------------------------
  A valid variation in the            An error or unexpected condition
  interaction                         

  May still achieve the main goal     Often interrupts or prevents the
                                      main goal

  Example: Save as draft              Example: System cannot save draft

  Example: Choose another valid       Example: Payment service is
  payment method                      unavailable
  -----------------------------------------------------------------------

Some organizations use "alternate flow" broadly to include all non-happy
paths. The important practice is to label and describe each path clearly
so readers understand whether it is a valid variation or an error
condition.

------------------------------------------------------------------------

# 11. Writing alternate and exception flows clearly

Use this sequence:

1.  Identify the main-flow step where the path branches.
2.  Give the path a clear name.
3.  State the condition that causes it.
4.  Number the actor and system steps.
5.  State whether the path returns to the main flow, continues elsewhere
    or ends.
6.  State the outcome and any data or status changes.
7.  Confirm the path with the relevant stakeholder.

### Flow reference example

``` text
Main flow
   |
   v
Step 8: Payment response received
   |
   +---- Success ----> Continue to confirmation
   |
   +---- Payment declined ----> Show failure and allow permitted retry
   |
   +---- Gateway unavailable -> Show service error and preserve safe state
```

A flow is incomplete if it describes an error message but does not
explain what happens next.

------------------------------------------------------------------------

# 12. A complete use-case template

Use a consistent template for documentation. Not every project needs
every field, but the template helps identify missing information.

  Field                        What to record
  ---------------------------- ---------------------------------------------------
  Use case ID                  Unique identifier, such as UC-01
  Use case name                Verb + goal, such as Submit Admission Application
  Description                  Short explanation of the goal
  Scope/system                 System being described
  Primary actor                Actor who initiates the use case
  Supporting actors            External roles or systems involved
  Stakeholders and interests   Relevant stakeholder expectations
  Trigger                      Event that starts the use case
  Preconditions                Conditions that must already be true
  Main success flow            Normal actor-system interaction
  Alternate flows              Valid variations
  Exception flows              Error and failure paths
  Success postconditions       State after successful completion
  Minimal guarantees           What remains true if the use case fails
  Business rules               Policies or rules affecting the interaction
  Assumptions                  Conditions not yet confirmed
  Open questions               Details requiring stakeholder clarification
  Priority/status              Agreed priority and documentation status

### Documentation quality checklist

Before sharing a use case, check:

-   Is the goal meaningful to the actor?
-   Is the primary actor correct?
-   Is the system boundary clear?
-   Is the trigger specific?
-   Are preconditions genuinely true before the interaction?
-   Does the main flow reach the goal?
-   Are system responses included?
-   Are alternate and exception paths covered where relevant?
-   Are outcomes and data changes clear?
-   Are unresolved assumptions and questions visible?
-   Can a tester derive test scenarios from the flow?

------------------------------------------------------------------------

# 13. Use-case relationships: include and extend

These relationships are useful when documenting larger systems.
Understand the basic idea before using them; do not add them merely to
make a diagram look complex.

## 13.1 Include relationship

An **include** relationship represents behavior that a base use case
always uses as part of its execution. It is useful when a common
required interaction is reused by multiple use cases.

Example:

-   Submit Admission Application includes Authenticate Applicant.
-   View Application Status includes Authenticate Applicant.

If authentication is required every time these use cases run, it may be
documented as shared included behavior.

**Remember:** Include means the referenced behavior is required in the
base use case, not an optional possibility.

## 13.2 Extend relationship

An **extend** relationship represents additional behavior that occurs
under a condition or at an extension point.

Example:

-   Apply Fee Waiver may extend Pay Application Fee when the applicant
    qualifies for a waiver and the business policy permits it.

**Remember:** Extend is conditional additional behavior. The base use
case can be understood without assuming the extension always occurs.

## 13.3 Include versus extend

  -----------------------------------------------------------------------
  Include                             Extend
  ----------------------------------- -----------------------------------
  Required reused behavior            Conditional additional behavior

  Base use case uses the included     Extension adds behavior at a
  behavior                            defined condition

  Example: Authenticate applicant     Example: Apply eligible fee waiver

  Helps avoid repeating common        Helps represent optional or
  mandatory steps                     conditional behavior
  -----------------------------------------------------------------------

Do not confuse these relationships with ordinary step references in
textual use cases. Use them only when they make the model clearer.

------------------------------------------------------------------------

# 14. Use cases, user stories and acceptance criteria

These techniques describe requirements from different angles and can
complement each other.

  -----------------------------------------------------------------------
  Item                    Main focus              Example
  ----------------------- ----------------------- -----------------------
  Functional requirement  Capability the solution The portal must allow
                          must provide            applicants to submit
                                                  applications

  User story              User need and benefit   As an applicant, I want
                                                  to submit my
                                                  application so that I
                                                  can apply for admission

  Acceptance criteria     Conditions for          A complete application
                          accepting the story     is recorded and a
                                                  reference is displayed

  Use case                Interaction steps and   Applicant reviews
                          possible paths          details, uploads
                                                  documents, submits and
                                                  receives confirmation

  Test case               Specific steps and      Submit a valid
                          expected result used    application and verify
                          for testing             that a reference is
                                                  generated
  -----------------------------------------------------------------------

### How they fit together

``` text
Business need
     |
     v
Requirement / capability
     |
     v
User story and acceptance criteria
     |
     v
Use case: actor, trigger, preconditions and flows
     |
     v
Test scenarios and test cases
     |
     v
Validation of the delivered behavior
```

A user story does not automatically replace a use case. A short story
may be sufficient for a small feature, while a complex interaction with
multiple actors and exceptions may need detailed use-case documentation.

------------------------------------------------------------------------

# 15. Worked scenario: Online admission portal

Consider a college that wants applicants to submit applications online.

## 15.1 Business context

The college currently receives paper applications. Staff manually check
forms and documents. Applicants contact the admissions office to ask
whether their applications were received.

The proposed portal should allow applicants to submit applications and
receive a reference.

## 15.2 Identify the use case

**Use case:** Submit Admission Application

**Primary actor:** Applicant

**Supporting actor:** Payment gateway, if a fee is required

**Stakeholders:** Applicant, admissions team, finance team, college
management

**Goal:** Submit an application for an open admission program.

**Trigger:** Applicant selects the submit action after reviewing the
application.

**Preconditions:** 1. Applicant is authenticated. 2. Applicant has an
active draft. 3. The admission program is accepting applications.

## 15.3 Main success flow

1.  Applicant opens the active draft.
2.  Portal displays saved application information.
3.  Applicant completes required fields.
4.  Applicant uploads required documents.
5.  Applicant selects Continue.
6.  Portal validates required information and document rules.
7.  Portal displays an application summary.
8.  Applicant confirms the submission.
9.  If a fee applies, portal requests payment through the payment
    gateway.
10. Payment gateway returns a successful response.
11. Portal records the successful payment and completes the submission.
12. Portal generates an application reference.
13. Portal displays the confirmation and current status.

## 15.4 Alternate scenarios

**A. Applicant saves a draft** - Applicant chooses Save as Draft. -
Portal saves the available information. - Portal confirms that the draft
was saved. - No submitted status or final application reference is
presented as a successful submission.

**B. Applicant corrects details** - Applicant chooses Edit from the
summary. - Portal opens the relevant section. - Applicant changes the
information. - Portal validates the updated information. - Applicant
returns to the summary.

## 15.5 Exception scenarios

**C. Required field is missing** - Portal identifies the missing
field. - Portal prevents progression to final submission. - Portal
displays a clear message. - Applicant completes the missing information
and retries.

**D. Document format is not accepted** - Portal rejects the file. -
Portal explains the permitted file format or relevant rule. - Applicant
uploads an acceptable file.

**E. Payment is declined** - Portal informs the applicant that payment
did not succeed. - Portal follows the agreed payment and retry policy. -
The application is not incorrectly marked as successfully paid.

**F. Admission deadline has passed** - Portal checks the program's
application window. - Portal informs the applicant that submission is
unavailable. - Portal does not accept a late application unless an
authorized exception process exists.

## 15.6 Open questions a BA should raise

1.  Is payment mandatory for every admission program?
2.  At what exact point is the application considered submitted?
3.  Can applicants submit without all documents if they provide them
    later?
4.  Which file formats and maximum file sizes are permitted?
5.  How many payment retries are allowed?
6.  What happens if payment succeeds but the portal does not receive the
    response?
7.  Can an applicant edit an application after submission?
8.  What happens when the deadline passes while an applicant is
    completing the form?
9.  How long should draft information be retained?
10. Which status should appear immediately after successful submission?

These questions demonstrate an important BA habit: document what is
known, identify what is uncertain and obtain confirmation instead of
inventing business rules.

------------------------------------------------------------------------

# 16. Common use-case documentation mistakes

  -----------------------------------------------------------------------
  Mistake                 Why it causes problems  Better approach
  ----------------------- ----------------------- -----------------------
  Naming a use case after Describes a UI action   Use a goal-oriented
  a button                rather than an actor    verb phrase
                          goal                    

  Treating every          Some stakeholders never Confirm actual
  stakeholder as an actor interact with the       interaction
                          system                  

  Listing internal        Confuses system         Define the system
  databases as actors     internals with external boundary
                          participants            

  Missing preconditions   Readers cannot tell     State required starting
                          when the interaction    conditions
                          can start               

  Writing only actor      System behavior and     Include actor and
  actions                 responses are missing   system steps

  Writing a vague main    Developers and testers  Use specific,
  flow                    interpret it            observable steps
                          differently             

  Ignoring alternate      Valid user choices are  Identify meaningful
  flows                   missed                  variations

  Ignoring exceptions     Error handling remains  Document relevant
                          undefined               failure paths

  Mixing business rules   Unconfirmed details may Label confirmed rules
  with assumptions        be treated as facts     and open assumptions

  Prescribing technical   Limits the solution     Describe required
  design                  before analysis is      behavior, not internal
                          complete                code

  Over-documenting        Makes the use case hard Focus on meaningful
  trivial details         to read                 actor-system
                                                  interactions
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 17. Interview questions and answers

## Q1. What is a use case?

**Answer:**\
A use case describes how an actor interacts with a system to achieve a
specific goal. It includes the trigger, preconditions, main flow,
alternate or exception flows and expected outcomes.

**Example:** An applicant uses an admission portal to submit an
application.

## Q2. What is an actor in a use case?

**Answer:**\
An actor is a role played by a person or external system that interacts
with the system being analyzed. An actor is defined by its role, not by
an individual's name.

**Example:** Applicant, admissions officer or payment gateway.

## Q3. What is the difference between a primary actor and a supporting actor?

**Answer:**\
The primary actor initiates the use case to achieve a goal. A supporting
actor provides a service or information that helps the use case
complete.

**Example:** The applicant initiates an application submission; the
payment gateway supports payment processing.

## Q4. Can an external system be an actor?

**Answer:**\
Yes. An external system is an actor when it interacts with the system
under consideration. Examples include payment gateways, identity
verification services and notification services.

## Q5. What is the difference between an actor and a stakeholder?

**Answer:**\
An actor interacts with the system in a use case. A stakeholder has an
interest in, is affected by or can influence the change. A person can be
both, but not every stakeholder is an actor.

## Q6. What is a precondition?

**Answer:**\
A precondition is a condition that must already be true before a use
case begins.

**Example:** The applicant is signed in and has an active application
draft.

## Q7. What is a postcondition?

**Answer:**\
A postcondition describes the state or result expected after the use
case ends.

**Example:** After successful submission, the application is recorded
and has a unique reference.

## Q8. What is the main success flow?

**Answer:**\
It is the normal sequence of actor actions and system responses through
which the actor achieves the use-case goal without deviations or errors.

## Q9. What is the difference between an alternate flow and an exception flow?

**Answer:**\
An alternate flow describes a valid variation from the normal path, such
as saving a draft. An exception flow describes an error or unexpected
condition, such as a failed payment or unavailable service.

## Q10. Why should a BA document exception flows?

**Answer:**\
They make failure behavior explicit. Without them, teams may implement
inconsistent error handling, lose user data or disagree about what
should happen when a process cannot continue.

## Q11. What is the difference between include and extend?

**Answer:**\
Include represents behavior that is always required and reused by a base
use case. Extend represents conditional additional behavior that occurs
at a defined point when its condition is met.

## Q12. How is a use case different from a user story?

**Answer:**\
A user story briefly describes a need from a user's perspective, often
using role, goal and benefit. A use case describes the interaction in
more detail, including actors, preconditions, steps and alternate or
exception paths.

## Q13. How do you identify missing steps in a use case?

**Answer:**\
I review the actor's goal from start to finish, check every actor action
and system response, identify decisions and data validations, and ask
what happens when a condition is not met. I also confirm the flow with
stakeholders and check whether testers can derive meaningful scenarios.

## Q14. What would you do if two stakeholders describe different process flows?

**Answer:**\
I would document both versions, identify where they differ, understand
whether the difference is caused by role, policy, location or an
exception, and validate the correct business rule with the process owner
or authorized decision-maker. I would not choose one version without
evidence or authority.

## Q15. How detailed should a use case be?

**Answer:**\
It should be detailed enough for stakeholders and delivery teams to
understand the interaction, expected behavior and important variations.
The level of detail depends on complexity, risk, project approach and
team needs. Avoid both vague descriptions and unnecessary implementation
detail.

------------------------------------------------------------------------

# 18. Knowledge check

Try answering before checking the solutions.

1.  A customer starts a fund transfer. A payment service validates the
    transaction. Identify the primary actor and supporting actor.
2.  A manager is interested in a new HR system but never uses it. Is the
    manager necessarily an actor? Explain.
3.  For "Reset Password", write one possible trigger and one
    precondition.
4.  What is the difference between a trigger and a precondition?
5.  For "Submit Admission Application", write two suitable
    preconditions.
6.  Write one success postcondition for a successfully submitted
    application.
7.  Is "Applicant saves the form as a draft" an alternate flow or an
    exception flow? Why?
8.  Is "Payment gateway is unavailable" an alternate flow or an
    exception flow? Why?
9.  Why should a main success flow include system responses?
10. Explain include and extend in one or two sentences each.
11. Why is a database normally not an actor in a use case for the
    application that owns it?
12. A use case says "The system processes the request." What is missing,
    and how would you improve it?

## Suggested answers

1.  Primary actor: customer. Supporting actor: payment service, if it is
    external to the system being described.
2.  Not necessarily. The manager is a stakeholder because they are
    interested in the change, but is an actor only if they interact with
    the system in the use case.
3.  Trigger: User selects "Forgot password". Possible precondition: A
    user account exists. The exact preconditions depend on the system's
    account-recovery policy.
4.  A trigger is the event that starts the use case. A precondition is
    something that must already be true before it starts.
5.  Applicant is authenticated; an active application draft exists.
    Other conditions may apply depending on the business rules.
6.  The application is stored with submitted status and a unique
    reference is generated.
7.  Alternate flow. It is a valid user choice that saves progress but
    does not complete submission.
8.  Exception flow. It is an unexpected service failure that prevents
    the normal payment interaction.
9.  They explain how the system responds to actor actions, making
    expected behavior clearer and supporting development and testing.
10. Include is mandatory reusable behavior used by a base use case.
    Extend is conditional additional behavior that occurs when a defined
    condition is met.
11. The database is generally an internal component within the system
    boundary, not an external role interacting with the system.
12. The step is vague. State the actual validation or processing
    behavior, the result, and what the system displays or records.

------------------------------------------------------------------------

# 19. Quick revision sheet

  -----------------------------------------------------------------------
  Concept                             Remember
  ----------------------------------- -----------------------------------
  Use case                            Actor-system interaction to achieve
                                      a goal

  Actor                               External role or system interacting
                                      with the system

  Primary actor                       Initiates the use case to achieve a
                                      goal

  Supporting actor                    Helps the use case complete

  Stakeholder                         Interested in, affected by or able
                                      to influence the change

  System boundary                     Defines what is inside and outside
                                      the system

  Goal                                Result the actor wants

  Trigger                             Event that starts the use case

  Preconditions                       Conditions true before the use case
                                      starts

  Main success flow                   Normal path to achieve the goal

  Alternate flow                      Valid variation from the main flow

  Exception flow                      Error or unexpected path

  Postconditions                      Expected result or state after the
                                      use case ends

  Include                             Required reusable behavior

  Extend                              Conditional additional behavior
  -----------------------------------------------------------------------

### The key sequence

``` text
USE CASE
   |
   +-- Name and goal
   |
   +-- Actors
   |
   +-- Trigger
   |
   +-- Preconditions
   |
   +-- Main success flow
   |
   +-- Alternate flows
   |
   +-- Exception flows
   |
   +-- Postconditions
```

### A simple memory aid

-   **Actor:** Who interacts?
-   **Goal:** What do they want?
-   **Trigger:** What starts it?
-   **Precondition:** What must already be true?
-   **Main flow:** What normally happens?
-   **Alternate flow:** What valid variation can happen?
-   **Exception flow:** What can go wrong?
-   **Postcondition:** What is true at the end?

------------------------------------------------------------------------

# 20. Day 11 completion checklist

-   [ ] I can explain a use case in plain English.
-   [ ] I can identify primary and supporting actors.
-   [ ] I can distinguish actors from stakeholders.
-   [ ] I can identify external systems that act as actors.
-   [ ] I can define a system boundary.
-   [ ] I can write a goal-oriented use-case name.
-   [ ] I can distinguish a trigger from a precondition.
-   [ ] I can write suitable preconditions and postconditions.
-   [ ] I can document a numbered main success flow.
-   [ ] I can identify alternate flows and connect them to main-flow
    steps.
-   [ ] I can document exception flows and explain their outcomes.
-   [ ] I understand the basic difference between include and extend.
-   [ ] I can explain how use cases relate to user stories and
    acceptance criteria.
-   [ ] I can identify missing details and record open questions rather
    than guessing.
-   [ ] I can answer the interview questions in my own words.

------------------------------------------------------------------------

**Day 11 complete --- Use Cases, Actors, Preconditions, Flows and
Alternate Scenarios.**

**Next syllabus topic --- Day 12: Requirement Traceability, Validation,
Sign-off and Change Management.**
