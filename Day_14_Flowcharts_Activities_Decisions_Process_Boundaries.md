# Day 14 --- Flowcharts, Activities, Decisions and Process Boundaries

**Phase:** 3 --- Process Modeling and Documentation\
**Approved syllabus topic:** Flowcharts, activities, decisions and
process boundaries\
**Learning level:** Beginner to advanced\
**Study focus:** Class notes and interview preparation only

------------------------------------------------------------------------

## 1. Learning objectives

By the end of this lesson, you should be able to:

-   Explain what a flowchart is and when a BA uses one.
-   Understand common flowchart symbols and their meanings.
-   Identify process start and end points, activities, decisions, inputs
    and outputs.
-   Represent sequence, branching, merging and loops.
-   Define process boundaries before drawing a flowchart.
-   Convert a written business scenario into a logical flow.
-   Create clear, readable flowcharts using consistent conventions.
-   Recognize common flowchart mistakes and correct them.
-   Review a flowchart with stakeholders and check its completeness.
-   Explain flowchart concepts confidently in a BA interview.

## 2. What is a flowchart?

A **flowchart** is a visual representation of the steps in a process and
the order in which those steps occur. It uses standard shapes and arrows
to show activities, decisions, inputs, outputs and the direction of
flow.

A flowchart answers questions such as:

-   What starts the process?
-   What happens first, next and last?
-   Who or what performs an activity?
-   Where is a decision made?
-   What happens for each possible decision outcome?
-   Where does the process end?

### Simple example --- login

1.  User enters username and password.
2.  System checks the credentials.
3.  If they are correct, the user reaches the dashboard.
4.  If they are incorrect, the system displays an error.
5.  The user can try again or stop.

A flowchart makes these paths easier to understand than a long
paragraph.

## 3. Why Business Analysts use flowcharts

  -----------------------------------------------------------------------
  Purpose                             Practical benefit
  ----------------------------------- -----------------------------------
  Understand a process                Converts written descriptions into
                                      a visual sequence

  Communicate                         Helps business and technical teams
                                      discuss the same process

  Identify missing steps              Makes gaps and unclear transitions
                                      visible

  Analyze decisions                   Shows conditions and possible
                                      outcomes

  Identify rework                     Makes repeated paths and loops
                                      visible

  Clarify boundaries                  Shows where the process begins and
                                      ends

  Support requirements                Reveals system actions, rules and
                                      alternate paths

  Support testing                     Helps identify scenarios that need
                                      test coverage

  Support improvement                 Helps stakeholders discuss
                                      unnecessary steps and delays
  -----------------------------------------------------------------------

A flowchart describes process logic. It does not automatically prove
that the process is efficient or correct.

## 4. Basic flowchart symbols

A flowchart uses shapes to represent different kinds of process
elements. Follow the notation agreed by the organization or project. The
symbols below are common conventional flowchart symbols.

### 4.1 Terminator --- Start / End

```{=html}
<pre>
  ┌──────────────────┐
  │   Start / End    │
  └──────────────────┘
</pre>
```
-   Usually drawn as an oval or rounded rectangle.
-   Marks the beginning or completion of a process or defined process
    segment.
-   A process may have one start and multiple legitimate end points.
-   Use meaningful labels such as "Application submitted" or
    "Application closed."

### 4.2 Process --- Activity / Action

```{=html}
<pre>
  ┌──────────────────┐
  │  Verify details  │
  └──────────────────┘
</pre>
```
-   Drawn as a rectangle.
-   Represents work performed by a person or system.
-   Use a short action phrase: verb + object.
-   Examples: "Check documents", "Calculate total", "Send notification".

Avoid vague labels such as "Processing" or "Work".

### 4.3 Decision

```{=html}
<pre>
       /\
      /  \
     / Is  \
     \ valid? /
      \    /
       \/
</pre>
```
-   Drawn as a diamond.
-   Represents a question or condition that determines which path is
    followed.
-   Label it as a clear question.
-   Label outgoing paths with outcomes such as Yes/No, Valid/Invalid or
    Approved/Rejected.

