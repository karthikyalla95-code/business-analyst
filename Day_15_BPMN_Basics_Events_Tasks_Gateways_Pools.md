# Day 15 --- BPMN Basics: Events, Tasks, Gateways and Pools

**Phase 3: Process Modeling and Documentation**\
**Syllabus topic:** BPMN basics --- events, tasks, gateways and pools\
**Learning focus:** Understand how Business Process Model and Notation
(BPMN) represents business workflows, read basic BPMN diagrams, choose
the correct symbols and explain process behavior to business and
technical stakeholders.

------------------------------------------------------------------------

## 1. Learning objectives

By the end of this lesson, you should be able to:

-   Explain what BPMN is and why a Business Analyst uses it.
-   Distinguish BPMN from a simple flowchart and a high-level process
    map.
-   Recognize the main BPMN building blocks: events, activities,
    gateways, sequence flows, pools and lanes.
-   Identify start, intermediate and end events.
-   Distinguish a task from a subprocess.
-   Choose between exclusive, parallel and inclusive gateways.
-   Explain sequence flow versus message flow.
-   Model a simple process with more than one participant.
-   Read a BPMN diagram and explain its normal, alternate and exception
    paths.
-   Identify common BPMN modeling mistakes and validate a diagram with
    stakeholders.

## 2. What is BPMN?

**BPMN (Business Process Model and Notation)** is a standardized visual
notation for describing business processes. It uses agreed symbols and
connection rules so that business users, analysts, process owners and
technical teams can interpret a process consistently.

Think of BPMN as a shared visual language for explaining:

-   What starts a process.
-   Which activities are performed.
-   Who performs each activity.
-   Where decisions are made.
-   Which activities happen in sequence or in parallel.
-   How different participants communicate.
-   What event or condition ends the process.

### Practical example

An online order process may look like this:

1.  Customer places an order.
2.  The system validates the order.
3.  The system checks payment.
4.  If payment succeeds, the warehouse prepares the order.
5.  The courier collects the package.
6.  The customer receives the order.
7.  The process ends.

A BPMN model makes the sequence, decision and participants visible
rather than leaving them buried in a paragraph.

### Why a BA uses BPMN

-   **Communication:** stakeholders can review a visual representation
    instead of interpreting lengthy descriptions.
-   **Process discovery:** it helps document how work actually happens.
-   **Analysis:** delays, duplicate work, unnecessary approvals and
    unclear handoffs become easier to see.
-   **Requirements:** process steps can reveal system functions,
    business rules, data needs and exception handling.
-   **Improvement:** the current process can be compared with a proposed
    future process.
-   **Handover:** developers, testers and operations teams can
    understand expected process behavior.

BPMN is not only a drawing technique. It is a notation with defined
meanings and rules. A diagram that looks attractive but uses symbols
incorrectly can mislead its readers.

## 3. BPMN compared with flowcharts and process maps

  ------------------------------------------------------------------------
  Aspect            Basic flowchart   High-level        BPMN
                                      process map       
  ----------------- ----------------- ----------------- ------------------
  Main purpose      Show steps and    Show major        Model process
                    decisions         process stages    behavior precisely

  Symbols           Common simple     Often simple      Standardized BPMN
                    shapes            boxes and arrows  symbols

  Participants      May be shown      Often grouped by  Pools and lanes
                    informally        team              represent
                                                        participants and
                                                        responsibilities

  Events            Usually start/end Usually not       Start,
                    symbols           detailed          intermediate and
                                                        end events

  Parallel work     Can be            Usually           Explicit parallel
                    represented, but  simplified        gateway
                    often informally                    

  Communication     Often unclear     Usually           Message flow
  between                             high-level        
  participants                                          

  Best use          Simple logic      Management        Detailed process
                                      overview          analysis and
                                                        communication
  ------------------------------------------------------------------------

**Rule of thumb:** use a flowchart for straightforward logic, a process
map for a quick overview, and BPMN when you need to represent events,
responsibilities, handoffs, parallel work or communication between
participants.

## 4. The four main BPMN element groups

BPMN elements are commonly organized into four groups:

1.  **Flow objects:** events, activities and gateways.
2.  **Connecting objects:** sequence flows, message flows and
    associations.
3.  **Swimlanes:** pools and lanes.
4.  **Artifacts:** additional information such as data objects, groups
    and text annotations.

This lesson focuses on the flow objects, connections and swimlanes most
frequently used in introductory process models.

## 5. Events --- something that happens

An **event** represents something that happens during a process. An
event is not normally a task performed by a person; it marks a trigger,
occurrence or result that affects process flow.

BPMN events are shown as circles. The border style and internal marker
help identify the event type.

### 5.1 Start event

A start event indicates where a process instance begins.

-   It is drawn as a circle with a thin single border.
-   It answers: **What causes this process to begin?**
-   A process may have more than one start event when different triggers
    can initiate it.
-   A start event has outgoing flow and no incoming sequence flow.

Examples:

-   Customer submits an order.
-   Employee submits a leave request.
-   A scheduled daily report time is reached.
-   A support ticket is received.

**Example:** The online order process begins when the customer submits
an order. The event is not "Validate order"; that is work performed
after the process starts.

### 5.2 Intermediate event

