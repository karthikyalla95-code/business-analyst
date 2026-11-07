# Day 9 --- Requirement Analysis, Prioritization and MoSCoW

**Phase:** 2 --- Requirements Engineering\
**Approved syllabus topic:** Requirement analysis, prioritization and
MoSCoW\
**Estimated study time:** 2--3 hours\
**Difficulty:** Intermediate\
**Prerequisites:** Day 6 --- Requirement types; Day 7 --- Elicitation,
interviews and questionnaires; Day 8 --- Workshops, brainstorming,
observation and document analysis.

------------------------------------------------------------------------

## Learning objectives

By the end of this lesson, you should be able to:

1.  Explain what requirement analysis means and why raw stakeholder
    requests need analysis.
2.  Examine requirements for clarity, completeness, consistency,
    feasibility, relevance and testability.
3.  Identify ambiguity, duplication, conflict, dependency and missing
    information.
4.  Break broad requirements into smaller, understandable requirements.
5.  Explain why requirements must be prioritized and identify useful
    prioritization factors.
6.  Apply the MoSCoW technique correctly and explain its limitations.
7.  Communicate prioritization decisions and record the reasoning behind
    them.

------------------------------------------------------------------------

# 1. Why requirement analysis matters

Imagine a college asks a team to build an online admission portal.
During interviews and workshops, stakeholders request:

-   Students should be able to apply online.
-   The portal should be fast.
-   Applicants should receive updates.
-   Staff should be able to approve applications.
-   The system should support every document format.
-   Management wants reports.

These statements are useful starting points, but they are not yet a
complete, implementation-ready set of requirements.

Questions immediately arise:

-   What does "fast" mean?
-   Which document formats are actually required?
-   Which application updates should be sent, and through which channel?
-   Can staff reject applications as well as approve them?
-   Which reports does management need?
-   What should happen if a student submits an incomplete application?

A Business Analyst (BA) analyzes the information to discover what each
statement means, whether it is complete and realistic, whether it
conflicts with another requirement, and how important it is.

**Requirement analysis** turns collected information into requirements
that are understandable, sufficiently detailed, consistent, feasible and
useful for making decisions.

**Prioritization** determines which requirements matter most when time,
budget, people or other resources are limited.

The two activities work together:

``` text
Stakeholder input
       |
       v
Understand the business need
       |
       v
Analyze and clarify requirements
       |
       v
Check quality, gaps and conflicts
       |
       v
Prioritize requirements
       |
       v
Review with stakeholders
       |
       v
Baseline / agreed requirement set
```

A BA does not simply choose features based on personal preference. The
BA supports decisions using business value, risk, urgency, dependencies,
effort and stakeholder input. The authorized decision-maker or agreed
governance process confirms priorities.

------------------------------------------------------------------------

# 2. Words you need

  -----------------------------------------------------------------------
  Term                    Plain-English meaning   Example
  ----------------------- ----------------------- -----------------------
  Requirement analysis    Examining requirements  Clarifying what "fast
                          to understand and       search" means
                          improve them            

  Requirement refinement  Adding detail and       Defining which
                          removing uncertainty    application statuses
                          from a requirement      appear to a student

  Requirement             Breaking a broad        Splitting "manage
  decomposition           requirement into        applications" into
                          smaller parts           submit, review, approve
                                                  and reject

  Requirement quality     How well a requirement  A clear, testable
                          communicates a need     statement is higher
                                                  quality than "make it
                                                  user-friendly"

  Ambiguity               A statement that can be "The report should be
                          understood in more than generated quickly"
                          one way                 

  Incompleteness          Important information   A password reset
                          is missing              requirement does not
                                                  explain how identity is
                                                  verified

  Inconsistency           Two requirements        One says all users can
                          contradict one another  edit applications;
                                                  another says only staff
                                                  can

  Duplication             The same need is        Two entries describe
                          recorded more than once the same email
                                                  notification

  Feasibility             Whether a requirement   A requested integration
                          can realistically be    may not be possible
                          delivered within        with the available
                          constraints             system

  Testability             Whether it is possible  "Search results appear
                          to check objectively    within 2 seconds for
                          that a requirement is   95% of requests"
                          met                     

  Priority                Relative importance or  Payment security is
                          order of attention      prioritized over a
                                                  decorative theme

  Business value          The benefit a           Online submission
                          requirement provides to reduces manual data
                          the organization or its entry
                          customers               

  Dependency              A relationship in which Payment confirmation
                          one requirement or      depends on payment
                          activity relies on      gateway integration
                          another                 

  Trade-off               A choice involving      Deliver fewer features
                          competing benefits or   now to meet a fixed
                          limitations             launch date

  Release                 A planned delivery of a The first portal
                          set of solution         release supports
                          capabilities            application submission
                                                  and staff review
  -----------------------------------------------------------------------

**Important distinction:** Elicitation collects information. Analysis
examines and improves that information. Prioritization helps decide what
should be addressed first.

------------------------------------------------------------------------

# 3. Requirement analysis: the practical process

There is no single mandatory sequence for every organization, but the
following workflow is a useful way to analyze a set of requirements.

## Step 1 --- Understand the requirement in context

For every requirement, ask:

-   Who needs it?
-   What problem or need does it address?
-   Who will use or be affected by it?
-   What business outcome should it support?
-   Is it a business, stakeholder, functional or non-functional
    requirement?
-   Where did the information come from?

Example:

Original statement: "Students need application updates."

Context questions:

-   Which students: all applicants or only submitted applicants?
-   Which updates: received, under review, approved, rejected or more
    information required?
-   Where should updates appear: portal, email, SMS or more than one
    channel?
-   Who is responsible for changing the application status?

Do not assume the answer. Record what is known and ask the appropriate
stakeholder to clarify what is missing.