A decision with two outcomes should normally show both possible
branches.

### 4.4 Input / Output

```{=html}
<pre>
    __________________
   / Enter applicant  /
  / details          /
 /__________________/
</pre>
```
-   Commonly drawn as a parallelogram.
-   Represents information entering or leaving a process.
-   Examples: "Receive application", "Display confirmation", "Generate
    invoice".

### 4.5 Flow line / Arrow

```{=html}
<pre>
  [Receive request] ───────> [Check request]
</pre>
```
-   Shows the direction in which the process moves.
-   Use arrowheads consistently.
-   Avoid ambiguous lines that appear to connect to the wrong shape.

### 4.6 Connector

A small circle may be used as an on-page connector to link separated
parts of a flowchart.

Use matching labels such as A and A. A connector is useful when long
lines would make the diagram difficult to read.

### 4.7 Off-page connector

A pentagon-like connector is commonly used to indicate that the flow
continues on another page or diagram.

Label the destination clearly, such as "Continue on page 2 ---
Verification".

### 4.8 Predefined process / Subprocess

```{=html}
<pre>
  ║──────────────────║
  ║ Verify documents ║
  ║──────────────────║
</pre>
```
-   Commonly represented by a rectangle with additional vertical lines
    near its sides.
-   Represents a process that is defined in more detail elsewhere.
-   Useful when a diagram would become too large if every internal step
    were shown.

### 4.9 Document

A document symbol is commonly shown as a rectangle with a wavy bottom
edge.

Use it when a document or report is an important process output, for
example, "Generate payment receipt".

### 4.10 Manual operation

A trapezoid-like symbol may represent work performed manually.

Example: "Manually inspect the submitted paper form".

The exact symbol set can vary by convention and software. Be consistent
and include a small legend when a diagram uses less familiar symbols.

## 5. Flowchart symbol quick reference

  -----------------------------------------------------------------------
  Symbol            Shape             Meaning           Example
  ----------------- ----------------- ----------------- -----------------
  Terminator        Oval / rounded    Start or end      Start application
                    rectangle                           

  Process           Rectangle         Activity or       Verify documents
                                      action            

  Decision          Diamond           Condition /       Documents valid?
                                      branch            

  Input / Output    Parallelogram     Data received or  Enter applicant
                                      produced          details

  Flow line         Arrow             Direction of flow Next activity

  Connector         Small circle      Connects          A to A
                                      separated flow    
                                      sections          

  Off-page          Pentagon-like     Continues on      Continue to page
  connector         shape             another page      2

  Subprocess        Rectangle with    Detailed process  Verify payment
                    side lines        exists elsewhere  

  Document          Wavy-bottom       Document or       Generate receipt
                    rectangle         report            

  Manual operation  Trapezoid-like    Manually          Inspect paper
                    shape             performed action  form
  -----------------------------------------------------------------------

## 6. How to describe activities correctly

An activity is a unit of work performed by a person, team or system.

### 6.1 Use verb + object

Good activity labels:

-   Receive application.
-   Validate email address.
-   Check payment status.
-   Approve refund.
-   Generate confirmation.
-   Notify customer.

Weak activity labels:

-   Application.
-   Payment.
-   Validation.
-   Customer.
-   Processing.

The weak labels identify subjects but do not explain what work is
performed.

### 6.2 One activity should represent a meaningful action

Avoid combining many unrelated actions into one rectangle.

Weak:

"Receive application, verify documents, approve admission and send
confirmation."

Better:

1.  Receive application.
2.  Check document completeness.
3.  Verify documents.
4.  Record admission decision.
5.  Send confirmation.

However, do not split every tiny click into a separate box. The right
level of detail depends on the audience and purpose.

### 6.3 Identify the performer

A simple flowchart may not show the responsible role inside every box.
If responsibility matters, use role labels or a swimlane-style
arrangement.

Example:

-   Student: Submit application.
-   Portal: Record application.
-   Admissions officer: Verify documents.
-   Academic reviewer: Review eligibility.

A process diagram should not leave ownership unclear when the handoff is
important.