An intermediate event occurs after the process has started but before it
ends.

-   It is drawn as a circle with a double border.
-   It can represent something that happens during the process.
-   Depending on its type and position, it can catch or throw an event,
    wait for something, or indicate an exception.

Examples:

-   Wait for a payment response.
-   Receive a confirmation message.
-   A timer reaches a deadline.
-   An error occurs during processing.

For beginner-level diagrams, focus on the idea that an intermediate
event represents an occurrence or wait within the process, not a normal
work activity.

### 5.3 End event

An end event indicates that a process path has finished.

-   It is drawn as a circle with a thick border.
-   It answers: **What outcome ends this path?**
-   It has incoming sequence flow and no outgoing sequence flow.
-   A process can have multiple end events for different outcomes.

Examples:

-   Order completed.
-   Order cancelled.
-   Request rejected.
-   Payment failed and the process is terminated.

A process with separate success and rejection outcomes may use separate
end events so the outcomes are unambiguous.

### 5.4 Event types you should recognize

BPMN has several event definitions. You do not need to memorize every
advanced variation immediately, but you should understand the common
ones.

  -----------------------------------------------------------------------
  Event type              Meaning                 Practical example
  ----------------------- ----------------------- -----------------------
  None                    A basic event without a A simple process start
                          specified trigger type  

  Message                 A message is received   Receive a customer
                          or sent                 order message

  Timer                   A time or deadline      Wait until payment
                          condition occurs        deadline

  Error                   An error condition      A system operation
                          occurs                  raises an error

  Signal                  A signal is broadcast   A process reacts to a
                          or caught               shared signal

  Conditional             A condition becomes     Inventory reaches
                          true                    reorder threshold

  Escalation              Work is escalated       Unresolved request
                                                  moves to a manager
  -----------------------------------------------------------------------

**Important:** the event marker and whether the event is a start,
intermediate or end event together determine its meaning. For example, a
message start event means a message triggers the process; a message
intermediate catch event means the process waits to receive a message.

### 5.5 Event examples in an order process

  -----------------------------------------------------------------------
  Point in process        BPMN element            Reason
  ----------------------- ----------------------- -----------------------
  Customer submits order  Start event             This triggers the
                                                  process

  System validates order  Task                    Work is performed

  Payment response        Intermediate message    A response is received
  arrives                 event                   

  Order is fulfilled      End event               The successful path
                                                  finishes

  Payment deadline        Intermediate timer      A time condition occurs
  expires                 event                   
  -----------------------------------------------------------------------

### Common event mistakes

-   Using a task when the diagram needs to show a trigger.
-   Treating "check payment" as an event rather than an activity.
-   Drawing an end event with outgoing sequence flow.
-   Using the same vague label for start and end events.
-   Forgetting to show a meaningful unsuccessful or cancelled end
    outcome.

## 6. Activities --- work performed

An **activity** represents work carried out within a process. Activities
are drawn as rounded rectangles.

Examples:

-   Validate customer details.
-   Calculate order total.
-   Approve leave request.
-   Generate invoice.
-   Dispatch package.

### 6.1 Task

A **task** is a unit of work treated as one step at the current level of
detail.

Use a task when the diagram does not need to show the internal steps of
that activity.

Examples:

-   Verify customer identity.
-   Record payment.
-   Prepare shipment.
-   Send confirmation email.

Label tasks with a clear action, preferably **verb + object**.

Good task labels: - Validate application. - Check stock availability. -
Approve refund. - Update customer record.

Weak task labels: - Application. - Stock. - Refund. - Customer.

### 6.2 Common task types

BPMN provides task markers that describe the nature of the work. At a
beginner level, understand these common types:

  -----------------------------------------------------------------------
  Task type               Meaning                 Example
  ----------------------- ----------------------- -----------------------
  None task               General activity;       Review application
                          implementation is not   
                          specified               

  User task               A person performs work  HR officer approves
                          with software           leave in a portal
                          assistance              

  Manual task             A person performs work  Physically inspect a
                          without a               returned item
                          process-engine          
                          application performing  
                          the task                

  Service task            A system or service     Automatically calculate
                          performs an operation   tax

  Script task             A script is executed    Run a data
                                                  transformation script

  Send task               A message is sent       Send order confirmation

  Receive task            A message is received   Receive payment
                                                  confirmation
  -----------------------------------------------------------------------

Do not confuse the task type with the business purpose. "Approve leave
request" is the business activity; the task type indicates how that work
is performed.

### 6.3 Subprocess

A **subprocess** is an activity that contains a more detailed sequence
of work.

Use a subprocess when: - A process section has several internal steps. -
The main diagram is becoming crowded. - The same process section is
reused or needs separate explanation. - Readers need to understand the
high-level flow first and the detail separately.

Example:

At a high level, "Process payment" may be one subprocess. Its detailed
view may include: 1. Read payment details. 2. Send authorization
request. 3. Receive response. 4. Record transaction result. 5. Return
payment status.

A subprocess is still an activity in the parent process. Its internal
flow is documented at another level.