## Step 2 --- Check requirement quality

Use the quality checks below.

### 3.2.1 Clarity

A requirement should be understandable and should not rely on vague
words.

Weak: \> The portal should be easy to use.

Improved: \> An applicant should be able to locate the
application-status page from the main dashboard.

The improved statement is more specific. It may still need usability
criteria, such as the intended user group and how ease of use will be
evaluated.

### 3.2.2 Completeness

A requirement should contain enough information for the intended next
activity.

Weak: \> Staff can approve applications.

Questions that may be missing:

-   Which staff roles can approve?
-   What conditions must be satisfied?
-   Can an application be approved if documents are missing?
-   Is a reason required?
-   What happens after approval?
-   Is the applicant notified?

A requirement does not need every technical design detail at the
beginning. It needs enough information for its current level of
analysis, with unresolved questions recorded.

### 3.2.3 Consistency

Requirements should not contradict one another.

Example:

-   Requirement A: Applicants can edit their application until the
    deadline.
-   Requirement B: Applicants cannot edit an application after the first
    submission.

These statements may conflict. The BA should ask whether the second rule
applies only after the deadline, after staff review, or at another
point. The BA should not silently choose one interpretation.

### 3.2.4 Feasibility

A requirement must be assessed against relevant limits, such as:

-   Budget.
-   Delivery schedule.
-   Available technology.
-   Existing systems.
-   Skills and staffing.
-   Legal, policy or operational restrictions.
-   Security and privacy obligations.

Example:

A stakeholder requests real-time integration with an external government
system. Before accepting the requirement as feasible, the BA should
investigate whether the external system provides an accessible
interface, whether permission is available, and whether the timeline and
cost are acceptable.

A BA may identify feasibility concerns and coordinate technical
assessment. The BA should not claim technical impossibility without
suitable evidence.

### 3.2.5 Testability

A requirement should allow someone to determine whether it has been
satisfied.

Weak: \> The application page should load quickly.

More testable: \> Under the agreed normal operating conditions, the
application page should load within 3 seconds for at least 95% of
measured requests.

The example is measurable, but the team still needs to agree on the
measurement conditions, user load, test environment and measurement
method.

### 3.2.6 Relevance and value

Ask whether the requirement contributes to the business need or an
agreed obligation.

Example:

If the goal is to reduce manual admission processing, online document
submission may contribute directly. A decorative animation may have
little connection to that goal.

A requirement can still be necessary for compliance, accessibility,
security or another valid reason even if its immediate financial benefit
is not obvious.

### 3.2.7 Verifiability

Verifiability asks whether evidence can demonstrate that the requirement
is satisfied. Testability is closely related and often used in the same
discussion.

Example:

Requirement: "Only authorized admission officers can change an
application decision."

Possible verification: Test accounts with different roles are used to
confirm that authorized officers can change the decision and
unauthorized users cannot.

### Quality review table

  -----------------------------------------------------------------------
  Quality check           Question to ask         Warning sign
  ----------------------- ----------------------- -----------------------
  Clear                   Can different readers   Vague words or multiple
                          understand it in the    interpretations
                          same way?               

  Complete                Is enough information   Missing actor,
                          present for the next    condition or outcome
                          step?                   

  Consistent              Does it contradict      Two different rules for
                          another requirement or  the same situation
                          rule?                   

  Feasible                Can it be achieved      Unavailable integration
                          within known            or unrealistic deadline
                          constraints?            

  Testable                Can an objective        "Good", "simple",
                          pass/fail or measurable "fast" without criteria
                          check be defined?       

  Relevant                Does it support a need, Feature has no
                          objective or            identified reason
                          obligation?             

  Verifiable              Can evidence confirm    No observable result or
                          that it has been met?   evidence
  -----------------------------------------------------------------------

A useful memory aid is **C-C-C-F-T-R-V**: Clear, Complete, Consistent,
Feasible, Testable, Relevant and Verifiable. Organizations may use
different quality checklists; this is a practical review aid, not a
universal mandatory acronym.

------------------------------------------------------------------------

# 4. Find and resolve requirement problems

## 4.1 Ambiguous requirements

An ambiguous requirement has more than one possible interpretation.

Example:

> The system should notify users immediately.

Questions:

-   What event triggers the notification?
-   Who receives it?
-   What does "immediately" mean?
-   Which channel is used?
-   What happens if the channel is unavailable?

A clearer version might be:

> When an application status changes, the system should send an email
> notification to the applicant's registered email address within 2
> minutes.

This is more specific. The business must still confirm that email is the
required channel and that the two-minute target is appropriate.

## 4.2 Conflicting requirements

Conflicts can occur between:

-   Two stakeholders.
-   Two departments.
-   A stakeholder request and a business rule.
-   A functional requirement and a security requirement.
-   A new request and an existing system limitation.

Example:

-   Admissions team: applicants may edit submitted applications at any
    time.
-   Compliance team: submitted applications must not be changed after
    the deadline.

How should a BA respond?

1.  Record both statements and their sources.
2.  Understand the business reason behind each.
3.  Identify when and under what conditions the rules apply.
4.  Identify the impact of each possible interpretation.
5.  Facilitate a discussion with the relevant stakeholders.
6.  Escalate to the authorized decision-maker if needed.
7.  Record the agreed decision and update affected requirements.

Do not erase one stakeholder's view merely because another stakeholder
has more influence.

## 4.3 Duplicate requirements

Duplicates make a requirement set harder to manage and can lead to
inconsistent updates.

Example:

-   R-014: Send an email after successful application submission.
-   R-027: Email the applicant when the application is submitted
    successfully.

These may describe the same behavior. Check whether the trigger,
recipient, content and conditions are actually identical before merging
them.

Keep traceability to the original source where needed.

## 4.4 Missing requirements and gaps

