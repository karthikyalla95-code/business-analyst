# Day 13 --- Business Process Modeling and Process Discovery

**Phase:** 3 --- Process Modeling and Documentation\
**Approved syllabus topic:** Business process modeling and process
discovery\
**Learning level:** Beginner to advanced\
**Study focus:** Class notes and interview preparation only

------------------------------------------------------------------------

## 1. Learning objectives

By the end of this lesson, you should be able to:

-   Explain what a business process is and why organizations model
    processes.
-   Distinguish a process, procedure, activity, task and workflow.
-   Explain business process modeling (BPM) in practical terms.
-   Identify the start, end, inputs, outputs, roles, systems, decisions
    and exceptions in a process.
-   Discover a process from stakeholder conversations, observation,
    documents and system evidence.
-   Select an appropriate process-discovery technique.
-   Create a structured process inventory and process-discovery record.
-   Validate a discovered process with the people who perform or own it.
-   Recognize common process-discovery mistakes and avoid them.
-   Explain the work of a Business Analyst during process discovery.

## 2. Why business process modeling matters

Organizations achieve results through connected activities. A customer
order, employee onboarding, loan approval or student admission does not
happen through one action. Several people, systems and decisions are
involved.

When a process is not understood clearly, organizations may experience:

-   Repeated data entry.
-   Long waiting times.
-   Unclear responsibility.
-   Missing approvals.
-   Incorrect or incomplete information.
-   Work being sent back for correction.
-   Customers receiving inconsistent updates.
-   Employees depending on informal knowledge rather than a defined
    process.

**Example --- online order**

A customer places an order. The system checks payment, the warehouse
confirms stock, staff pack the item, a courier collects it and the
customer receives it.

If the order is paid but the warehouse does not receive the order
details, the process breaks at a handoff. Modeling helps the BA see
where that handoff occurs and who or what is responsible.

## 3. What is a business process?

A **business process** is a connected set of activities performed by
people, systems or both to produce a defined business result.

A useful way to understand a process is:

**Trigger → Inputs → Activities → Decisions and handoffs → Outputs →
Outcome**

Example:

-   Trigger: A student submits an admission application.
-   Inputs: Application form, identity proof, academic documents and
    payment details.
-   Activities: Register application, check documents and verify
    payment.
-   Decision: Are all required documents valid?
-   Output: Verified application or a request for missing information.
-   Outcome: An application ready for the next admission decision.

A process should have a recognizable purpose and result. A random list
of unrelated tasks is not a meaningful process model.

### 3.1 Characteristics of a business process

A business process generally has:

1.  **Purpose:** Why the process exists.
2.  **Trigger:** What starts it.
3.  **Inputs:** Information, materials or requests needed.
4.  **Activities:** Work performed.
5.  **Sequence:** The order or conditions in which work happens.
6.  **Roles:** People or teams responsible for activities.
7.  **Resources:** Systems, tools, equipment or documents used.
8.  **Rules:** Conditions that guide decisions.
9.  **Outputs:** What the process produces.
10. **Customer or recipient:** Who receives or benefits from the output.
11. **End condition:** What tells us the process instance is complete.
12. **Performance measures:** How effectiveness, speed, quality or cost
    may be evaluated.

Not every process has a customer outside the organization. For example,
an internal employee-access process produces an access decision for an
employee and the IT team.

## 4. Process, procedure, activity, task and workflow

These terms are related, but they are not interchangeable.

  -----------------------------------------------------------------------
  Term                    Meaning                 Example
  ----------------------- ----------------------- -----------------------
  Business process        End-to-end work that    Employee onboarding
                          produces an outcome     

  Procedure               Defined instructions    Steps for verifying
                          for performing work     identity documents

  Activity                A meaningful unit of    Verify employee details
                          work within a process   

  Task                    A smaller action that   Compare the name on two
                          contributes to an       records
                          activity                

  Workflow                The sequence and        Send a request to HR,
                          routing of work         then IT, then the
                                                  manager
  -----------------------------------------------------------------------

### Worked example: employee onboarding

-   Process: Onboard a new employee.
-   Activity: Verify employee information.
-   Task: Check the employee's date of birth against the submitted
    document.
-   Procedure: Follow the organization's identity-verification
    instructions.
-   Workflow: HR creates the employee record, the manager confirms the
    joining date, and IT prepares access.

**Interview tip:** If asked the difference between a process and a
workflow, explain that a process describes the broader business work and
intended result, while a workflow emphasizes how work moves between
steps, people or systems.

## 5. What is business process modeling?

**Business Process Modeling (BPM)** is the practice of representing
business activities, decisions, roles, information and sequence in a
structured visual or written form.

The model gives stakeholders a shared view of how work is performed or
how it is expected to be performed.

A model can be:

-   A high-level process map.
-   A flowchart.
-   A swimlane diagram.
-   A BPMN diagram.
-   A written process description.
-   A combination of a diagram and supporting details.

Day 13 introduces the purpose and discovery work behind process models.
The detailed notation and diagram-building techniques are covered in the
following syllabus days.