### Task vs subprocess

  -----------------------------------------------------------------------
  Task                                Subprocess
  ----------------------------------- -----------------------------------
  One unit of work at the current     A group of steps treated as one
  diagram level                       activity in the parent diagram

  Internal steps are not expanded     Internal steps can be modeled in
                                      detail

  Keeps a diagram simple              Adds detail where needed

  Example: Verify identity            Example: Complete identity
                                      verification process
  -----------------------------------------------------------------------

### 6.4 Activity labels and detail level

A task should communicate the action clearly without becoming a
paragraph.

-   Use a verb and an object.
-   Avoid labels such as "Work," "Process," or "Activity."
-   Keep the level of detail consistent.
-   Do not expand every tiny action into its own task.
-   Do not hide a complex approval or exception sequence inside one task
    if the reader needs that detail.

## 7. Gateways --- controlling the process path

A **gateway** controls how sequence flow is split or joined. It is drawn
as a diamond.

A gateway is not normally a business activity. It represents routing
logic: which path or paths should be followed?

Common introductory gateway types:

1.  Exclusive gateway (XOR).
2.  Parallel gateway (AND).
3.  Inclusive gateway (OR).

### 7.1 Exclusive gateway (XOR)

An exclusive gateway selects **one** outgoing path based on a condition.

Use it when only one alternative should be followed.

Example: Payment result?

-   If payment is successful → Confirm order.
-   If payment fails → Notify customer and close the order.

Only one of these paths is selected for a given decision.

Typical questions: - Is the application complete? - Is the customer
eligible? - Is the payment approved? - Is the requested item in stock?

**Practical rule:** if the business rule says "either this or that, but
not both," an exclusive gateway is usually appropriate.

Make each outgoing condition explicit. Avoid labels such as "Yes" and
"No" if the question itself is unclear. A clear gateway question plus
clearly labeled branches is easier to validate.

### 7.2 Parallel gateway (AND)

A parallel gateway starts or synchronizes multiple paths that are
intended to happen together.

Use it when all required branches should proceed, rather than choosing
only one.

Example: After an order is confirmed, the business may: - Reserve
inventory. - Generate an invoice. - Send an order confirmation.

These activities can happen in parallel if the business rules and system
design allow it.

A parallel split creates concurrent paths. A matching parallel join can
synchronize them so the process continues after all required incoming
branches have completed.

**Important:** a parallel gateway does not mean "choose whichever path
is available." It means the paths are all activated.

### 7.3 Inclusive gateway (OR)

An inclusive gateway activates **one or more** outgoing paths, depending
on which conditions are true.

Example: A customer requests optional delivery services: - Gift wrapping
may be selected. - Express delivery may be selected. - Both may be
selected. - Neither may be selected, if allowed by the business rule.

The gateway activates every branch whose condition is satisfied. A
corresponding inclusive join can bring the active branches back
together.

Use an inclusive gateway when the business rule allows multiple
alternatives to be selected, but not necessarily all.

### 7.4 Gateway comparison

  ------------------------------------------------------------------------
  Gateway          Logic                  Number of paths Example
                                                 followed 
  ---------------- ---------------- --------------------- ----------------
  Exclusive (XOR)  One alternative            Exactly one Approve or
                                                          reject

  Parallel (AND)   All branches     All outgoing branches Notify customer
                                                          and reserve
                                                          stock

  Inclusive (OR)   One or more            One or multiple Select one or
                   conditions                             more optional
                                                          services
  ------------------------------------------------------------------------

### 7.5 Gateway split and join

-   **Split:** one incoming path is routed into multiple outgoing paths.
-   **Join:** multiple incoming paths are brought together.
-   The correct gateway depends on the logic of the process.
-   Do not assume every split needs the same type of join. Model the
    actual business behavior.

Examples: - XOR split: choose either approve or reject. - AND split:
start stock reservation and invoice generation together. - AND join:
wait for both required activities to finish. - OR split: start all
optional services selected by the customer.

### 7.6 Decision conditions and branch labels

A gateway should represent a clear question or routing condition.

Weak: - Decision - Check - Status?

Better: - Is the payment approved? - Is the application complete? - Has
the customer selected express delivery?

Branches should show the condition that causes the path to be taken.

For an exclusive gateway, check that: - Every expected outcome is
represented. - Conditions do not accidentally overlap. - No possible
outcome is left without a route. - A default path is defined where
appropriate.

For inclusive gateways, check that all valid combinations are handled
and the join waits for the branches that were actually activated.

## 8. Connecting objects --- how elements relate

BPMN uses different connectors for different meanings. The most
important distinction is between **sequence flow** and **message flow**.

### 8.1 Sequence flow

A sequence flow is a solid line with a filled arrowhead.

It shows the order in which activities, events and gateways occur
**inside one process**.

Examples: - Start event → Validate order. - Validate order → Check
payment. - Payment approved → Prepare shipment.

A sequence flow is used within a pool. It does not represent a message
sent from one independent participant to another.

### 8.2 Message flow

A message flow is a dashed line with an open circle at the start and an
open arrowhead at the end.

It represents communication between separate participants, typically
between pools.

Examples: - Customer sends an order to the seller. - Payment provider
returns a payment result. - Seller sends a dispatch request to a
courier. - Courier sends a delivery confirmation to the seller.

A message flow does not show the internal order of work within a
participant's process.