A gap is an area of necessary information or behavior that has not been
addressed.

For an online application process, possible gaps include:

-   What happens when a required document is missing?
-   Can an applicant save a draft?
-   Can an application be submitted twice?
-   What happens after the deadline?
-   Can staff return an application for correction?
-   How are rejected applications communicated?
-   What happens if a notification fails?

A useful method is to walk through the business process from beginning
to end and examine normal, alternate and exception situations.

## 4.5 Dependencies

Some requirements rely on others.

Example:

``` text
Applicant creates an account
          |
          v
Applicant verifies email
          |
          v
Applicant completes application
          |
          v
Applicant submits application
          |
          v
System records submission
          |
          v
System sends confirmation
```

The confirmation depends on a successful submission event and a valid
destination address.

Record dependencies so the team understands sequencing and the impact of
a change. A dependency is not automatically a risk; a risk is an
uncertain event that may affect an objective.

## 4.6 Requirement decomposition

A broad requirement may contain several behaviors. Break it into smaller
pieces that can be discussed, estimated, implemented and tested more
easily.

Broad requirement: \> The system should manage student applications.

Possible decomposition:

1.  Applicants can create an application.
2.  Applicants can save an incomplete application as a draft.
3.  Applicants can upload required documents.
4.  Applicants can submit an application before the deadline.
5.  Staff can view submitted applications.
6.  Authorized staff can request missing information.
7.  Authorized staff can approve or reject an application.
8.  Applicants can view the latest application status.

Check that the smaller requirements collectively represent the original
need. Do not split a requirement so aggressively that its business
meaning is lost.

------------------------------------------------------------------------

# 5. From raw request to a well-analyzed requirement

Consider this stakeholder statement:

> "We need a better way for students to know what is happening with
> their applications."

### 5.1 Understand the need

The likely need is visibility into application progress. Confirm this
with the stakeholder rather than treating the interpretation as a fact.

### 5.2 Ask clarification questions

-   Which application statuses should be visible?
-   Who can view the status?
-   Does the status need to update automatically?
-   Should students receive notifications?
-   How frequently should the information refresh?
-   Should staff see the same information as applicants?
-   Are there privacy restrictions on what can be displayed?

### 5.3 Draft a clearer requirement

> An applicant should be able to view the current status of their own
> submitted application after signing in.

### 5.4 Add agreed business rules

For example, the organization may confirm these statuses:

-   Submitted.
-   Under review.
-   More information required.
-   Approved.
-   Rejected.

These statuses are illustrative. The actual organization must confirm
its process and terminology.

### 5.5 Define acceptance or verification conditions

Examples:

-   A signed-in applicant can view the status of their own application.
-   An applicant cannot view another applicant's application.
-   The displayed status matches the latest status recorded by an
    authorized staff member.
-   If no application has been submitted, the page displays an agreed
    explanatory message.

These conditions make the requirement easier to review and validate.

------------------------------------------------------------------------

# 6. Why prioritization is necessary

A project may contain more requirements than the team can deliver at
once.

For example, an admission portal may need:

-   Secure login.
-   Online application submission.
-   Document upload.
-   Staff application review.
-   Payment.
-   Email notifications.
-   Reports.
-   A mobile-friendly interface.
-   Multiple language support.
-   A customized dashboard.

If all requirements are treated as equally urgent, the team may struggle
to decide what to build first.

Prioritization helps answer:

-   Which requirements are essential to the business outcome?
-   Which requirements are required by policy, law or contract?
-   Which requirements reduce major risks?
-   Which requirements are prerequisites for other work?
-   Which requirements provide high value for reasonable effort?
-   Which requirements can wait for a later release?

**Prioritization is not simply ranking features by popularity.** It is a
reasoned decision based on agreed criteria and stakeholder input.

## 6.1 Common prioritization factors

  -----------------------------------------------------------------------
  Factor                  Meaning                 Example
  ----------------------- ----------------------- -----------------------
  Business value          How much the            Online submission
                          requirement contributes reduces manual
                          to business outcomes    processing

  User value              How much it helps the   Applicants can see
                          people using the        application status
                          solution                

  Urgency                 How soon it is needed   A feature required
                                                  before the admission
                                                  deadline

  Risk reduction          Whether it reduces      Access control protects
                          significant             application records
                          operational, security   
                          or delivery risk        

  Compliance              Whether it satisfies a  Required data-retention
                          legal, regulatory,      rule
                          policy or contractual   
                          obligation              

  Dependency              Whether other           Account verification
                          requirements rely on it before application
                                                  submission

  Cost or effort          Resources and time      A complex integration
                          needed                  may require substantial
                                                  work

  Frequency of use        How often users need    Staff review
                          the capability          applications every
                                                  working day

  Strategic alignment     How strongly it         Faster admissions
                          supports organizational processing supports a
                          goals                   digital-service
                                                  strategy
  -----------------------------------------------------------------------

Do not treat these factors as automatically equal. The project should
agree which criteria matter most.

## 6.2 Value versus effort

A simple comparison is to consider expected value alongside estimated
effort.

  -----------------------------------------------------------------------
  Requirement       Expected value    Estimated effort  Initial
                                                        observation
  ----------------- ----------------- ----------------- -----------------
  View application  High              Low               Strong candidate
  status                                                for early
                                                        delivery

  Custom dashboard  Low               Medium            May be deferred
  animation                                             

  Secure role-based High              Medium            Important
  access                                                risk-control
                                                        capability

  Complex external  High              High              Needs feasibility
  integration                                           and dependency
                                                        analysis
  -----------------------------------------------------------------------

This table supports discussion; it does not by itself determine the
final priority. A requirement with high effort may still be essential,
especially for compliance, security or the core business process.

## 6.3 Priority is not the same as effort