### 5.1 Why do BAs model processes?

  -----------------------------------------------------------------------
  Purpose                             Practical value
  ----------------------------------- -----------------------------------
  Understand current work             Shows how work actually happens

  Communicate                         Gives stakeholders a shared picture

  Identify gaps                       Makes missing steps and unclear
                                      handoffs visible

  Find delays                         Helps locate waiting and repeated
                                      work

  Clarify responsibility              Shows which role performs each
                                      activity

  Support requirements                Reveals system actions and business
                                      rules

  Support change                      Provides a baseline for comparing a
                                      proposed process

  Support testing                     Helps identify scenarios and
                                      exceptions that need testing

  Improve consistency                 Reduces dependence on undocumented
                                      knowledge
  -----------------------------------------------------------------------

A process model is not just a drawing. It is a communication and
analysis tool.

## 6. Process levels and hierarchy

A large business process can be broken into smaller levels. The exact
naming varies between organizations, but a useful hierarchy is:

  -----------------------------------------------------------------------
  Level                   What it represents      Example
  ----------------------- ----------------------- -----------------------
  Value chain / business  Broad organizational    Customer service
  area                    capability              

  End-to-end process      A complete business     Resolve customer
                          outcome                 complaint

  Sub-process             A major part of the     Investigate complaint
                          process                 

  Activity                A meaningful piece of   Review transaction
                          work                    history

  Task                    A specific action       Open the customer's
                                                  transaction record
  -----------------------------------------------------------------------

### Example hierarchy

**Business area:** Student admissions

-   **End-to-end process:** Process student admission
    -   Sub-process: Receive application
        -   Activity: Capture applicant details
        -   Activity: Record submitted documents
    -   Sub-process: Verify application
        -   Activity: Check document completeness
        -   Activity: Validate academic details
    -   Sub-process: Communicate decision
        -   Activity: Prepare decision
        -   Activity: Notify applicant

### Why decomposition is useful

-   A high-level model is easier for executives to understand.
-   A detailed model helps operational staff and system teams understand
    specific work.
-   Decomposition prevents one diagram from becoming too large.
-   It helps the BA identify where more discovery is needed.

**Practical rule:** Start with the end-to-end process, then expand only
the areas that need more detail.

## 7. Process boundaries: where does the process start and end?

A process boundary defines what is included in the process being
studied.

A process can appear confusing if different stakeholders use different
start and end points.

Example: In an order-fulfilment discussion:

-   Customer Service may say the process starts when the customer
    submits an order.
-   Warehouse staff may say their process starts when an order appears
    in the fulfilment queue.
-   Finance may say its process starts when payment is authorized.

All three perspectives may be correct because they are describing
different process boundaries.

### 7.1 Define the boundary using four questions

1.  What event starts the process?
2.  What final result marks completion?
3.  Which activities are inside the scope?
4.  Which related activities are outside the scope but interact with it?

**Example --- employee onboarding boundary**

-   Start: HR receives an approved hiring confirmation.
-   Included: Create employee record, collect documents, arrange
    orientation and request system access.
-   End: Employee is ready to begin work with required access and
    onboarding steps completed.
-   Outside scope: Recruitment and long-term performance management.
-   External interaction: Payroll setup may be handled by a separate
    process.

### 7.2 Avoid boundary confusion

Do not assume that a department's boundary is the same as the process
boundary. An end-to-end process often crosses multiple departments.

For example, customer order fulfilment may involve Sales, Payment,
Warehouse, Logistics and Customer Support.

## 8. Process elements a BA must discover

A process model is only as useful as the information behind it. During
discovery, identify the following elements.

### 8.1 Trigger

A trigger is the event or condition that starts a process instance.

Examples:

-   Customer submits an order.
-   Employee joins the organization.
-   A payment is received.
-   A complaint is registered.
-   A scheduled review date arrives.

Ask: **What exactly causes this work to begin?**

### 8.2 Inputs

Inputs are the information, requests, materials or resources needed to
perform the process.

Examples:

-   Customer details.
-   Application form.
-   Purchase order.
-   Supporting documents.
-   Payment confirmation.

Ask:

-   What information is required?
-   Who provides it?
-   In what format?
-   What happens if it is missing or incorrect?

### 8.3 Activities and tasks

Activities describe the work performed.

Example:

-   Receive application.
-   Check completeness.
-   Verify documents.
-   Record the result.
-   Notify the applicant.

For each activity, discover:

-   Who performs it?
-   What information is used?
-   Which system or tool is used?
-   What is the expected result?
-   How long does it normally take?
-   What can go wrong?

### 8.4 Decisions and business rules

A decision is a point where the next step depends on a condition.

Example:

**Are all mandatory documents valid?**

-   Yes: Move the application to the next review stage.
-   No: Request missing or corrected documents.

A business rule defines the condition or policy used to make the
decision.

Example rule: An application cannot move to final review until all
mandatory documents have been verified.

Do not record only the word "approved" or "rejected." Discover the
actual conditions, authority and exceptions.

### 8.5 Roles and responsibilities

Identify who performs, owns, approves, supports or receives the work.

Examples:

-   Applicant.
-   Admissions officer.
-   Department reviewer.
-   Finance officer.
-   System administrator.

A role is not necessarily a named individual. Record the business role
or team unless a specific person is genuinely relevant.

### 8.6 Handoffs

A handoff occurs when responsibility or work moves from one person, team
or system to another.

Example:

Admissions officer verifies the documents and sends the application to
the academic department for review.

Discover:

-   What information is transferred?
-   How is the handoff performed?
-   Who receives it?
-   How does the receiver know work is waiting?
-   Can the work be rejected or returned?
-   How is ownership tracked?

Handoffs are common locations for delays, lost information and unclear
responsibility.

### 8.7 Systems and tools

Record the systems used at each step.

Examples:

-   Customer relationship management (CRM) system.
-   Enterprise resource planning (ERP) system.
-   Email.
-   Spreadsheet.
-   Document-management system.
-   Payment gateway.
-   Paper form.

Also discover manual workarounds. A process may appear automated on
paper while staff actually copy information into spreadsheets or send
emails to complete it.

### 8.8 Outputs and outcomes

An **output** is the direct result of an activity or process.

An **outcome** is the broader effect or value created by that result.

Example:

-   Output: A verified student application.
-   Outcome: The college can make an admission decision using complete
    and checked information.

### 8.9 Exceptions and rework

An exception is a situation that does not follow the normal path.

Examples:

-   Required document is missing.
-   Payment fails.
-   Customer provides invalid information.
-   Manager is unavailable to approve.
-   System is temporarily unavailable.

Rework occurs when work must be repeated or corrected.

Example: An application is returned to the student because the uploaded
document is unreadable. The student uploads it again, and the officer
repeats the check.

**Important:** Discovering only the normal path gives an incomplete
picture of the real process.

## 9. Process discovery: meaning and purpose

**Process discovery** is the systematic activity of finding out how a
business process actually works, including its steps, roles, decisions,
systems, information, exceptions and performance.

The word "actually" matters.

A documented procedure may describe the official process, while
employees may follow additional steps because of system limitations,
customer needs or informal practices.

### 9.1 What process discovery should establish

At the end of discovery, the BA should understand:

-   The business purpose and expected outcome.
-   The process owner and key participants.
-   The start and end boundaries.
-   The normal sequence of activities.
-   Decisions and business rules.
-   Roles and handoffs.
-   Inputs, outputs and information used.
-   Systems and manual workarounds.
-   Exceptions, rework and escalation paths.
-   Known delays, pain points and controls.
-   Available evidence and unresolved questions.

### 9.2 Discover the actual process, not the assumed process

Consider this statement from a manager:

"All applications are verified within one day."

An admissions officer may explain that the one-day target applies only
when documents are complete. Incomplete applications wait for the
student to respond. The system may also show a status as "under review"
even when no officer has started the work.

The BA should investigate these differences rather than copying the
manager's statement as fact.

## 10. Process discovery techniques

A BA usually combines multiple techniques. No single technique provides
the full picture.

### 10.1 Stakeholder interviews

A planned conversation with people who perform, manage, support or
receive the process.

Useful for discovering:

-   Why an activity is performed.
-   Informal decision rules.
-   Exceptions.
-   Frustrations and workarounds.
-   Differences between teams.

Example questions:

-   "Please walk me through the last application you processed."
-   "What happens after you receive the application?"
-   "What information do you check?"
-   "What happens when a document is missing?"
-   "Who receives the application after your review?"

**Strength:** Provides detailed explanations and context.\
**Limitation:** People may forget steps, describe the ideal process or
give different accounts.

### 10.2 Workshops

A facilitated group session involving multiple stakeholders.

Useful for:

-   Agreeing on process boundaries.
-   Comparing different department perspectives.
-   Identifying handoffs.
-   Resolving conflicting descriptions.
-   Confirming a shared process view.

Example: Admissions, Finance and IT representatives jointly explain what
happens between application submission and confirmation.

**Strength:** Differences can be discussed immediately.\
**Limitation:** Senior or confident participants may dominate; quieter
participants may not share important details.

### 10.3 Direct observation

The BA watches people perform the work in its real environment.

Useful for identifying:

-   Steps people forget to mention.
-   Repeated data entry.
-   Waiting.
-   Physical movement or document transfers.
-   Informal communication.
-   Actual system usage.

Example: Observe an admissions officer processing an application from
the moment it enters the queue.

**Strength:** Reveals actual behavior.\
**Limitation:** Observation takes time, and people may change their
behavior when being watched.

### 10.4 Document analysis

Review existing material that describes or records the process.

Examples:

-   Standard operating procedures (SOPs).
-   Policy documents.
-   Forms and templates.
-   Checklists.
-   Approval matrices.
-   Reports.
-   Email templates.
-   System manuals.
-   Audit records.

Useful for discovering formal rules, required information, controls and
documented responsibilities.

**Strength:** Provides evidence and historical context.\
**Limitation:** Documents may be outdated, incomplete or inconsistent
with actual practice.

### 10.5 System and data analysis