### 8.3 Association

An association connects an artifact, such as a note or data object, to a
BPMN element. It provides context or shows relevant information without
controlling the sequence of the process.

Example: - Attach an "Order details" data object to the task "Validate
order." - Attach a note explaining the refund policy to the refund
decision.

### Connector comparison

  -----------------------------------------------------------------------
  Connector         Appearance        Meaning           Typical use
  ----------------- ----------------- ----------------- -----------------
  Sequence flow     Solid line,       Order of process  Task to task
                    filled arrow      flow              inside a pool

  Message flow      Dashed line, open Communication     Customer pool to
                    arrow             between           seller pool
                                      participants      

  Association       Dotted/dashed     Link to           Note or data
                    association line  supporting        object linked to
                                      information       task
  -----------------------------------------------------------------------

**Common mistake:** drawing a message flow between two tasks in the same
pool. If the line represents the order of work in one process, use
sequence flow.

## 9. Pools and lanes --- who is involved?

Pools and lanes show process participants and responsibilities.

### 9.1 Pool

A **pool** represents a participant in a collaboration. A participant
may be an organization, company, customer, external service provider or
another independent process participant.

Examples: - Customer. - Online retailer. - Payment gateway. - Courier
company.

A pool can contain a process model. A black-box pool may show a
participant without exposing its internal process.

Use separate pools when you need to show interactions between
independent participants.

### 9.2 Lane

A **lane** is a subdivision within a pool. It organizes activities by
role, department, team or system responsibility.

Examples inside an online retailer pool: - Order Management. -
Finance. - Warehouse. - Customer Support.

Lanes help answer: **Who is responsible for this activity?**

### 9.3 Pool vs lane

  -----------------------------------------------------------------------
  Pool                                Lane
  ----------------------------------- -----------------------------------
  Represents a participant            Divides a participant's process by
                                      responsibility

  Often represents an organization or Often represents a role,
  external participant                department, team or system

  Message flows can connect pools     Sequence flows can cross lanes
                                      within the same pool

  Example: Retailer and Payment       Example: Finance and Warehouse
  Provider                            lanes inside Retailer
  -----------------------------------------------------------------------

### 9.4 How to decide whether to use a pool or lane

Ask:

1.  Is this an independent participant in the collaboration?
    -   If yes, consider a separate pool.
2.  Is this a role or department within the same participant?
    -   If yes, consider a lane.
3.  Does the diagram need to show communication between participants?
    -   Use separate pools and message flows.
4.  Does it only need to show responsibility handoffs within one
    organization?
    -   Lanes within one pool may be sufficient.

### 9.5 Sequence flow across lanes

A sequence flow may cross lane boundaries inside the same pool because
it is still one participant's process.

Example: - Order Management validates an order. - The sequence flow
moves to the Warehouse lane. - Warehouse staff prepare the package.

This is a responsibility handoff within the retailer's process, not
necessarily communication between independent participants.

### 9.6 Message flow between pools

A customer and retailer are separate participants. The customer's order
submission can be shown as a message flow from the Customer pool to the
Retailer pool.

A payment provider may be a third pool. The retailer sends a payment
request and receives a payment response through message flows.

## 10. Artifacts and supporting information

Artifacts add useful context without changing the process flow.

### 10.1 Data object

A data object represents information used or produced by an activity.

Examples: - Order details. - Customer application. - Payment receipt. -
Delivery confirmation. - Approval record.

A data object helps the reader understand what information an activity
needs or creates. It does not replace the activity itself.

### 10.2 Text annotation

A text annotation adds an explanatory note to a diagram.

Examples: - "Orders above ₹50,000 require manager approval." - "Payment
is retried once after a temporary failure." - "Manual verification is
required when identity data does not match."

Use annotations for useful context, not to hide essential process logic
that should be represented by activities, gateways or events.

### 10.3 Group

A group visually groups related elements for discussion or
documentation. It does not change the sequence flow or process behavior.

## 11. Step-by-step method to create a basic BPMN model

Follow this sequence when converting a written business process into
BPMN.

### Step 1: Define the process boundary

Write down: - Process name. - Trigger. - End outcomes. - What is
included. - What is excluded.

Example: "Online Order Fulfilment" begins when the retailer receives a
valid order and ends when the order is delivered or cancelled.

### Step 2: Identify participants

List the independent participants: - Customer. - Retailer. - Payment
provider. - Courier.

Decide which participants need their own pools.

### Step 3: Identify internal roles

Within the retailer, identify relevant responsibilities: - Order
Management. - Finance. - Warehouse. - Customer Support.

These can become lanes if the responsibility distinction matters.

### Step 4: List activities in sequence

Write actions using verb + object: - Receive order. - Validate order
details. - Request payment authorization. - Reserve inventory. - Prepare
package. - Dispatch order. - Confirm delivery.

### Step 5: Identify events

Ask: - What starts the process? - Does the process wait for a
response? - Is there a timer or deadline? - What outcomes end the
process?

### Step 6: Identify gateways

Look for decision questions and parallel work: - Is the order valid? ---
exclusive. - Is payment approved? --- exclusive. - Should stock
reservation and invoice generation happen concurrently? --- parallel. -
Which optional services did the customer select? --- inclusive.