-   **Priority** describes the importance or order of attention.
-   **Effort** estimates the work needed.
-   **Complexity** describes how difficult or uncertain the work may be.
-   **Risk** describes uncertainty that may affect objectives.

A high-priority requirement can be difficult. A low-effort requirement
is not automatically high priority.

------------------------------------------------------------------------

# 7. MoSCoW prioritization technique

MoSCoW is a prioritization technique that groups requirements into four
categories:

-   **M --- Must have**
-   **S --- Should have**
-   **C --- Could have**
-   **W --- Won't have this time**

The final category is often described as "Won't have this time" to make
clear that the requirement is not necessarily rejected forever. It is
outside the agreed scope for the current time period or release.

## 7.1 Must have

A Must-have requirement is essential for the agreed release or outcome.
Without it, the solution may be unusable for its intended purpose, fail
a critical obligation, or fail to meet a fundamental business need.

Examples for an admission portal:

-   Applicants must be able to submit an application.
-   Authorized staff must be able to access submitted applications for
    review.
-   The system must protect application information from unauthorized
    access.

**Test:** If this requirement is not delivered in the release, can the
release still achieve its essential purpose and meet its mandatory
obligations? If not, it may be a Must-have.

Be careful: calling every stakeholder's favorite feature a Must-have
makes prioritization meaningless.

## 7.2 Should have

A Should-have requirement is important and provides meaningful value,
but the release may still be viable without it. There may be a
reasonable workaround, or it may be possible to deliver it shortly
afterwards.

Examples:

-   Applicants should receive an email confirmation after submission.
-   Staff should be able to filter applications by status.

A Should-have should not be treated as unimportant. It may become
essential if new evidence, policy or business circumstances change.

## 7.3 Could have

A Could-have requirement is desirable but has a lower impact if omitted
from the current release.

Examples:

-   Applicants could choose from additional dashboard themes.
-   The portal could provide optional visual progress indicators if the
    core status information is already available.

Could-haves are often considered when time and resources remain after
higher-priority requirements are addressed.

## 7.4 Won't have this time

A Won't-have-this-time requirement is explicitly excluded from the
current release or agreed time period.

Examples:

-   A native mobile application may be postponed if the current release
    is a responsive web portal.
-   Advanced predictive admission analytics may be excluded from the
    first release.

Record the reason and the relevant release or time boundary. "Won't have
this time" does not mean "never."

## 7.5 MoSCoW comparison table

  -----------------------------------------------------------------------
  Category          Meaning           Consequence if    Example
                                      omitted from      
                                      current release   
  ----------------- ----------------- ----------------- -----------------
  Must              Essential         Core outcome or   Submit an
                                      mandatory         application
                                      obligation may    
                                      fail              

  Should            Important         Release can work, Email
                                      but value or      confirmation
                                      quality is        
                                      reduced           

  Could             Desirable         Limited impact on Optional
                                      the essential     dashboard theme
                                      outcome           

  Won't this time   Agreed exclusion  Not delivered in  Native mobile app
                    for now           this release      deferred
  -----------------------------------------------------------------------

## 7.6 Worked MoSCoW example

Scenario: A college is launching an online admission portal for the next
admission cycle.

  -----------------------------------------------------------------------
  ID                Requirement       Category          Reason
  ----------------- ----------------- ----------------- -----------------
  R-01              Applicants can    Must              Needed to
                    create an account                   identify
                    and sign in                         applicants and
                    securely                            protect records

  R-02              Applicants can    Must              Core purpose of
                    complete and                        the portal
                    submit an                           
                    application                         

  R-03              Authorized staff  Must              Required for the
                    can review                          admission process
                    submitted                           
                    applications                        

  R-04              Applicants can    Should            Important
                    view their                          transparency and
                    application                         support benefit
                    status                              

  R-05              Applicants        Should            Helpful
                    receive an email                    communication; an
                    confirmation                        agreed portal
                    after submission                    confirmation may
                                                        provide a
                                                        temporary
                                                        alternative

  R-06              Staff can filter  Should            Improves staff
                    applications by                     efficiency
                    status                              

  R-07              Applicants can    Could             Optional
                    select dashboard                    personalization
                    themes                              

  R-08              A native mobile   Won't this time   Current release
                    application is                      is limited to the
                    delivered in the                    responsive web
                    same release                        portal
  -----------------------------------------------------------------------

**Important:** These classifications are scenario-specific examples, not
universal rules. If email confirmation is legally or operationally
mandatory, it may need to be Must-have. If status visibility is
essential to the service commitment, it may also become Must-have.
Priorities depend on agreed outcomes and constraints.

------------------------------------------------------------------------

# 8. How to apply MoSCoW correctly

Use this practical sequence.

### Step 1 --- Confirm the scope boundary

State what is being prioritized:

-   A whole project?
-   A particular release?
-   A sprint?
-   A defined delivery period?

MoSCoW categories are meaningful only when the time or scope boundary is
clear.

### Step 2 --- Confirm the objective

Understand what the release must achieve.

Example: \> Enable applicants to submit admission applications online
and allow admission staff to review them before the application
deadline.

### Step 3 --- Prepare a clear requirement list

Requirements should be sufficiently understood before assigning
categories. If a requirement is vague, clarify it first or mark it as
needing further analysis.

### Step 4 --- Agree the Must-have conditions

Ask stakeholders what would make the release fail if omitted. Consider
mandatory obligations, core business processes, safety, security and
critical dependencies.

### Step 5 --- Classify Should and Could requirements

Compare business value, user value, urgency, risk, effort and
dependencies. Discuss trade-offs openly.

### Step 6 --- Record Won't-have-this-time items

Record what is excluded, why it is excluded and whether it may be
reconsidered later.

### Step 7 --- Review dependencies and feasibility