Review available system screens, logs, timestamps, reports, transaction
records or audit trails, subject to access and privacy rules.

Useful for identifying:

-   Actual sequence of recorded events.
-   Processing and waiting time.
-   Transaction volumes.
-   Repeated attempts.
-   Error patterns.
-   Differences between teams or periods.

Example: Compare the time an application is submitted with the time it
is first opened by an officer and the time it is verified.

**Strength:** Can reveal patterns across many process instances.\
**Limitation:** System data may not record manual work, informal
decisions or the reason for a delay.

### 10.6 Surveys and questionnaires

Collect standardized information from a wider group.

Useful for:

-   Measuring how often a problem occurs.
-   Comparing experiences across teams.
-   Identifying common pain points.
-   Gathering feedback before deeper interviews.

**Strength:** Can reach many respondents.\
**Limitation:** Usually provides less depth than interviews and may
suffer from low response rates or unclear questions.

### 10.7 Process mining --- introductory awareness

Process mining uses event data from information systems to reconstruct
and analyze process behavior.

An event log commonly contains:

-   Case or process-instance ID.
-   Activity name.
-   Timestamp.
-   Optional resource or user.
-   Optional additional attributes.

Example event log:

  Case ID   Activity                     Timestamp
  --------- ---------------------------- -----------------
  A101      Application submitted        09:00
  A101      Document check started       09:25
  A101      Missing document requested   09:40
  A101      Document received            Next day, 11:00
  A101      Verification completed       Next day, 11:20

This sequence can help distinguish active processing time from waiting
time.

Process mining is not the same as interviewing or manually drawing a
process. It analyzes recorded event data. It may miss work that is not
captured by the system.

## 11. Choosing the right discovery technique

  -----------------------------------------------------------------------
  Discovery need          Useful technique        Why
  ----------------------- ----------------------- -----------------------
  Understand why staff    Interview               Allows probing and
  follow a certain step                           follow-up

  Agree on a cross-team   Workshop                Brings stakeholders
  process                                         together

  See what employees      Observation             Shows actual work
  really do                                       

  Understand formal rules Document analysis       Reviews approved
                                                  material

  Measure volume and      System/data analysis    Uses recorded evidence
  delays                                          

  Gather broad feedback   Questionnaire           Standardizes responses

  Reconstruct             Process mining          Analyzes event logs
  system-recorded paths                           
  -----------------------------------------------------------------------

### Use more than one source

Suppose a manager says applications take one day, officers say three
days, and system records show a median of two days.

Do not immediately choose one answer. Clarify:

-   Are all three measuring the same start and end points?
-   Does the manager mean working time or elapsed time?
-   Are incomplete applications included?
-   Are weekends excluded?
-   Does the system timestamp capture the real start of work?

This is called **triangulation**: comparing information from different
sources to improve confidence in the findings.

## 12. A practical step-by-step process discovery approach

### Step 1: Understand the business context

Clarify:

-   Why is the process being studied?
-   What business problem or opportunity triggered the work?
-   Who owns the process?
-   Which customers or internal users are affected?
-   What outcome matters?

Example: The college wants to reduce admission-processing delays and
repeated student enquiries.

### Step 2: Define the process scope

Write down:

-   Process name.
-   Start event.
-   End event.
-   Included activities.
-   Excluded activities.
-   Related processes and interfaces.

Example: Start when an application is submitted; end when the
application is marked verified or returned for correction. The final
admission decision is outside this discovery boundary.

### Step 3: Identify stakeholders and participants

Include people who:

-   Perform the work.
-   Approve or control it.
-   Own the process.
-   Provide information.
-   Receive the output.
-   Support the systems.
-   Experience the service as a customer.

Do not interview only managers. Frontline employees often know the
operational details and exceptions.

### Step 4: Collect existing evidence

Request relevant documents, forms, reports, system screens and policies.

Record:

-   Document name and owner.
-   Version or date.
-   Whether it is approved.
-   What part of the process it describes.
-   Any conflict with stakeholder explanations.

### Step 5: Plan discovery sessions

For each session, define:

-   Objective.
-   Participants and roles.
-   Topics to cover.
-   Questions.
-   Evidence to review.
-   Time required.
-   Note-taking responsibility.
-   Follow-up actions.

### Step 6: Walk through a real process instance

Ask a participant to describe or demonstrate a recent, representative
case.

A real example is often more useful than asking, "How do you normally do
this?"

Follow the case from trigger to completion. Record each activity,
decision, handoff, system and exception.

### Step 7: Capture the process elements

Use a structured table:

  --------------------------------------------------------------------------------------------------
          Step Activity      Role         Input          System/tool   Output         Next step /
                                                                                      decision
  ------------ ------------- ------------ -------------- ------------- -------------- --------------
             1 Receive       Admissions   Submitted form Portal        Application    Completeness
               application   system /                                  record         check
                             officer                                                  

             2 Check         Admissions   Application    Portal        Check result   Valid or
               documents     officer      and files                                   incomplete

            3A Request       Admissions   Missing-item   Email /       Request sent   Wait for
               missing file  officer      details        portal                       student

            3B Send for      Admissions   Complete file  Portal        Review-ready   Academic
               review        officer                                   record         review
  --------------------------------------------------------------------------------------------------