## 7. Decisions and branching logic

A decision is a point at which the next activity depends on a condition.

Example:

**Is the payment successful?**

-   Yes → Generate receipt.
-   No → Display payment failure and allow another attempt or
    cancellation.

### 7.1 Write decisions as questions

Good decision labels:

-   Is the application complete?
-   Is the customer eligible?
-   Has payment been received?
-   Is manager approval required?
-   Is the document valid?

Avoid labels such as:

-   Application.
-   Payment status.
-   Approval.
-   Check.

These do not clearly express the condition being evaluated.

### 7.2 Label every decision branch

For a Yes/No decision, label both outgoing arrows.

Do not rely on the reader to guess which arrow means Yes.

Example:

```{=html}
<pre>
                  / Is payment successful? \
                 /                           \
              Yes                             No
               |                               |
       [Generate receipt]             [Show payment error]
</pre>
```
### 7.3 Decisions should be logically complete

Ask:

-   Are all realistic outcomes represented?
-   Can two branches be true at the same time?
-   Is there an outcome that is not covered?
-   What happens when the result is unknown?
-   Is there a fallback when the system cannot evaluate the condition?

Example: "Is the application complete?"

Possible results: - Complete. - Incomplete. - Unable to determine
because the system is unavailable.

If the third situation is possible and important, it may need a separate
exception path.

### 7.4 Multiple outcomes

Some decisions have more than two possible outcomes.

Example: Document verification result:

-   Valid → Continue to review.
-   Invalid → Request correction.
-   Unreadable → Ask for a clearer upload.
-   Suspected duplicate → Escalate for investigation.

Use clear branch labels. Do not create an unexplained collection of
arrows.

### 7.5 Business rule versus decision

These are related but different.

-   **Business rule:** The policy or condition that must be followed.
-   **Decision:** The point in the process where the condition is
    evaluated and a path is selected.

Example:

-   Rule: An application must include all mandatory documents before it
    can be verified.
-   Decision: Are all mandatory documents present?
-   Yes path: Continue verification.
-   No path: Request missing documents.

## 8. Sequence, branching, merging and loops

### 8.1 Sequence

A sequence shows activities performed one after another.

```{=html}
<pre>
(Start)
   |
[Receive request]
   |
[Record request]
   |
[Review request]
   |
 (End)
</pre>
```
Use a sequence when the next step follows the previous step without a
decision branch.

### 8.2 Branching

Branching occurs when the process can follow different paths.

```{=html}
<pre>
             [Check details]
                    |
             <Details valid?>
               /        \
             Yes         No
              |           |
       [Continue]   [Request correction]
</pre>
```
### 8.3 Merging

Merging occurs when separate paths join a common next step.

Example:

-   Payment by card succeeds.
-   Payment by bank transfer is confirmed.
-   Both paths continue to "Create order".

Do not merge paths if they require different next steps or if important
information would be lost.

### 8.4 Loop / repetition

A loop occurs when an activity or set of activities may repeat.

Example:

1.  User enters a password.
2.  System checks the password.
3.  If incorrect, user may try again.
4.  The process returns to password entry.
5.  If correct, access is granted.

A loop should have a clear exit condition. If retries are limited, show
what happens after the limit is reached.

### 8.5 Avoid accidental infinite loops

A loop with no exit condition can make a process appear endless.

Example: - "If invalid, check again" with no correction step or limit.

Improve it: - Explain what the user must correct. - Define whether
another attempt is allowed. - Define what happens after the maximum
attempts. - Show the exit path.

## 9. Process boundaries in flowchart design

A process boundary defines the start, end and scope of the work being
represented.

Before drawing, agree on the boundary with stakeholders.

### 9.1 Define the start

Ask:

-   What event triggers the process?
-   Who or what initiates it?
-   Is the trigger an event, request, schedule or condition?

Examples: - Customer submits an order. - Student submits an
application. - Employee's joining is confirmed. - Complaint is received.

### 9.2 Define the end

Ask:

-   What result means this process is complete?
-   Who receives the output?
-   Is there more than one valid end state?
-   Does the next activity belong to another process?