A requirement should not be prioritized in isolation if another
requirement must be delivered first. Check whether the proposed release
can actually deliver the selected set.

### Step 8 --- Obtain stakeholder agreement

Discuss disagreements and document the decision, decision-maker,
rationale and date. The BA facilitates and records; the designated
authority approves where required.

### Step 9 --- Revisit priorities when circumstances change

Priorities can change if:

-   A regulation changes.
-   A deadline moves.
-   A dependency becomes unavailable.
-   A major risk is discovered.
-   New user research changes the expected value.
-   Budget or capacity changes.

Changes should be assessed and communicated rather than silently
changing the agreed list.

------------------------------------------------------------------------

# 9. MoSCoW rules and common mistakes

MoSCoW is useful, but it is not a substitute for analysis or
decision-making.

## 9.1 Agree what "Must" means

If stakeholders label 90% of requirements as Must-have, the method is
not helping the team make trade-offs.

A Must-have should have a clear reason tied to the release objective, a
mandatory obligation or an essential capability.

## 9.2 Do not confuse stakeholder seniority with business value

A senior stakeholder's request deserves consideration, but priority
should be based on agreed criteria and decision authority---not title
alone.

## 9.3 Do not ignore dependencies

A feature may appear low priority by itself but be a prerequisite for a
high-priority capability.

Example: Email verification may appear less visible than application
submission, but if secure account verification is required before
submission, it must be considered in the delivery sequence.

## 9.4 Do not use MoSCoW as a precise numerical score

MoSCoW provides categories, not a mathematical ranking. It does not
automatically tell you whether one Should-have is more important than
another.

If the team needs finer ranking within a category, use agreed criteria
or another prioritization method as a supporting technique.

## 9.5 Do not treat Won't-have as a permanent rejection

Always state the time boundary: "Won't have in Release 1" is clearer
than "Won't have."

## 9.6 Do not prioritize unclear requirements

A requirement such as "make the system intelligent" cannot be
meaningfully prioritized until its intended behavior and value are
understood.

## 9.7 Do not let the BA make unauthorized business decisions

The BA analyzes, facilitates, explains trade-offs and documents
decisions. Final priority authority depends on the organization's
governance, product ownership and project roles.

------------------------------------------------------------------------

# 10. Other prioritization techniques you may encounter

MoSCoW is the focus of this lesson. In practice, teams may use
additional techniques.

  ---------------------------------------------------------------------------
  Technique         How it works      When it may help      Limitation
  ----------------- ----------------- --------------------- -----------------
  Simple ranking    Put requirements  Small lists where     Can become
                    in order from     stakeholders can      difficult with
                    highest to lowest agree on an order     many requirements
                    priority                                

  Value versus      Compare expected  Early release         Estimates may be
  effort            benefit with      planning and          uncertain
                    estimated work    trade-off discussions 

  Weighted scoring  Score             When several criteria Results depend on
                    requirements      must be compared      chosen criteria
                    against agreed    systematically        and weights
                    criteria and                            
                    weights                                 

  Pairwise          Compare two       When stakeholders     Can take time as
  comparison        requirements at a struggle to rank a    the list grows
                    time to decide    larger list           
                    which is more                           
                    important                               

  Kano model        Groups features   Product and           Requires suitable
                    by how they       customer-experience   customer insight
                    affect customer   decisions             and
                    satisfaction                            interpretation
  ---------------------------------------------------------------------------

These methods do not replace stakeholder agreement, feasibility checks
or mandatory obligations.

## 10.1 Weighted scoring --- simple illustration

Suppose a team agrees to evaluate requirements using three criteria:

-   Business value: 50% weight.
-   Urgency: 30% weight.
-   Risk reduction: 20% weight.

Each requirement receives a score from 1 to 5 for each criterion.

Illustrative formula:

`Total score = (Business value × 0.50) + (Urgency × 0.30) + (Risk reduction × 0.20)`

Example:

  -------------------------------------------------------------------------------
  Requirement       Business      Urgency         Risk Calculation          Total
                value (1--5)       (1--5)    reduction               
                                                (1--5)               
  ------------- ------------ ------------ ------------ ------------- ------------
  Secure access            5            5            5 5×0.50 +               5.0
                                                       5×0.30 +      
                                                       5×0.20        

  Status page              4            3            2 4×0.50 +               3.3
                                                       3×0.30 +      
                                                       2×0.20        

  Dashboard                1            1            1 1×0.50 +               1.0
  theme                                                1×0.30 +      
                                                       1×0.20        
  -------------------------------------------------------------------------------

The scores are illustrative, not objective facts. Stakeholders must
agree on the criteria, weights and scoring scale. A high score does not
override a mandatory requirement or a critical dependency.

------------------------------------------------------------------------

# 11. Recording analysis and prioritization decisions

A requirement list becomes more useful when each entry has enough
information to understand and manage it.

A practical requirement record may contain:

  -----------------------------------------------------------------------
  Field                   Purpose                 Example
  ----------------------- ----------------------- -----------------------
  Requirement ID          Unique reference        REQ-001

  Requirement statement   What is needed          Applicant can view
                                                  their own application
                                                  status

  Type                    Requirement             Functional
                          classification          

  Source                  Where it came from      Applicant interview

  Rationale               Why it is needed        Reduce status enquiries

  Priority                Agreed importance       Should

  Business value          Expected benefit        Better applicant
                                                  visibility

  Dependencies            Related requirements    Applicant sign-in

  Assumptions / open      What is not yet         Status refresh timing
  questions               confirmed               to be agreed

  Acceptance /            How it may be checked   Applicant sees own
  verification notes                              status after sign-in

  Status                  Current lifecycle state Under review

  Decision owner          Who confirms the        Admissions product
                          decision                owner
  -----------------------------------------------------------------------