This table is a discovery record, not yet a detailed flowchart.

### Step 8: Capture exceptions and variations

Ask:

-   What happens when information is missing?
-   What happens when a system is unavailable?
-   Are there different paths for different customer types?
-   Who handles urgent cases?
-   What happens when an approval is rejected?
-   Can work be returned to an earlier step?

### Step 9: Identify pain points without jumping to solutions

Record the observed issue and its evidence.

Weak note: "The portal needs automation."

Better note: "Officers manually copy applicant details from the portal
into a spreadsheet. In the observed sample, this happened for every
application and took approximately three minutes per record."

The second note describes a current-state observation. Automation may be
one solution option, but it should not be assumed before analysis.

### Step 10: Validate the findings

Share the discovered process with relevant participants.

Ask them to confirm:

-   Is the sequence accurate?
-   Are the roles correct?
-   Are decisions and rules complete?
-   Are exceptions represented?
-   Does the process vary by department or case type?
-   What has been missed?

Record corrections, unresolved differences and approval status.

### Step 11: Organize the discovery output

A process-discovery record can contain:

1.  Process purpose and context.
2.  Process owner and stakeholders.
3.  Scope and boundaries.
4.  Trigger and end condition.
5.  Inputs and outputs.
6.  Activities and sequence.
7.  Roles and responsibilities.
8.  Systems and documents.
9.  Decisions and business rules.
10. Handoffs.
11. Exceptions and rework.
12. Pain points and supporting evidence.
13. Performance information.
14. Assumptions and open questions.
15. Validation feedback and next steps.

This is a documentation structure to organize findings, not an
independent project assignment.

## 13. Worked example --- student admission application process

### 13.1 Business context

A college receives applications through an online portal. Students
complain that they do not know which documents are missing. Admissions
officers spend time answering status enquiries and checking
spreadsheets.

**Discovery objective:** Understand the current application-receipt and
document-verification process, including delays, handoffs and
exceptions.

### 13.2 Scope

-   Start: Student submits an application.
-   End: Application is marked document-verified or returned for
    correction.
-   Included: Application receipt, completeness check, document
    verification and communication.
-   Excluded: Final academic selection and fee payment after admission
    offer.

### 13.3 Stakeholders

  Stakeholder          What they know or contribute
  -------------------- --------------------------------------------------
  Student              Submission experience and communication problems
  Admissions officer   Daily processing steps and exceptions
  Admissions manager   Policy, targets and approval responsibilities
  IT support           Portal behavior and technical issues
  Academic reviewer    Information needed for the next stage

### 13.4 Discovered normal flow

1.  Student completes the application form.
2.  Student uploads required documents.
3.  Portal records the submission.
4.  Admissions officer opens the application.
5.  Officer checks whether all mandatory documents are present.
6.  Officer verifies document details.
7.  If documents are valid, the officer marks the application as
    verified.
8.  The application moves to the next review stage.

### 13.5 Discovered exception flow

If a document is missing or unreadable:

1.  Officer identifies the issue.
2.  Officer records the missing or incorrect item.
3.  Officer sends an email to the student.
4.  Application waits for the student to respond.
5.  Student uploads a replacement document.
6.  Officer checks the new document.
7.  The application either becomes verified or is returned again.

### 13.6 Discovery findings

  -----------------------------------------------------------------------
  Finding                 Evidence to collect     Why it matters
  ----------------------- ----------------------- -----------------------
  Students cannot easily  Student interviews and  Creates repeated
  identify missing        portal review           enquiries
  documents                                       

  Officers send separate  Observation and email   Adds manual work
  emails                  templates               

  Applications wait for   Timestamp analysis      Waiting may dominate
  student responses                               total elapsed time

  Officers use a          Observation and         Creates duplicate
  spreadsheet to track    spreadsheet review      records
  pending cases                                   

  Verification rules are  Interviews and policy   May cause inconsistent
  not clear to all        review                  decisions
  officers                                        
  -----------------------------------------------------------------------

### 13.7 Separate fact, interpretation and question

  -----------------------------------------------------------------------
  Type                                Example
  ----------------------------------- -----------------------------------
  Fact / observation                  Officers use a spreadsheet to list
                                      pending applications

  Interpretation / hypothesis         Duplicate tracking may increase
                                      effort or create inconsistent
                                      status information

  Open question                       Is the spreadsheet the official
                                      tracking method or an informal
                                      workaround?
  -----------------------------------------------------------------------

This separation prevents the BA from presenting an assumption as a
confirmed cause.

### 13.8 What should the BA do next?

-   Confirm the steps with more than one admissions officer.
-   Check the official document-verification policy.
-   Review portal statuses and available timestamps.
-   Ask students how they learn which document is missing.
-   Confirm whether all application categories follow the same route.
-   Record unresolved differences before finalizing the process
    description.

## 14. Process discovery documentation templates

These templates are practical note-taking formats for BA work.