Examples: - Order is dispatched. - Application is verified or returned
for correction. - Employee access is provisioned. - Complaint is
resolved or formally escalated.

### 9.3 Define what is in scope

Write down the activities included in the diagram.

Example --- order processing:

**Included** - Receive order. - Validate order. - Confirm payment. -
Check stock. - Create fulfilment request.

**Excluded** - Product marketing. - Supplier procurement. - Delivery
after handoff to the courier. - Post-delivery customer support.

Excluded activities may still interact with the process.

### 9.4 Boundary mistakes

  -----------------------------------------------------------------------
  Mistake                 Why it causes confusion Better approach
  ----------------------- ----------------------- -----------------------
  Start point is vague    Readers do not know     Name a specific event
                          what triggers work      

  End point is missing    It is unclear when the  Define a measurable end
                          process is complete     condition

  Diagram covers too much It becomes difficult to Decompose into
                          read                    subprocesses

  Diagram covers too      Important handoffs are  Show the relevant
  little                  hidden                  end-to-end segment

  Department boundary     Work crossing           Follow the business
  used as process         departments is omitted  outcome
  boundary                                        

  External interaction    Inputs and dependencies Show relevant external
  omitted                 are unclear             participants or
                                                  handoffs
  -----------------------------------------------------------------------

## 10. How to create a flowchart step by step

### Step 1: Understand the process purpose

Ask: - Why are we drawing this flowchart? - Who will use it? - What
business question should it answer?

A management overview and a detailed operational flowchart need
different levels of detail.

### Step 2: Confirm the process boundary

Document: - Process name. - Start event. - End condition. - Included
work. - Excluded work.

Do this before drawing shapes.

### Step 3: Collect process information

Use discovery methods from Day 13: - Interviews. - Workshops. -
Observation. - Document analysis. - System and data review.

Ask stakeholders to walk through a real example, not only the ideal
process.

### Step 4: List activities in sequence

Write the activities as numbered steps before drawing.

Example: 1. Receive application. 2. Record application. 3. Check
document completeness. 4. Verify documents. 5. Record verification
result. 6. Notify student.

### Step 5: Identify decisions

For each step, ask: - Is there a condition? - Does the next step depend
on the answer? - What are all possible outcomes? - Which business rule
controls the decision?

### Step 6: Identify alternate and exception paths

Ask: - What happens if information is missing? - What happens if the
system is unavailable? - What happens if approval is rejected? - Can the
work be repeated? - Is escalation required?

### Step 7: Select the appropriate symbols

Use: - Terminator for start/end. - Rectangle for activities. - Diamond
for decisions. - Parallelogram for input/output where relevant. - Arrows
for direction. - Connectors when needed.

### Step 8: Draw from top to bottom or left to right

Choose a primary direction and maintain it consistently.

Keep: - Main flow easy to follow. - Decision labels close to their
arrows. - Crossovers to a minimum. - Related activities close
together. - Alternate paths visually understandable.

### Step 9: Review the logic

Trace each possible path from start to an end point.

Check: - Does every activity have a valid incoming and outgoing flow
where appropriate? - Does every decision have labeled outcomes? - Does
each branch lead somewhere meaningful? - Are loops intentional and
escapable? - Are all valid end states represented?

### Step 10: Validate with stakeholders

Walk through the diagram with people who perform and own the process.

Ask: - Is this how work actually happens? - Are any steps missing? - Are
the decision rules correct? - Are exceptions represented? - Are roles
and handoffs accurate? - Does the boundary match the agreed scope?

Record corrections and update the version.

## 11. Worked example --- online order processing

### 11.1 Business scenario

A customer places an order on an e-commerce website. The business
validates the order, checks payment and stock, and either confirms the
order or informs the customer that it cannot proceed.

### 11.2 Process boundary

-   Start: Customer submits an order.
-   End: Order is confirmed or the customer is informed that the order
    cannot proceed.
-   Included: Order validation, payment check, stock check and order
    confirmation.
-   Excluded: Packing, shipping and delivery.