The fields used vary by organization and project. Do not add fields
simply to make a document look complicated; capture information that
supports decisions and delivery.

## 11.1 Keep a decision log

When stakeholders agree on a priority or resolve a conflict, record:

-   Decision ID.
-   Date.
-   Decision.
-   Reason or evidence.
-   Options considered.
-   People or roles involved.
-   Person authorized to approve.
-   Requirements affected.
-   Follow-up actions.

Example:

  -----------------------------------------------------------------------
  Decision                            Recorded outcome
  ----------------------------------- -----------------------------------
  D-01                                Email confirmation classified as
                                      Should-have for Release 1

  Reason                              Applicants will receive an
                                      on-screen confirmation; email is
                                      valuable but not a release-blocking
                                      obligation in this scenario

  Approved by                         Authorized product owner

  Impact                              R-05 remains in the backlog for a
                                      later release
  -----------------------------------------------------------------------

A decision log helps prevent the same discussion from being repeated and
makes the reasoning visible.

------------------------------------------------------------------------

# 12. Industry scenario --- admission portal prioritization

A college plans to replace a paper-based admission process with an
online portal. Stakeholders include applicants, admission officers, the
admissions manager, IT/security staff and finance.

The initial request list is:

1.  Applicants can register and sign in.
2.  Applicants can complete and submit applications.
3.  Applicants can upload required documents.
4.  Staff can review applications.
5.  Staff can approve or reject applications.
6.  Applicants can view application status.
7.  Applicants receive email notifications.
8.  Staff can export reports.
9.  Applicants can personalize dashboard colors.
10. A native mobile application is launched with the first release.

### Analysis before prioritization

The BA should not immediately assign MoSCoW categories. First clarify:

-   Which documents are required?
-   What is the application deadline?
-   Which staff roles can make decisions?
-   Are approval and rejection rules documented?
-   Is status visibility required by policy or service expectations?
-   Is email notification mandatory, or is an on-screen confirmation
    sufficient for the first release?
-   What report formats and fields are needed?
-   Does the organization require a native app, or will a responsive
    website meet the need?
-   What security and privacy requirements apply?

### Example outcome

After clarification and stakeholder agreement, the team may classify
core registration, application submission, document handling and
authorized staff review as Must-have. Status visibility and email
notifications may be Should-have or Must-have depending on the confirmed
service requirements. Personalization may be Could-have. The native
mobile application may be Won't-have-this-time if the first release is
explicitly a responsive web portal.

### What the BA contributes

-   Clarifies statements and records open questions.
-   Identifies missing, conflicting and duplicate requirements.
-   Checks alignment with business objectives.
-   Makes dependencies visible.
-   Facilitates prioritization discussions.
-   Explains trade-offs and impacts.
-   Records agreed categories and rationale.
-   Confirms that the authorized stakeholders approve the decisions.

------------------------------------------------------------------------

# 13. Common mistakes and how to correct them

  -----------------------------------------------------------------------
  Mistake                 Why it causes trouble   Better approach
  ----------------------- ----------------------- -----------------------
  Accepting raw requests  Important details       Ask questions and
  as final requirements   remain unclear          refine the statements

  Prioritizing before     The team may rank the   Confirm the business
  understanding the need  wrong thing             objective first

  Marking everything      No meaningful trade-off Define strict Must-have
  Must-have               remains                 criteria

  Treating low effort as  Easy work may not       Compare value, urgency,
  high priority           deliver meaningful      risk and effort
                          value                   

  Ignoring dependencies   A planned feature may   Record prerequisites
                          be blocked              and sequencing

  Treating assumptions as Decisions may rely on   Label assumptions and
  confirmed facts         incorrect information   validate them

  Ignoring conflicting    The delivered solution  Record, investigate and
  stakeholder views       may not satisfy the     resolve conflicts
                          process                 

  Failing to record the   Decisions become        Maintain rationale and
  reason for priority     difficult to explain    decision records
                          later                   

  Treating Won't-have as  Future planning becomes State the release or
  never                   confusing               time boundary

  Changing priorities     Scope and expectations  Use agreed review and
  informally              become unstable         change processes
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 14. Quick revision sheet

  -----------------------------------------------------------------------
  Topic                               Remember
  ----------------------------------- -----------------------------------
  Requirement analysis                Examine, clarify and improve
                                      collected requirements

  Refinement                          Add useful detail and remove
                                      uncertainty

  Decomposition                       Break broad requirements into
                                      smaller requirements

  Ambiguity                           More than one possible
                                      interpretation

  Incompleteness                      Necessary information is missing

  Inconsistency                       Requirements or rules contradict
                                      one another

  Duplication                         Same need is recorded more than
                                      once

  Feasibility                         Can it be delivered within known
                                      constraints?

  Testability                         Can an objective check be defined?

  Prioritization                      Decide relative importance using
                                      agreed criteria

  Business value                      Contribution to business outcomes

  Dependency                          One requirement or activity relies
                                      on another

  MoSCoW Must                         Essential for the agreed release

  MoSCoW Should                       Important, but release may remain
                                      viable without it

  MoSCoW Could                        Desirable, lower impact if omitted

  MoSCoW Won't this time              Explicitly excluded from the
                                      current release/time period

  Decision log                        Record decisions, reasons, owners
                                      and impacts
  -----------------------------------------------------------------------

**Remember this sequence:**

``` text
COLLECT
   |
   v
UNDERSTAND
   |
   v
CLARIFY
   |
   v
CHECK QUALITY
   |
   v
FIND GAPS / CONFLICTS / DEPENDENCIES
   |
   v
PRIORITIZE
   |
   v
AGREE AND RECORD
   |
   v
REVIEW WHEN CONDITIONS CHANGE
```

------------------------------------------------------------------------

# 15. Interview preparation --- questions and answers