### Step 7: Connect the elements

-   Use sequence flow for the order of work within a pool.
-   Use message flow for communication between pools.
-   Use associations for supporting information and annotations.

### Step 8: Add exception paths

Consider: - Invalid order. - Payment declined. - Stock unavailable. -
Courier cannot deliver. - Customer cancels before dispatch.

Do not model only the happy path if important business outcomes are
missing.

### Step 9: Review the logic

Check: - Does each process path start correctly? - Does every path have
a valid continuation or end? - Are gateway conditions clear? - Does the
gateway type match the business rule? - Are all message flows between
participants? - Are lanes used for responsibility rather than
independent participants?

### Step 10: Validate with stakeholders

Walk through the diagram with the people who perform and own the
process. Ask them to explain each activity, decision, handoff and
exception. Record corrections and confirm that the model represents
actual or agreed future behavior.

## 12. Worked scenario --- online order processing

### Business description

A customer submits an order to an online retailer. The retailer
validates the order and requests payment authorization from a payment
provider. If payment is declined, the retailer informs the customer and
closes the order. If payment is approved, the retailer reserves stock
and prepares the shipment. The courier collects and delivers the
package. The retailer records delivery confirmation and closes the
order.

### Participants and lanes

  -----------------------------------------------------------------------
  Pool                    Lane                    Responsibility
  ----------------------- ----------------------- -----------------------
  Customer                Customer                Submit order and
                                                  receive updates

  Online Retailer         Order Management        Validate order and
                                                  coordinate fulfilment

  Online Retailer         Finance                 Record payment result

  Online Retailer         Warehouse               Reserve stock and
                                                  prepare package

  Payment Provider        Payment Service         Authorize or decline
                                                  payment

  Courier                 Delivery Operations     Collect and deliver
                                                  package
  -----------------------------------------------------------------------

The retailer's lanes are subdivisions of one participant. The customer,
payment provider and courier are separate participants.

### Logical process sequence

1.  **Customer pool:** Submit order.
2.  **Retailer --- Order Management:** Receive order message and
    validate order.
3.  **Retailer:** At an exclusive gateway, check whether the order is
    valid.
    -   No → notify customer and end as "Order rejected."
    -   Yes → request payment authorization.
4.  **Payment Provider:** Receive request, process payment and send the
    result.
5.  **Retailer:** Receive payment response.
6.  **Exclusive gateway:** Is payment approved?
    -   No → notify customer and end as "Payment declined."
    -   Yes → continue fulfilment.
7.  **Parallel gateway:** Start stock reservation and invoice generation
    if these activities can safely occur concurrently.
8.  **Parallel join:** Continue after both required activities finish.
9.  **Warehouse:** Prepare package.
10. **Courier:** Collect and deliver package.
11. **Retailer:** Record delivery confirmation.
12. **End event:** Order delivered.

### Which BPMN elements are used?

  -----------------------------------------------------------------------
  Process detail          BPMN element            Why
  ----------------------- ----------------------- -----------------------
  Customer submits order  Message start event or  A customer message
                          message interaction,    triggers retailer
                          depending on model      processing
                          boundary                

  Validate order          User/service task       Work is performed

  Is order valid?         Exclusive gateway       Exactly one outcome is
                                                  selected

  Request payment         Send task or message    Communication with
                          flow                    another participant

  Receive payment result  Receive task or message Retailer receives
                          catch event             provider response

  Is payment approved?    Exclusive gateway       Approved or declined

  Reserve stock and       Parallel gateway and    Two required activities
  generate invoice        tasks                   proceed concurrently

  Both activities         Parallel join           Synchronizes the
  finished                                        branches

  Delivery confirmed      Message event/task,     Courier communicates
                          depending on detail     the delivery result

  Order delivered         End event               Successful process
                                                  outcome
  -----------------------------------------------------------------------

**Modeling note:** BPMN allows multiple valid levels of detail. For
example, a payment interaction can be shown with send/receive tasks and
message flows, or at a higher level with message events. Choose the
level that answers the stakeholder's questions without overcomplicating
the model.

### Example business rules

-   An order must contain at least one item.
-   Payment must be authorized before the order is released for
    fulfilment.
-   An order with unavailable stock cannot be dispatched.
-   A declined payment must not create a completed order.
-   Delivery confirmation is required before the order is marked
    delivered.

### Questions to validate with stakeholders

-   Can a customer edit an order after payment authorization?
-   Is stock reserved before or after payment?
-   Can invoice generation happen in parallel with stock reservation?
-   How many payment retries are allowed?
-   What happens if the payment provider does not respond?
-   What happens if the courier cannot deliver?
-   Who owns customer communication for each exception?

## 13. Worked scenario --- employee leave approval

### Business description

An employee submits a leave request. The HR system checks whether the
request contains required information. If details are missing, the
employee is asked to correct it. If complete, the manager reviews the
request. The manager approves or rejects it. HR records the decision and
the employee receives a notification.

### Suggested BPMN logic

-   **Pool:** Organization.
-   **Lanes:** Employee, HR System, Manager, HR Operations.
-   **Start event:** Leave request submitted.
-   **Task:** Validate request details.
-   **Exclusive gateway:** Is the request complete?
    -   No → Ask employee to update request → employee resubmits.
    -   Yes → Manager reviews request.