### 11.3 Activity list

1.  Customer submits order.
2.  System records order details.
3.  System validates the order.
4.  System checks payment status.
5.  System checks stock availability.
6.  System confirms order.
7.  System sends confirmation to customer.

Exception activities: - Ask customer to correct invalid details. -
Display payment failure. - Inform customer that the item is unavailable.

### 11.4 Text flowchart

```{=html}
<pre>
                 (Start)
                    |
          [Customer submits order]
                    |
           [Record order details]
                    |
             <Order details valid?>
                /          \
              No            Yes
              |              |
       [Show validation] [Check payment]
       [error to customer]     |
              |          <Payment successful?>
        [Correct details]     /       \
              |             No         Yes
              └── back       |           |
                      [Show payment] [Check stock]
                      [failure]          |
                          |       <Stock available?>
                        (End)        /        \
                                    No          Yes
                                    |            |
                             [Inform customer] [Confirm order]
                                    |            |
                                  (End)   [Send confirmation]
                                                 |
                                               (End)
</pre>
```
### 11.5 What the BA should check

-   Does the system validate details before payment?
-   Is payment authorization different from payment capture?
-   What happens if payment succeeds but the stock check fails?
-   Is the customer refunded automatically or through a separate
    process?
-   Can the customer correct the order without starting again?
-   What happens if the payment gateway does not respond?
-   Are partial fulfilments allowed?

These questions may reveal additional branches or connected processes.
The flowchart should reflect confirmed business rules, not invented
assumptions.

## 12. Worked example --- student document verification

### 12.1 Scenario

A student submits an admission application and uploads documents. An
admissions officer checks whether the documents are complete and valid.

### 12.2 Process boundary

-   Start: Application is submitted.
-   End state 1: Application is marked document-verified.
-   End state 2: Application is returned to the student for correction.
-   Included: Completeness check, document verification and
    communication.
-   Excluded: Academic selection and final admission decision.

### 12.3 Flow

```{=html}
<pre>
                   (Start)
                      |
             [Receive application]
                      |
             [Check document list]
                      |
              <All documents present?>
                 /             \
               No               Yes
               |                 |
       [List missing items] [Verify documents]
               |                 |
       [Notify the student] <Documents valid?>
               |             /         \
        [Wait for upload]   No           Yes
               |             |             |
       [Receive new file] [Request       [Mark verified]
               |          correction]       |
       └──> [Check document list]          (End)
                             |
                      [Student responds]
                             |
                    [Receive corrected file]
                             |
                    [Verify documents again]
</pre>
```
### 12.4 Questions raised by the model

-   Can an application contain more than one missing document?
-   Does the student receive one combined correction request?
-   Is there a deadline for submitting corrections?
-   What happens if the student does not respond?
-   Can the officer override a failed validation?
-   Who handles suspected fraudulent documents?
-   Is there a maximum number of correction cycles?

A useful flowchart often reveals missing requirements and business
rules.

## 13. Flowchart quality checklist

Use this checklist when creating or reviewing a diagram.

### Scope and structure

-   The process has a clear name.
-   The start event is specific.
-   The end condition is clear.
-   Included and excluded work is documented.
-   The diagram has an appropriate level of detail.

### Symbols and labels

-   Symbols are used consistently.
-   Activities use clear action phrases.
-   Decisions are written as questions.
-   Decision branches are labeled.
-   Arrows show direction clearly.
-   A legend explains any uncommon symbols.

### Logic

-   Every realistic path is represented.
-   Branches lead to valid next steps.
-   Loops have clear exit conditions.
-   End states are intentional.
-   No unexplained arrows or disconnected activities remain.

### Business accuracy

-   Roles and handoffs are correct.
-   Business rules are confirmed.
-   Exceptions are included where relevant.
-   The diagram reflects actual practice or is clearly labeled as a
    proposed process.
-   Stakeholders have reviewed the diagram.

### Readability

-   The primary direction is consistent.
-   Lines do not cross unnecessarily.
-   Labels are short and meaningful.
-   The diagram is not overloaded.
-   Large processes are decomposed into smaller diagrams.