## Q1. What is requirement analysis?

**Answer:**

Requirement analysis is the process of examining collected requirements
to understand their meaning, identify missing information, resolve
ambiguity and conflict, assess feasibility and ensure that requirements
are sufficiently clear and useful for solution development and
validation.

**Example:** If a stakeholder says "the system should be fast," the BA
clarifies the expected response time, conditions and measurement method.

**Follow-up:** What can happen if requirements are not analyzed
properly?

**Answer:** Teams may build the wrong functionality, make incorrect
assumptions, underestimate effort, miss important scenarios or deliver a
solution that does not meet business needs.

## Q2. What is the difference between requirement elicitation and requirement analysis?

**Answer:**

Elicitation is about discovering and collecting information from
stakeholders and other sources. Analysis is about examining that
information, clarifying it, identifying gaps and conflicts, and making
it sufficiently precise for further work.

**Example:** Asking staff how they review applications is elicitation.
Identifying missing approval rules and clarifying the review conditions
is analysis.

**Follow-up:** Can elicitation and analysis happen at the same time?

**Answer:** Yes. They are often iterative. Analysis may reveal questions
that require another interview or workshop.

## Q3. How do you identify an ambiguous requirement?

**Answer:**

Look for vague words, undefined terms, missing conditions or statements
that can be interpreted in multiple ways. Ask stakeholders for examples,
boundaries, measurable expectations and exception cases.

**Example:** "Notify users quickly" should be clarified by identifying
the recipient, trigger, channel and expected time.

**Follow-up:** Should the BA guess when a stakeholder is unavailable?

**Answer:** No. Record the open question and any temporary assumption
clearly. Validate it with the appropriate stakeholder before treating it
as an agreed requirement.

## Q4. What makes a requirement good?

**Answer:**

A good requirement is clear, sufficiently complete, consistent,
feasible, relevant and testable or verifiable. It should communicate a
real need and avoid unnecessary ambiguity.

**Example:** "An applicant can view the current status of their own
submitted application after signing in" is clearer and more testable
than "provide a good application experience."

**Follow-up:** Does every requirement need technical design details?

**Answer:** No. The required level of detail depends on the stage and
purpose. Avoid adding design decisions before they are needed or agreed.

## Q5. What is requirement prioritization?

**Answer:**

Requirement prioritization is the process of determining the relative
importance or order of requirements using factors such as business
value, urgency, risk, compliance, dependencies and effort.

**Example:** Secure access and application submission may take priority
over optional dashboard personalization.

**Follow-up:** Who decides the final priority?

**Answer:** The BA supports the decision, but final authority depends on
the organization's roles and governance---for example, a product owner,
sponsor or authorized business decision-maker.

## Q6. Explain the MoSCoW technique.

**Answer:**

MoSCoW is a prioritization method that classifies requirements as
Must-have, Should-have, Could-have or Won't-have this time. It helps
stakeholders agree what is essential for a defined release or time
period and what can be deferred.

**Follow-up:** Does Won't-have mean the requirement is permanently
rejected?

**Answer:** No. It means it is excluded from the current agreed release
or period. It may be reconsidered later.

## Q7. How do you prevent every stakeholder from marking their requirement as Must-have?

**Answer:**

Agree on the definition of Must-have before classification. Ask what
would happen if the requirement were omitted from the release, connect
it to the agreed business objective or mandatory obligation, and discuss
alternatives and workarounds. Record the rationale and use the
authorized decision process.

**Follow-up:** What if stakeholders still disagree?

**Answer:** Document the competing needs and impacts, facilitate a
discussion and escalate the decision to the appropriate authority if
necessary.

## Q8. What is the difference between priority and effort?

**Answer:**

Priority describes the importance or order of attention. Effort
estimates the work required. A requirement can be high priority and high
effort, or low priority and low effort.

**Example:** Secure integration may require substantial effort but still
be essential.

**Follow-up:** Should the team always select high-value, low-effort
requirements first?

**Answer:** They are often attractive candidates, but mandatory
requirements, dependencies, risk and release objectives must also be
considered.

## Q9. How do you handle conflicting requirements?

**Answer:**

I would record both requirements and their sources, understand the
business reasons, identify the conditions under which each applies,
assess the impacts, facilitate discussion and obtain a decision from the
authorized stakeholder. I would then update the requirements and
decision records.

**Follow-up:** Should the BA remove one requirement without discussion?

**Answer:** No. The BA should not silently discard a stakeholder's need
or make an unauthorized business decision.

## Q10. What is a requirement dependency?

**Answer:**

A dependency exists when one requirement or activity relies on another.
For example, an applicant may need a verified account before submitting
an application.

**Follow-up:** Why does dependency analysis matter during
prioritization?

**Answer:** A high-priority requirement may not be deliverable until its
prerequisite is completed. The team must account for the correct
sequence and delivery impact.

## Q11. What information should be recorded with a priority decision?

**Answer:**

Record the requirement, assigned priority, rationale, relevant business
objective, dependencies, decision owner, date and any affected
requirements or release scope. A decision log can preserve the
discussion and approval.

**Follow-up:** Why is rationale important?

**Answer:** It makes decisions explainable, supports future reviews and
reduces repeated disagreement.

## Q12. Can a requirement's priority change?

**Answer:**

Yes. Priorities may change when business objectives, regulations,
deadlines, risks, dependencies, budget or stakeholder evidence changes.
The impact should be assessed and the change should follow the agreed
governance process.

**Follow-up:** Should a developer change the priority independently?

**Answer:** Not unless the developer has been given that authority. The
relevant product or business decision-maker should approve priority
changes.

## Q13. What is the difference between MoSCoW and weighted scoring?

**Answer:**