-   **Exclusive gateway:** Is leave approved?
    -   Yes → HR records approval.
    -   No → HR records rejection.
-   **Task:** Notify employee.
-   **End events:** Request approved / Request rejected.

### Analysis points

-   The correction loop should return to the appropriate validation
    step.
-   Approval and rejection are alternative outcomes, so an exclusive
    gateway is appropriate.
-   The manager and HR Operations are lanes if they belong to the same
    organizational participant.
-   If an external payroll provider receives a leave update, that
    provider may be represented as a separate pool with message flow.

## 14. Common BPMN mistakes and how to correct them

  -----------------------------------------------------------------------
  Mistake                 Why it is a problem     Better approach
  ----------------------- ----------------------- -----------------------
  Using a task as the     Hides what initiates    Add a start event, then
  start trigger           the process             the task

  Using an XOR gateway    Only one branch is      Use a parallel gateway
  for parallel work       selected                when all branches must
                                                  proceed

  Using an AND gateway    Activates all branches  Use an exclusive
  for alternatives        when only one should be gateway
                          selected                

  Using an inclusive      Allows multiple paths   Use XOR
  gateway when only one   to activate             
  path is allowed                                 

  Connecting pools with   Confuses communication  Use message flow
  sequence flow           with internal process   between pools
                          order                   

  Using message flow      Misrepresents internal  Use sequence flow
  between tasks in one    sequence                
  pool                                            

  Treating departments as Creates unnecessary     Use lanes for internal
  separate participants   pools                   responsibilities
  automatically                                   

  Missing gateway         Readers cannot          Label branches with
  conditions              determine why a path is business conditions
                          selected                

  Showing only the        Omits important         Add rejection, failure
  successful path         business outcomes       and timeout paths

  Putting too much detail Makes the model hard to Use subprocesses and
  in one diagram          read                    separate detailed views

  Using annotations for   Important behavior is   Model the logic with
  essential logic         not represented in the  tasks, events and
                          flow                    gateways

  No stakeholder          Diagram may represent   Walk through each path
  validation              assumptions rather than with process owners
                          reality                 
  -----------------------------------------------------------------------

## 15. BPMN quality checklist

Before sharing a BPMN diagram, review the following:

### Process structure

-   [ ] Process boundary and name are clear.
-   [ ] Start event represents the actual trigger.
-   [ ] End events represent meaningful outcomes.
-   [ ] Activities use clear verb + object labels.
-   [ ] Level of detail is consistent.

### Events and gateways

-   [ ] Events are used for things that happen; tasks are used for work.
-   [ ] Intermediate events represent waits, messages, timers or other
    occurrences where needed.
-   [ ] Gateway type matches the business rule.
-   [ ] Gateway conditions are understandable.
-   [ ] All expected branches are represented.
-   [ ] Parallel branches are joined correctly when synchronization is
    required.

### Participants and connectors

-   [ ] Pools represent participants.
-   [ ] Lanes represent responsibilities within a participant.
-   [ ] Sequence flow is used within a process.
-   [ ] Message flow is used for communication between pools.
-   [ ] Supporting data and notes are linked clearly.

### Business accuracy

-   [ ] Important exceptions and rework loops are included.
-   [ ] Business rules are represented or documented.
-   [ ] No unexplained dead ends exist.
-   [ ] Stakeholders have validated the model.
-   [ ] Assumptions and unresolved questions are recorded.

## 16. Tool awareness --- where BPMN diagrams can be created

A Business Analyst may use a dedicated BPMN modeler or a general
diagramming tool. The important skill is understanding the notation, not
merely knowing where to click.

  -----------------------------------------------------------------------
  Tool                    Typical use             What to understand
  ----------------------- ----------------------- -----------------------
  diagrams.net (draw.io)  General diagrams and    Shapes, connectors,
                          basic BPMN-style        alignment, labels and
                          diagrams                swimlanes

  Lucidchart              Collaborative process   Templates, shared
                          diagrams                editing, comments and
                                                  diagram organization

  Microsoft Visio         Business process        BPMN shapes,
                          diagrams in             containers, connectors
                          organizations           and validation features

  Camunda Modeler         BPMN process modeling,  BPMN events, tasks,
                          especially executable   gateways, pools and
                          process models          model validation
  -----------------------------------------------------------------------

### General workflow in a diagramming tool

1.  Create a blank diagram or choose a BPMN template.
2.  Add a pool for each participant.
3.  Add lanes for roles or departments within a participant.
4.  Place the start event.
5.  Add tasks in the correct sequence.
6.  Add gateways where process routing is required.
7.  Add intermediate and end events where appropriate.
8.  Connect elements using the correct connector type.
9.  Label activities, gateway questions and branch conditions.
10. Add data objects or annotations only where they add useful context.
11. Align and space elements so the diagram can be read left to right or
    top to bottom.
12. Review the diagram with stakeholders and correct the logic.

**Tool tip:** a diagramming application may let you draw an invalid
connection. The fact that a shape can be connected does not mean the
connection is semantically correct in BPMN.