## 14. Common flowchart mistakes and corrections

  -----------------------------------------------------------------------
  Mistake                 Problem                 Correction
  ----------------------- ----------------------- -----------------------
  Using a rectangle for   Decisions become        Use a diamond for
  every shape             indistinguishable from  decisions
                          activities              

  Decision has no labels  Reader cannot identify  Label every outgoing
                          each outcome            branch

  Activity label is only  Action is unclear       Use verb + object
  a noun                                          

  Missing start or end    Process scope is        Define start and end
                          unclear                 terminators

  Arrows point in         Flow is difficult to    Use one main direction
  inconsistent directions follow                  

  Too many steps in one   Multiple actions and    Split into meaningful
  box                     decisions are hidden    activities

  Missing exception path  Diagram represents only Ask about errors,
                          ideal cases             rework and escalation

  Loop has no exit        Process may appear      Define correction and
                          endless                 exit conditions

  Lines cross repeatedly  Connections are hard to Reposition shapes or
                          interpret               use connectors

  Assumptions shown as    Diagram may be          Mark assumptions and
  facts                   inaccurate              validate them

  Too much detail         Diagram becomes         Use a high-level map
                          unreadable              and subprocess detail
  -----------------------------------------------------------------------

## 15. Flowchart versus process map versus BPMN

These terms are related but have different uses.

  -----------------------------------------------------------------------
  Feature           Basic flowchart   Process map       BPMN
  ----------------- ----------------- ----------------- -----------------
  Main purpose      Show sequence and Show process at a Model business
                    decisions         chosen level      processes using a
                                                        formal notation

  Symbols           Common flowchart  May use simple    Standardized BPMN
                    shapes            boxes and arrows  elements

  Detail            Simple to         Often high-level, Can represent
                    detailed          but can be        complex process
                                      detailed          behavior

  Roles             Can be shown with Often shown at a  Pools and lanes
                    labels or lanes   high level        provide
                                                        participant
                                                        structure

  Best use          Explain logic and Give an overview  Communicate
                    branching         of process steps  detailed process
                                                        behavior
                                                        consistently
  -----------------------------------------------------------------------

BPMN is covered in Day 15. Do not assume every flowchart is a BPMN
diagram.

## 16. Tool awareness: where flowcharts can be created

A BA may create flowcharts using different tools. The choice depends on
company standards, collaboration needs and available licenses.

### 16.1 Microsoft Visio

Commonly used for professional diagrams and process documentation.

Typical capabilities: - Flowchart shape libraries. - Connectors and
alignment tools. - Swimlane diagrams. - Templates. - Export and sharing
options.

A typical workflow: 1. Open a flowchart template. 2. Add a start
terminator. 3. Add activity rectangles. 4. Add decision diamonds. 5.
Connect shapes with arrows. 6. Label branches. 7. Align and distribute
shapes. 8. Review and export the diagram.

### 16.2 diagrams.net (draw.io)

A diagramming tool commonly used for flowcharts and technical diagrams.

Typical workflow: 1. Create a blank diagram or select a flowchart
template. 2. Open the flowchart shape library. 3. Drag a terminator,
process and decision shape onto the canvas. 4. Add text labels. 5.
Connect shapes using connector arrows. 6. Label Yes/No branches. 7.
Arrange the diagram and save or export it.

Useful when a lightweight diagramming option is sufficient.

### 16.3 Lucidchart

A collaborative diagramming platform used for flowcharts, process maps
and other diagrams.

Common capabilities: - Templates and shape libraries. - Collaboration
and comments. - Diagram sharing. - Connectors and layout support.

### 16.4 Choosing a tool

  -----------------------------------------------------------------------
  Need                                Suitable consideration
  ----------------------------------- -----------------------------------
  Organization already uses Microsoft Check whether Visio is approved and
  365                                 available

  Lightweight flowchart creation      diagrams.net may be sufficient

  Real-time collaboration             Consider a collaboration-focused
                                      diagramming tool

  Formal enterprise documentation     Follow the organization's approved
                                      tool and standards
  -----------------------------------------------------------------------