### 14.1 Process overview

  Field                  What to record
  ---------------------- -----------------------------------
  Process name           Clear business process title
  Purpose                Why the process exists
  Process owner          Role accountable for the process
  Trigger                Event that starts the process
  End condition          Event or result that completes it
  Customer / recipient   Who receives the output
  Scope                  Included and excluded work
  Participants           Roles and teams involved
  Systems                Applications and tools used
  Key outputs            Results produced
  Known issues           Reported or observed problems
  Open questions         Items requiring confirmation

### 14.2 Activity discovery log

  Field           Example
  --------------- -------------------------------------------
  Activity ID     ACT-03
  Activity name   Verify uploaded documents
  Performer       Admissions officer
  Trigger         Application enters verification queue
  Input           Application and uploaded files
  Steps           Open file, compare details, record result
  System          Admission portal
  Business rule   All mandatory documents must be valid
  Output          Verified or correction required
  Next owner      Academic review team or student
  Exception       File is unreadable
  Evidence        Officer walkthrough and policy document

### 14.3 Open-question log

  --------------------------------------------------------------------------
  ID             Question       Why it matters Owner to       Status
                                               clarify        
  -------------- -------------- -------------- -------------- --------------
  Q-01           Are weekends   Defines how    Admissions     Open
                 included in    processing     manager        
                 the processing time is                       
                 target?        measured                      

  Q-02           Can officers   Clarifies      Process owner  Open
                 reject a       authority and                 
                 document       decision rules                
                 directly?                                    

  Q-03           Does the       Helps measure  IT support     Open
                 portal record  queue waiting                 
                 the first time                               
                 an officer                                   
                 opens an                                     
                 application?                                 
  --------------------------------------------------------------------------

### 14.4 Evidence log

  --------------------------------------------------------------------------
  Evidence       Source         Date / version What it        Limitation
                                               supports       
  -------------- -------------- -------------- -------------- --------------
  Verification   Admissions     Current        Formal         May not show
  policy         manager        approved       document rules informal work
                                version                       

  Officer        Admissions     Session date   Actual         One person's
  walkthrough    officer                       sequence and   experience
                                               workarounds    

  Portal         System report  Selected       Recorded       May not
  timestamps                    period         timing         capture
                                                              offline work
  --------------------------------------------------------------------------

## 15. Process performance: what to observe during discovery

Even when the lesson is focused on discovering the process, the BA
should notice what can be measured.

  -----------------------------------------------------------------------
  Measure                 Meaning                 Example
  ----------------------- ----------------------- -----------------------
  Throughput              Number of cases         300 applications per
                          completed in a period   week

  Cycle time              Time taken for a        2 working days
                          process instance from   
                          defined start to end    

  Processing time         Time spent actively     35 minutes
                          performing work         

  Waiting time            Time a case waits       1.5 days waiting for a
                          before the next         document
                          activity                

  Error rate              Proportion of cases     12 incorrect records
                          with an error           out of 200

  Rework rate             Proportion of cases     30 returned
                          requiring repeated work applications out of 200

  First-time-right rate   Proportion completed    170 out of 200
                          correctly without       
                          rework                  

  Backlog                 Work waiting to be      85 pending applications
                          processed               
  -----------------------------------------------------------------------

### 15.1 Do not confuse processing time and cycle time

Suppose an application requires:

-   10 minutes for the initial check.
-   15 minutes for document verification.
-   10 minutes for recording the result.
-   1 day waiting for a student to upload a missing document.

Active processing time = 10 + 15 + 10 = 35 minutes.

Elapsed cycle time is much longer because it includes waiting. The exact
cycle-time calculation depends on the agreed start and end timestamps
and whether non-working hours are included.

### 15.2 Ask measurement questions

-   What is the normal volume?
-   How is completion time measured?
-   Are timestamps reliable?
-   Is the measure based on working hours or calendar time?
-   Are incomplete and cancelled cases included?
-   Are averages hiding a small number of very delayed cases?
-   Is there a target, and who owns it?

A BA should record the definition and source of a metric, not just its
number.

## 16. Common process discovery challenges

### 16.1 People describe the ideal process

**Problem:** A stakeholder explains what should happen rather than what
actually happens.

**BA response:** Ask for a recent real example and walk through it step
by step.

### 16.2 Different stakeholders describe different processes

**Problem:** Teams have different responsibilities, local practices or
interpretations.

**BA response:** Identify where the process varies, document each
legitimate path and facilitate clarification with the process owner.

### 16.3 Informal work is hidden

**Problem:** Employees use calls, spreadsheets, personal reminders or
side emails that are absent from official documents.

**BA response:** Ask what they do when the official system does not
support the work and observe real cases where appropriate.

### 16.4 Exceptions are ignored

**Problem:** The model covers only the happy path.

**BA response:** Ask "What can go wrong?" and "What happens next?" for
each important step.

### 16.5 The BA jumps to a solution

**Problem:** The BA hears about a manual step and immediately proposes
automation.

**BA response:** First understand the reason, rule, frequency, risk and
business value of the step. Then evaluate solution options.

### 16.6 Too much detail is collected

**Problem:** The model becomes difficult to read and maintain.