## 17. BPMN vocabulary for quick revision

  -----------------------------------------------------------------------
  Term                                Meaning
  ----------------------------------- -----------------------------------
  BPMN                                Standard visual notation for
                                      business process modeling

  Event                               Something that happens and affects
                                      process flow

  Start event                         Trigger that begins a process

  Intermediate event                  Event that occurs during a process

  End event                           Marks the end of a process path

  Activity                            Work performed in a process

  Task                                A unit of work at the current level
                                      of detail

  Subprocess                          An activity containing a more
                                      detailed process

  Gateway                             Controls how sequence flow is split
                                      or joined

  Exclusive gateway (XOR)             Selects one outgoing path

  Parallel gateway (AND)              Activates all required branches

  Inclusive gateway (OR)              Activates one or more
                                      condition-matching branches

  Sequence flow                       Shows order of flow within a
                                      process

  Message flow                        Shows communication between
                                      participants

  Association                         Links supporting information to an
                                      element

  Pool                                Represents a participant

  Lane                                Divides a pool by role or
                                      responsibility

  Data object                         Represents information used or
                                      produced

  Annotation                          Adds explanatory text

  Group                               Visually groups related elements
                                      without changing flow
  -----------------------------------------------------------------------

## 18. Interview questions and answers

### Q1. What is BPMN?

**Answer:** BPMN stands for Business Process Model and Notation. It is a
standardized visual language used to represent business processes,
including events, activities, decisions, responsibilities and
communication between participants. A BA uses it to document, analyze
and communicate workflows.

### Q2. Why would you use BPMN instead of a simple flowchart?

**Answer:** A simple flowchart is useful for basic steps and decisions.
BPMN provides more specific symbols for events, tasks, gateways,
participants and communication. It is more suitable when a process
involves multiple roles, handoffs, parallel activities or message
exchanges.

### Q3. What is the difference between an event and a task?

**Answer:** An event represents something that happens, such as an order
being received or a deadline expiring. A task represents work performed,
such as validating an order or approving a request.

### Q4. Explain start, intermediate and end events.

**Answer:** A start event indicates what triggers the process. An
intermediate event occurs while the process is running, such as
receiving a response or waiting for a timer. An end event marks the
completion of a process path.

### Q5. What is a gateway in BPMN?

**Answer:** A gateway controls how the process flow is split or joined.
It represents routing logic rather than normal business work. Common
types are exclusive, parallel and inclusive gateways.

### Q6. What is the difference between an exclusive and a parallel gateway?

**Answer:** An exclusive gateway selects one outgoing path based on a
condition. A parallel gateway activates all outgoing branches. For
example, approve or reject uses an exclusive gateway, while sending two
required independent notifications can use a parallel gateway.

### Q7. When would you use an inclusive gateway?

**Answer:** I would use an inclusive gateway when one or more outgoing
conditions can be true. For example, a customer may select gift
wrapping, express delivery, both, or neither if the business rules allow
it.

### Q8. What is the difference between sequence flow and message flow?

**Answer:** Sequence flow shows the order of activities within a
process. Message flow represents communication between separate
participants, usually shown as different pools. A sequence flow is
solid, while a message flow is dashed.

### Q9. What is a pool and what is a lane?

**Answer:** A pool represents a participant such as a customer, company
or external provider. A lane divides a pool into responsibilities such
as departments, teams or roles. Pools show participants; lanes show
responsibility within a participant.

### Q10. Can sequence flow cross lanes?

**Answer:** Yes. Lanes are subdivisions of the same pool, so sequence
flow can cross lane boundaries to show work moving between roles or
departments within that participant.

### Q11. Can sequence flow connect two different pools?

**Answer:** No. Communication between separate pools is represented with
message flow. Sequence flow describes the internal order of one process.

### Q12. What is a subprocess?

**Answer:** A subprocess is an activity that contains a more detailed
sequence of work. It helps keep the main diagram readable while allowing
complex sections to be expanded separately.

### Q13. How would you model a payment approval process?

**Answer:** I would start with an event representing the payment
request, then add a task to submit or process the payment. I would use
an exclusive gateway to evaluate the response. The approved path would
continue to order fulfilment, while the declined path would notify the
customer and end with a payment-declined outcome. If an external payment
provider is involved, I would represent it as a separate pool and show
communication using message flows.

### Q14. How do you decide whether something should be a separate pool or a lane?

**Answer:** I consider whether it is an independent participant or a
responsibility within the same participant. An external payment provider
is usually a separate pool. Finance and Warehouse teams within the
retailer can be lanes in the retailer's pool.

### Q15. What should a BA check before presenting a BPMN diagram?

**Answer:** I would check that the process boundary, start and end
events, activity labels, gateway conditions, participant
responsibilities, connector types and exception paths are clear. I would
then validate the diagram with process owners and people who perform the
work.

### Q16. What is a message start event?

**Answer:** A message start event indicates that a process begins when a
particular message is received. For example, a retailer's order process
may begin when it receives an order submission from a customer.

### Q17. What is the purpose of a timer event?

**Answer:** A timer event represents a time-based trigger or condition.
It can be used to wait until a specified time, schedule an action or
handle a deadline. For example, a payment process may follow a timeout
path if no response arrives within the allowed period.