**Important:** Tool names and interface details may change. Learn the
modeling concepts first; the same process logic can be represented in
different tools.

## 17. Interview questions and answers

### Q1. What is a flowchart?

A flowchart is a visual representation of process steps, decisions and
the direction of work. It uses shapes and arrows to make the process
easier to understand and communicate.

### Q2. Why does a Business Analyst use flowcharts?

A BA uses flowcharts to understand and communicate process logic,
identify missing steps, clarify decisions, reveal rework and support
requirement analysis and testing.

### Q3. What does a rectangle represent in a flowchart?

A rectangle represents a process or activity, such as "Verify customer
details".

### Q4. What does a diamond represent?

A diamond represents a decision or condition. Its outgoing paths should
show the possible outcomes, such as Yes and No.

### Q5. What is a terminator symbol?

A terminator, commonly shown as an oval or rounded rectangle, represents
the start or end of a process or process segment.

### Q6. What is the purpose of an arrow?

An arrow shows the direction of flow from one process element to
another.

### Q7. How should an activity be named?

Use a clear action phrase, usually a verb followed by an object, such as
"Validate payment" or "Send confirmation".

### Q8. How should a decision be named?

Write the decision as a clear question, such as "Is the payment
successful?" Then label the outgoing branches with their outcomes.

### Q9. What is a process boundary?

A process boundary defines the start, end and scope of the process being
modeled. It identifies which activities are included and which are
outside the diagram's scope.

### Q10. What is branching?

Branching occurs when a decision or condition causes the process to
follow different paths.

### Q11. What is merging?

Merging occurs when two or more paths join a common subsequent activity
or flow.

### Q12. What is a loop in a flowchart?

A loop represents work that may repeat, such as asking a user to correct
invalid information and resubmit it. A loop should have a defined exit
condition.

### Q13. What is the difference between a flowchart and BPMN?

A basic flowchart uses common shapes to show activities and decisions.
BPMN is a more formal business-process modeling notation with
standardized elements for events, tasks, gateways and participants.

### Q14. What should a BA do before drawing a flowchart?

The BA should understand the process purpose, define the boundary,
identify stakeholders, collect process information, list activities,
discover decisions and exceptions, and confirm the intended level of
detail.

### Q15. How do you validate a flowchart?

Walk through it with process participants and the process owner. Confirm
activities, sequence, decisions, roles, handoffs, exceptions and
start/end conditions. Update the diagram based on feedback.

### Q16. What happens if a decision has an unlabeled branch?

The reader cannot reliably identify which outcome follows that path. The
BA should label the branch clearly and verify that all possible outcomes
are covered.

### Q17. Can a flowchart have multiple end points?

Yes. A process can have multiple legitimate outcomes, such as "Order
confirmed", "Order cancelled" or "Order rejected". Each end state should
be clearly labeled.

### Q18. How do you avoid making a flowchart too complicated?

Start with the end-to-end process at a high level. Break complex
sections into subprocesses or separate diagrams. Include detail only
when it helps the intended audience understand the process.

### Q19. What is the difference between a business rule and a decision?

A business rule defines the condition or policy. A decision is the point
in the process where that condition is evaluated and the next path is
selected.

### Q20. What would you do if stakeholders disagree about a flowchart?

I would record the different explanations, identify whether they
represent valid process variations or conflicting practices, collect
supporting evidence and discuss the issue with the process owner. I
would update the model only after the relevant behavior is clarified.

## 18. Knowledge check

Try the questions before reviewing the answers.

### Questions

1.  Which symbol represents an activity?
    -   A. Diamond
    -   B. Rectangle
    -   C. Oval
    -   D. Circle connector
2.  Which symbol represents a decision?
    -   A. Diamond
    -   B. Rectangle
    -   C. Parallelogram
    -   D. Terminator
3.  What should normally be written inside a decision diamond?
    -   A. A person's name
    -   B. A question or condition
    -   C. A long paragraph
    -   D. A document version