**BA response:** Start with an end-to-end overview and expand complex or
important areas separately.

### 16.7 Documents are outdated

**Problem:** The SOP does not match current practice.

**BA response:** Record its version, owner and approval status, then
compare it with interviews, observation and system evidence.

### 16.8 Stakeholders are unavailable

**Problem:** Important process knowledge is held by busy employees.

**BA response:** Agree on focused sessions, use short walkthroughs,
review existing evidence and record assumptions for later confirmation.

## 17. What a Business Analyst should and should not do

  -----------------------------------------------------------------------
  A BA should                         A BA should avoid
  ----------------------------------- -----------------------------------
  Ask neutral, open questions         Suggest answers through leading
                                      questions

  Observe real work where possible    Assume a policy document is always
                                      followed

  Include frontline and management    Interview only senior managers
  perspectives                        

  Record exceptions and workarounds   Capture only the happy path

  Separate facts from assumptions     Present guesses as confirmed facts

  Confirm process boundaries          Allow scope to remain unclear

  Validate findings with stakeholders Treat the first draft as final

  Record evidence and open questions  Rely only on memory

  Understand before recommending      Jump immediately to automation
  -----------------------------------------------------------------------

## 18. Interview questions and answers

### Q1. What is a business process?

A business process is a connected set of activities performed by people,
systems or both to produce a defined business result. For example, order
fulfilment includes receiving an order, checking payment, preparing the
item and arranging delivery.

### Q2. What is business process modeling?

Business process modeling is the structured representation of
activities, decisions, roles, information and sequence involved in
business work. It helps stakeholders understand, communicate and analyze
a process.

### Q3. What is process discovery?

Process discovery is the systematic investigation of how a process
actually operates. It identifies activities, roles, inputs, outputs,
decisions, systems, handoffs, exceptions and performance information.

### Q4. Why is process discovery important before proposing a solution?

Without discovery, a BA may solve the wrong problem or miss important
rules and exceptions. Understanding the actual process helps ensure that
proposed changes address the real business need.

### Q5. What is the difference between a process and a procedure?

A process describes the connected work that produces a business outcome.
A procedure provides instructions for performing particular work within
that process.

### Q6. What is the difference between an activity and a task?

An activity is a meaningful unit of work, such as verifying an
application. A task is a smaller action within it, such as comparing the
applicant's name with an identity document.

### Q7. What techniques can a BA use for process discovery?

Common techniques include stakeholder interviews, workshops, direct
observation, document analysis, questionnaires, system/data analysis and
process mining. The BA selects and combines techniques based on the
process and available evidence.

### Q8. Why is observation useful?

Observation allows the BA to see actual work, including informal steps,
system usage, handoffs, waiting and workarounds that stakeholders may
forget to mention.

### Q9. What is a process boundary?

A process boundary defines where the process starts and ends and which
activities are included or excluded. Clear boundaries prevent
stakeholders from discussing different parts of a larger process as
though they were the same.

### Q10. What is a process handoff?

A handoff occurs when work or responsibility moves from one role, team
or system to another. Poor handoffs can create delays, missing
information and unclear ownership.

### Q11. What is triangulation in process discovery?

Triangulation means comparing information from multiple sources, such as
interviews, observations, documents and system records. It helps
identify contradictions and increases confidence in findings.

### Q12. Why should a BA identify exceptions?

Exceptions show what happens when the normal path cannot continue. If
they are ignored, the process description will be incomplete and may
fail to represent important real-world situations.

### Q13. What is the difference between processing time and waiting time?

Processing time is the time spent actively performing work. Waiting time
is the time a case spends waiting for an action, person, decision or
information. Both can contribute to total elapsed cycle time.

### Q14. What is process mining?

Process mining analyzes event data recorded by information systems to
discover and examine actual process paths. It can reveal variations,
delays and repeated activities, but it is limited by what the systems
record.

### Q15. What should a BA do when stakeholders provide conflicting process descriptions?

The BA should record the differences, identify whether they reflect
different process variants or inconsistent practices, gather evidence,
and discuss the issue with relevant participants and the process owner.
The BA should not silently choose one version.

### Q16. How do you ensure that discovered process information is accurate?

Use multiple discovery techniques, walk through real cases, compare
stakeholder explanations with documents and system evidence, record
uncertainties, and validate the findings with the people who perform and
own the process.

### Q17. What is a process owner?

A process owner is the role accountable for the overall performance and
governance of a process. The owner may not personally perform every
activity.

### Q18. What is the difference between an output and an outcome?

An output is the direct result produced by the process, such as a
verified application. An outcome is the broader effect, such as enabling
a timely and informed admission decision.

### Q19. How can a BA identify bottlenecks during discovery?

The BA can examine queues, handoffs, waiting time, repeated work,
approval delays, system timestamps and stakeholder feedback. A suspected
bottleneck should be supported by evidence rather than assumed from one
complaint.

### Q20. What would you do if the official SOP differs from actual employee behavior?

I would record the difference, understand why employees follow the
alternative method, check whether the SOP is current and approved, and
discuss the gap with the process owner. I would not assume either source
is correct without investigation.