### Q18. What is the difference between a BPMN diagram and an executable workflow?

**Answer:** A BPMN diagram may be created mainly to communicate and
analyze a business process. An executable workflow is modeled with the
technical details and engine-specific requirements needed for a process
automation platform to run it. Not every business BPMN diagram is
directly executable.

### Q19. How do you handle exceptions in BPMN?

**Answer:** I identify important exception conditions during process
discovery and represent them with suitable gateways, events, tasks and
end outcomes. For example, a declined payment may follow a separate path
that notifies the customer and closes the order. I validate exception
behavior with the process owner.

### Q20. What is the BA's role in BPMN modeling?

**Answer:** The BA discovers and clarifies the process, identifies
participants and responsibilities, documents activities and business
rules, models normal and alternate paths, validates the diagram with
stakeholders and uses the model to identify improvement and requirement
opportunities.

## 19. Knowledge check

Try answering these questions before reading the explanations.

### Questions

1.  Which BPMN element represents the trigger that begins a process?
2.  Which shape is used for a gateway?
3.  A customer can either approve or reject a request. Which gateway is
    appropriate?
4.  A process must start three required activities at the same time.
    Which gateway is appropriate?
5.  A customer may select one or more optional services. Which gateway
    may be appropriate?
6.  Which connector shows the order of work inside one pool?
7.  Which connector shows communication between separate participants?
8.  What does a pool represent?
9.  What does a lane represent?
10. Can sequence flow cross lanes within the same pool?
11. Is "Validate application" an event or a task?
12. Is "Application received" an event or a task?
13. Why might a BA use a subprocess?
14. What should happen if an exclusive gateway has an outcome that is
    not represented by any branch?
15. Who should validate a BPMN model?

### Answers and explanations

1.  **Start event.** It identifies the trigger for process execution.
2.  **Diamond.** Gateways are represented by diamond shapes.
3.  **Exclusive gateway (XOR).** Only one alternative is followed.
4.  **Parallel gateway (AND).** All required branches are activated.
5.  **Inclusive gateway (OR).** One or more condition-matching branches
    can be activated.
6.  **Sequence flow.** It represents internal process order.
7.  **Message flow.** It represents communication between participants.
8.  **A participant.** Examples include a customer, retailer or payment
    provider.
9.  **A responsibility subdivision.** Examples include Finance or
    Warehouse within a retailer pool.
10. **Yes.** Sequence flow can cross lanes inside one pool.
11. **Task.** Validation is work being performed.
12. **Event.** Receipt is something that happens and may trigger work.
13. **To keep the parent diagram readable while showing complex work in
    a separate detailed view.**
14. **Clarify and model the missing outcome.** All valid business
    outcomes need an appropriate route; a default path may be used where
    suitable.
15. **Process owners and people who perform the work, along with
    relevant stakeholders.** Their review helps confirm that the model
    reflects actual or agreed process behavior.

## 20. Day 15 quick revision sheet

Remember these core ideas:

-   BPMN is a standardized language for business process modeling.
-   Events represent things that happen.
-   Tasks represent work performed.
-   Gateways control routing and joining.
-   Start events begin process paths; intermediate events occur during
    them; end events finish them.
-   XOR means one path.
-   AND means all required paths.
-   OR means one or more condition-matching paths.
-   Sequence flow shows internal process order.
-   Message flow shows communication between participants.
-   Pools represent participants.
-   Lanes represent responsibilities within a participant.
-   Subprocesses organize detailed work under a higher-level activity.
-   A good BPMN model includes important alternate and exception paths
    and is validated with stakeholders.

### The simplest way to remember the three gateways

  Business meaning   Gateway
  ------------------ -----------------
  Choose one         Exclusive (XOR)
  Do all             Parallel (AND)
  Do one or more     Inclusive (OR)

### The simplest way to remember connectors

  What are you showing?                         Connector
  --------------------------------------------- ---------------
  What happens next in the same process?        Sequence flow
  A message sent between participants?          Message flow
  A note or data item attached to an element?   Association

## 21. Day 15 completion checklist

-   [ ] I can define BPMN and explain why a BA uses it.
-   [ ] I can distinguish BPMN from a basic flowchart and a process map.
-   [ ] I can identify start, intermediate and end events.
-   [ ] I can explain common message, timer and error event concepts.
-   [ ] I can distinguish tasks from subprocesses.
-   [ ] I can write clear task labels using verb + object.
-   [ ] I can explain exclusive, parallel and inclusive gateways.
-   [ ] I can identify when to use each gateway.
-   [ ] I can distinguish sequence flow, message flow and association.
-   [ ] I can explain pools and lanes.
-   [ ] I can decide whether a department belongs in a lane or an
    independent participant needs a pool.
-   [ ] I can identify data objects and text annotations.
-   [ ] I can read a simple BPMN process and explain its normal and
    exception paths.
-   [ ] I can identify common BPMN modeling mistakes.
-   [ ] I can validate a process model with stakeholders.
-   [ ] I can answer the interview questions in my own words.

------------------------------------------------------------------------

**Day 15 complete --- BPMN Basics: Events, Tasks, Gateways and Pools.**

**Next syllabus topic --- Day 16: AS-IS and TO-BE Process Analysis.**