4.  What should be shown on outgoing branches from a Yes/No decision?
    -   A. No labels
    -   B. The activity owner's salary
    -   C. Yes and No labels
    -   D. Random identifiers
5.  What is a loop used to show?
    -   A. A process that can repeat
    -   B. A process owner
    -   C. A document title
    -   D. A process boundary only
6.  Why define the process boundary before drawing?
    -   A. To choose colors
    -   B. To establish what is included and where the process starts
        and ends
    -   C. To avoid interviewing stakeholders
    -   D. To select a database
7.  Which is the better activity label?
    -   A. Payment
    -   B. Customer
    -   C. Validate payment
    -   D. Details
8.  A flowchart shows only the normal path and ignores failed payments.
    What is the issue?
    -   A. It contains too many exceptions
    -   B. It may be incomplete
    -   C. It is automatically BPMN
    -   D. It has too many terminators
9.  What is merging?
    -   A. Splitting one path into several
    -   B. Joining separate paths into a common flow
    -   C. Ending every process
    -   D. Removing all arrows
10. What should a BA do after creating the first flowchart?

-   A. Treat it as final
-   B. Validate it with stakeholders
-   C. Remove all decision paths
-   D. Avoid documenting assumptions

### Answers with explanations

1.  **B --- Rectangle.** It represents an activity or process step.
2.  **A --- Diamond.** It represents a decision.
3.  **B --- A question or condition.** This makes the decision logic
    understandable.
4.  **C --- Yes and No labels.** Branch labels show which outcome
    follows each path.
5.  **A --- A process that can repeat.** A loop should have an exit
    condition.
6.  **B.** Boundaries establish the process scope and prevent confusion.
7.  **C --- Validate payment.** It describes an action clearly.
8.  **B --- It may be incomplete.** Important exception paths must be
    discovered and represented.
9.  **B.** Separate paths join a shared subsequent flow.
10. **B.** Stakeholder validation checks whether the diagram reflects
    the actual or agreed process.

## 19. Day 14 revision sheet

  Topic               Remember
  ------------------- --------------------------------------------------
  Flowchart           Visual representation of steps and process logic
  Terminator          Start or end
  Process rectangle   Activity or action
  Decision diamond    Condition that selects a path
  Input / Output      Information received or produced
  Flow line           Direction of process movement
  Connector           Links separated parts of a diagram
  Subprocess          Detailed process represented elsewhere
  Activity label      Verb + object
  Decision label      Clear question or condition
  Branching           One flow splits into different paths
  Merging             Separate paths join a common flow
  Loop                A path repeats until an exit condition is met
  Process boundary    Start, end and included scope
  Exception path      What happens outside the normal flow
  Validation          Confirming diagram accuracy with stakeholders

### Five rules to remember

1.  Define the process boundary before drawing.
2.  Use rectangles for activities and diamonds for decisions.
3.  Label every decision branch.
4.  Show important exceptions and loops.
5.  Validate the diagram with the people who perform and own the
    process.

## 20. Day 14 completion checklist

-   [ ] I can define a flowchart and explain why a BA uses one.
-   [ ] I can identify terminator, process, decision, input/output and
    connector symbols.
-   [ ] I can write activities using verb + object.
-   [ ] I can write decisions as clear questions.
-   [ ] I can label decision branches correctly.
-   [ ] I can explain sequence, branching, merging and loops.
-   [ ] I can identify loop exit conditions.
-   [ ] I can define process start, end and scope.
-   [ ] I can convert a written scenario into a sequence of activities
    and decisions.
-   [ ] I can identify alternate and exception paths.
-   [ ] I can review a flowchart for logical completeness and
    readability.
-   [ ] I can explain the difference between a flowchart, process map
    and BPMN.
-   [ ] I can describe how a BA validates a flowchart with stakeholders.
-   [ ] I can answer the interview questions in my own words.

------------------------------------------------------------------------

**Day 14 complete --- Flowcharts, Activities, Decisions and Process
Boundaries.**

**Next syllabus topic --- Day 15: BPMN Basics --- Events, Tasks,
Gateways and Pools.**