## 19. Knowledge check

Try answering before reading the explanations.

### Questions

1.  What are the three broad parts of a process when described simply?
    -   A. Trigger, activities and outcome
    -   B. Team, salary and budget
    -   C. Design, coding and deployment
    -   D. Login, logout and password
2.  Which technique is most useful for seeing how an employee actually
    performs work?
    -   A. Document analysis only
    -   B. Direct observation
    -   C. Guessing
    -   D. Project estimation
3.  What does a process boundary define?
    -   A. The employee's job title
    -   B. The start, end and scope of the process
    -   C. The software license
    -   D. The project budget only
4.  An application waits two days for a missing document. This is
    primarily:
    -   A. Processing time
    -   B. Waiting time
    -   C. Development time
    -   D. Testing time
5.  Why should a BA compare interviews, documents and system evidence?
    -   A. To create more paperwork
    -   B. To avoid speaking to stakeholders
    -   C. To identify contradictions and improve confidence
    -   D. To replace process validation
6.  A manager describes the official process, but employees use an
    additional spreadsheet. What should the BA do?
    -   A. Ignore the spreadsheet
    -   B. Immediately demand its removal
    -   C. Investigate and document the actual use and reason
    -   D. Assume the manager is incorrect
7.  What is a handoff?
    -   A. A process ending permanently
    -   B. Work moving between roles, teams or systems
    -   C. A performance review
    -   D. A type of database
8.  Which statement correctly describes process mining?
    -   A. It analyzes recorded event data to understand process
        behavior
    -   B. It is another name for interviewing
    -   C. It guarantees that all manual work is visible
    -   D. It replaces business rules

### Answers with explanations

1.  **A** --- A process can be understood through its trigger, connected
    activities and intended result.
2.  **B** --- Observation reveals actual work, including informal steps
    and workarounds.
3.  **B** --- Boundaries define where the process begins and ends and
    what is included.
4.  **B** --- The case is waiting for information rather than being
    actively processed.
5.  **C** --- Multiple sources help identify gaps and conflicting
    accounts.
6.  **C** --- The spreadsheet may be a workaround or an important
    operational control. Investigate before judging it.
7.  **B** --- A handoff transfers work or responsibility.
8.  **A** --- Process mining uses system event data; it cannot show work
    that is never recorded.

## 20. Day 13 revision sheet

  -----------------------------------------------------------------------
  Topic                               Remember
  ----------------------------------- -----------------------------------
  Business process                    Connected activities that produce a
                                      business result

  Process modeling                    Structured representation of
                                      business work

  Process discovery                   Investigation of how work actually
                                      happens

  Trigger                             Event that starts a process

  Input                               Information or resource needed

  Activity                            Meaningful unit of work

  Task                                Smaller action within an activity

  Decision                            Point where a condition determines
                                      the next path

  Business rule                       Policy or condition guiding
                                      business behavior

  Handoff                             Transfer of work or responsibility

  Output                              Direct result produced

  Outcome                             Broader business effect

  Process boundary                    Start, end and included scope

  Exception                           Situation outside the normal path

  Rework                              Repeated or corrected work

  Triangulation                       Comparing multiple sources of
                                      evidence

  Process mining                      Analysis of system event data

  Cycle time                          Elapsed time across a defined
                                      process instance

  Processing time                     Active time spent doing work

  Waiting time                        Time spent waiting for the next
                                      action
  -----------------------------------------------------------------------

### Quick mental checklist for process discovery

For any process, ask:

1.  Why does it exist?
2.  What starts it?
3.  What completes it?
4.  What information is needed?
5.  What activities happen and in what order?
6.  Who performs each activity?
7.  Which systems and documents are used?
8.  Where are the decisions and rules?
9.  Where does work move between people or teams?
10. What happens when something goes wrong?
11. Where does work wait or get repeated?
12. What evidence supports the description?
13. Have the findings been validated?

## 21. Day 13 completion checklist

-   [ ] I can define a business process with a practical example.
-   [ ] I can distinguish a process, procedure, activity, task and
    workflow.
-   [ ] I can explain business process modeling and its benefits.
-   [ ] I can describe process hierarchy and decomposition.
-   [ ] I can define process boundaries, triggers and end conditions.
-   [ ] I can identify inputs, activities, decisions, roles, handoffs,
    systems, outputs and outcomes.
-   [ ] I can explain process discovery and why actual practice matters.
-   [ ] I can compare interviews, workshops, observation and document
    analysis.
-   [ ] I understand system/data analysis and process mining at an
    introductory level.
-   [ ] I can explain triangulation and validate conflicting evidence.
-   [ ] I can distinguish processing time, waiting time and cycle time.
-   [ ] I can record exceptions, workarounds and open questions.
-   [ ] I can explain the BA's responsibilities during process
    discovery.
-   [ ] I can answer the interview questions in my own words.

------------------------------------------------------------------------

**Day 13 complete --- Business Process Modeling and Process Discovery.**

**Next syllabus topic --- Day 14: Flowcharts, activities, decisions and
process boundaries.**