MoSCoW places requirements into four categories. Weighted scoring
assigns scores against agreed criteria and weights to support a more
detailed comparison. They can be used together, but neither removes the
need for stakeholder judgment.

**Follow-up:** Can a weighted score override a legal requirement?

**Answer:** No. Mandatory obligations and critical constraints must be
respected regardless of a simple numerical score.

## Q14. What would you do if a requirement is too vague to prioritize?

**Answer:**

I would identify the missing information, ask clarification questions,
document open points and obtain enough detail to understand the need and
its value. I would avoid assigning a confident priority based on an
unclear statement.

**Follow-up:** Can it remain in the requirement list?

**Answer:** Yes, it can be recorded with an appropriate status such as
"Needs clarification," rather than being treated as an agreed, ready
requirement.

## Q15. What is the BA's role in requirement prioritization?

**Answer:**

The BA organizes and clarifies requirements, connects them to business
objectives, identifies dependencies and impacts, facilitates
prioritization discussions, explains trade-offs and documents decisions.
The BA supports the decision rather than automatically owning final
priority authority.

**Follow-up:** What makes prioritization successful?

**Answer:** Clear objectives, agreed criteria, realistic constraints,
stakeholder participation, visible rationale and timely review.

------------------------------------------------------------------------

# 16. Daily quiz

Try each question before checking the answer key.

### Question 1

A stakeholder says, "The portal must be user-friendly." What should the
BA do first?

A. Mark it Must-have immediately.\
B. Ask what user tasks and measurable usability expectations are
intended.\
C. Ask developers to choose the design.\
D. Remove the requirement.

### Question 2

Two requirements state that applicants can edit an application after
submission and that submitted applications cannot be edited. What issue
should the BA investigate?

A. Duplication only.\
B. Inconsistency or conflicting business rules.\
C. Low business value.\
D. A completed dependency.

### Question 3

Which statement best describes a MoSCoW Should-have?

A. It is never useful.\
B. It is essential or the release cannot work.\
C. It is important, but the release may remain viable without it.\
D. It is permanently rejected.

### Question 4

A requirement has high business value but also high effort. What is the
correct interpretation?

A. It must be low priority.\
B. Priority and effort are different considerations; assess the business
need, constraints and trade-offs.\
C. It must be a Could-have.\
D. It should be deleted.

### Question 5

What does "Won't have this time" mean in MoSCoW?

A. The requirement can never be delivered.\
B. The requirement is excluded from the current agreed release or time
period.\
C. The requirement has already been completed.\
D. The requirement has no stakeholder.

## Answer key with explanations

1.  **B** --- "User-friendly" is vague. The BA should clarify intended
    users, tasks and how usability expectations will be evaluated.
2.  **B** --- The statements may conflict. The BA should investigate the
    conditions and obtain an agreed rule.
3.  **C** --- A Should-have is important, but the release can remain
    viable without it.
4.  **B** --- High value does not automatically mean low effort or low
    priority. Consider dependencies, constraints and trade-offs.
5.  **B** --- It is a current-scope decision, not necessarily a
    permanent rejection.

------------------------------------------------------------------------

# 17. Knowledge check --- explain in your own words

1.  What is the difference between requirement analysis and requirement
    prioritization?
2.  Give one example each of an ambiguous, incomplete and inconsistent
    requirement.
3.  Why should a BA check feasibility before a requirement is treated as
    agreed?
4.  What is the difference between priority and effort?
5.  Explain all four MoSCoW categories using an online admission portal.
6.  Why is a release boundary important when using MoSCoW?
7.  What should a BA do when two stakeholders disagree about a
    requirement?
8.  Why should the rationale for a priority decision be recorded?
9.  How can dependencies affect the order in which requirements are
    delivered?
10. Name two situations that could cause a requirement's priority to
    change.

## Suggested answers

1.  Analysis clarifies and evaluates requirements; prioritization
    determines their relative importance.
2.  Ambiguous: "respond quickly." Incomplete: "staff can approve"
    without defining who or under what conditions. Inconsistent: one
    rule allows editing after submission while another prohibits it.
3.  To identify whether it can be delivered within technical, financial,
    schedule, operational and other constraints.
4.  Priority is importance; effort is the work required.
5.  Must: application submission; Should: status email; Could: optional
    theme; Won't this time: native mobile app in the first release.
    These are illustrative classifications and depend on the agreed
    scenario.
6.  Because "this time" must refer to a defined release or period.
7.  Record both views, understand the reasons and impacts, facilitate
    discussion and obtain an authorized decision.
8.  It makes decisions transparent and easier to review.
9.  A requirement may depend on another requirement being completed
    first.
10. A new regulation, changed deadline, new risk, altered dependency,
    budget change or new stakeholder evidence.

------------------------------------------------------------------------

# 18. Day 9 completion checklist

Use this checklist to assess whether you understand the lesson.

-   [ ] I can explain requirement analysis in plain English.
-   [ ] I can distinguish elicitation, analysis and prioritization.
-   [ ] I can identify ambiguity, incompleteness, inconsistency and
    duplication.
-   [ ] I can check requirements for clarity, completeness, consistency,
    feasibility and testability.
-   [ ] I can break a broad requirement into smaller requirements.
-   [ ] I can explain business value, urgency, risk, effort and
    dependency.
-   [ ] I can define all four MoSCoW categories.
-   [ ] I can apply MoSCoW to a realistic release scenario.
-   [ ] I understand that MoSCoW priorities depend on the agreed scope
    and business context.
-   [ ] I can explain why a BA facilitates and documents decisions
    rather than assuming final authority.
-   [ ] I have answered the quiz and reviewed any incorrect answers.
-   [ ] I can answer at least two interview questions without reading
    the answers.

------------------------------------------------------------------------

**Next syllabus topic --- Day 10: User stories, acceptance criteria and
INVEST principles.**
