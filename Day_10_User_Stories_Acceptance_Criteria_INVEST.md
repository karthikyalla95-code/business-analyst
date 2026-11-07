# Day 10 --- User Stories, Acceptance Criteria and INVEST Principles

**Phase:** 2 --- Requirements Engineering\
**Approved syllabus topic:** User stories, acceptance criteria and
INVEST principles\
**Approved independent mini-project title:** User Story Writing Lab\
**Estimated study time:** 2--3 hours\
**Difficulty:** Intermediate\
**Prerequisites:** Day 6 --- Requirement types; Day 7 --- Requirement
elicitation; Day 8 --- Workshops and other elicitation techniques; Day 9
--- Requirement analysis, prioritization and MoSCoW.

------------------------------------------------------------------------

## Learning objectives

By the end of this lesson, you should be able to:

1.  Explain what a user story is and when teams use it.
2.  Write user stories using the standard role--goal--benefit format.
3.  Distinguish a user story from a requirement, task and use case.
4.  Write clear acceptance criteria that describe observable outcomes.
5.  Recognize common acceptance-criteria formats, including
    scenario-based Given--When--Then.
6.  Apply the INVEST principles to review and improve user stories.
7.  Identify vague, oversized, solution-prescriptive or untestable
    stories and refine them.
8.  Explain how stories, acceptance criteria, prioritization and
    validation fit together.

------------------------------------------------------------------------

# 1. Why user stories matter

Imagine a college is building an online admission portal. A stakeholder
says:

> "We need an application-status feature."

That sentence names a feature, but it does not clearly explain who needs
it, what they need to do or why it matters.

A Business Analyst (BA) helps express the need from the perspective of
the person who will use the solution:

> As an applicant, I want to view the status of my submitted application
> so that I know what action, if any, I need to take next.

This is a **user story**.

It communicates: - **Who:** an applicant. - **What:** view the status of
a submitted application. - **Why:** understand progress and next steps.

A user story is a concise description of a capability from a user's
perspective. It is commonly used by Agile teams to discuss, prioritize,
refine and deliver work.

A user story is not a complete specification by itself. The team
discusses it, adds acceptance criteria, identifies questions and
dependencies, and agrees when it is sufficiently understood for
delivery.

``` text
User need
   |
   v
User story
   |
   v
Conversation and refinement
   |
   v
Acceptance criteria
   |
   v
Development and testing
   |
   v
Review against agreed outcomes
```

------------------------------------------------------------------------

# 2. Words you need

  -----------------------------------------------------------------------
  Term                    Plain-English meaning   Example
  ----------------------- ----------------------- -----------------------
  User story              A short description of  An applicant wants to
                          a need from a user's    view application status
                          perspective             

  User / actor            The person or role that Applicant, admission
                          interacts with the      officer
                          solution                

  Goal                    What the user wants to  View a submitted
                          do                      application's status

  Benefit                 Why the goal matters    Know whether further
                                                  action is needed

  Acceptance criteria     Conditions that must be Applicant can view only
                          satisfied for a story   their own application
                          to be accepted          status

  Scenario                A specific situation or Applicant signs in and
                          path through a process  opens the status page

  Given--When--Then       A structured way to     Given a signed-in
                          describe a scenario and applicant, when they
                          its expected result     open their application,
                                                  then its current status
                                                  is shown

  Backlog                 An ordered list of work List of portal stories
                          or items for a product  
                          or team                 

  Refinement              A collaborative         Clarify what status
                          activity to clarify,    values are displayed
                          split, estimate and     
                          prepare backlog items   

  Epic                    A large body of related Manage admission
                          work that is usually    applications
                          divided into smaller    
                          stories                 

  Story point             A team's relative       A team estimates one
                          estimate of work,       story as 3 points
                          complexity and          
                          uncertainty             

  INVEST                  A checklist for         Independent,
                          evaluating the quality  Negotiable, Valuable,
                          of user stories         Estimable, Small,
                                                  Testable

  Definition of Done      A team's shared quality Code reviewed, tests
  (DoD)                   standard for completed  passed and
                          work                    documentation updated
  -----------------------------------------------------------------------

**Important:** A user story describes a user need. Acceptance criteria
describe the conditions that must be met for that story to be accepted.
The Definition of Done is a broader team-wide completion standard and is
not a replacement for story-specific acceptance criteria.

------------------------------------------------------------------------

# 3. The standard user story format

A widely used format is:

> As a **\[type of user\]**, I want **\[a goal or capability\]**, so
> that **\[a benefit or reason\]**.

Each part has a purpose.

  -----------------------------------------------------------------------
  Part                    Question answered       Example
  ----------------------- ----------------------- -----------------------
  As a...                 Who needs the           As an applicant
                          capability?             

  I want...               What does the user want I want to view my
                          to do?                  submitted application's
                                                  status

  So that...              Why is it useful?       So that I know whether
                                                  I need to take further
                                                  action
  -----------------------------------------------------------------------

## 3.1 Example: application status

**User story**

> As an applicant, I want to view the status of my submitted application
> so that I can understand its progress.

Breakdown:

-   Role: Applicant.
-   Goal: View the status of a submitted application.
-   Benefit: Understand progress.

## 3.2 Example: staff application review

> As an admission officer, I want to view submitted applications so that
> I can review applicant information and make an admission decision.

-   Role: Admission officer.
-   Goal: View submitted applications.
-   Benefit: Review applications and make decisions.

## 3.3 Example: missing documents

> As an admission officer, I want to request missing documents from an
> applicant so that the application can be completed before a decision
> is made.

-   Role: Admission officer.
-   Goal: Request missing documents.
-   Benefit: Obtain the information needed for review.

## 3.4 Example: report access

> As an admissions manager, I want to view the number of applications by
> status so that I can monitor the admission workload.

-   Role: Admissions manager.
-   Goal: View application counts grouped by status.
-   Benefit: Monitor workload.

------------------------------------------------------------------------

# 4. How to write a good user story

Follow this sequence.

## Step 1 --- Identify the user

Ask who benefits directly from the capability.

Possible roles in an admission portal:

-   Applicant.
-   Admission officer.
-   Admissions manager.
-   Finance officer.
-   System administrator.

Avoid using "the system" as the user when a real person or external
actor can be identified. A system story may sometimes be appropriate for
technical or integration work, but the team should still identify the
business or operational reason.

## Step 2 --- Identify the user's goal

Ask what the user wants to accomplish, not which screen or button they
want.

Less useful: \> As an applicant, I want a blue button.

More useful: \> As an applicant, I want to submit my completed
application so that the admissions team can begin reviewing it.

The button is a possible design choice. The goal is the business
capability.

## Step 3 --- Identify the benefit

Ask why the capability matters.

Weak: \> As an applicant, I want to click Submit so that I can click
Submit.

Better: \> As an applicant, I want to submit my completed application so
that it can be considered for admission.

The benefit should explain the value rather than repeat the action.

## Step 4 --- Check scope

A story should describe a manageable capability. If it includes many
unrelated actions or roles, it may be too large.

Too broad: \> As an applicant, I want to manage my complete admission
journey so that everything is available online.

Possible smaller stories:

1.  Create an applicant account.
2.  Sign in to the portal.
3.  Complete an application form.
4.  Save an application as a draft.
5.  Upload required documents.
6.  Submit a completed application.
7.  View application status.

## Step 5 --- Discuss details and questions

A user story is a starting point for conversation. Ask:

-   What must be true before the user can do this?
-   What happens when the action succeeds?
-   What happens when it fails?
-   Are there permissions or business rules?
-   What data is required?
-   Are there limits or deadlines?
-   What happens in exceptional situations?

Record unanswered questions rather than inventing answers.

## Step 6 --- Add acceptance criteria

Define observable conditions that demonstrate the story has been
delivered correctly. See Sections 6 and 7.

------------------------------------------------------------------------

# 5. User stories versus requirements, tasks and use cases

These terms are related, but they are not interchangeable.

  -----------------------------------------------------------------------
  Item                    What it describes       Example
  ----------------------- ----------------------- -----------------------
  Business requirement    A business need or      Reduce manual admission
                          outcome                 processing

  User story              A user's goal and       As an applicant, I want
                          benefit                 to submit my
                                                  application online so
                                                  that it can be
                                                  processed

  Functional requirement  A specific behavior the The portal shall allow
                          solution must provide   an applicant to submit
                                                  a completed application

  Non-functional          A quality or constraint The application page
  requirement                                     shall meet an agreed
                                                  response-time target

  Acceptance criterion    A condition for         A submitted application
                          accepting a particular  receives a unique
                          story                   reference number

  Task                    A piece of work needed  Create the submission
                          to implement a story    API

  Use case                A more structured       Applicant submits an
                          description of          admission application
                          interactions between an 
                          actor and a system      
  -----------------------------------------------------------------------

### Example of how they relate

**Business requirement:** Reduce manual admission processing.

**User story:** \> As an applicant, I want to submit my application
online so that the admissions team can process it without receiving a
paper form.

**Functional requirement:** \> The portal shall allow an authenticated
applicant to submit an application when all mandatory fields and
required documents are present.

**Acceptance criterion:** \> Given an authenticated applicant with all
mandatory fields and required documents completed, when the applicant
submits the application, then the portal records the submission and
displays a unique application reference.

**Possible implementation tasks:** - Create submission validation. -
Save the submitted application. - Generate a reference number. - Display
the confirmation.

The tasks describe work the team may perform. They are not the user's
need itself.

------------------------------------------------------------------------

# 6. Acceptance criteria

**Acceptance criteria** are specific conditions that a user story must
satisfy to be accepted.

They help the team agree on what success looks like before
implementation is completed.

Good acceptance criteria are:

-   Clear and understandable.
-   Specific to the story.
-   Observable or measurable.
-   Testable.
-   Consistent with business rules.
-   Focused on outcomes rather than unnecessary implementation details.

## 6.1 Weak versus strong criteria

Story: \> As an applicant, I want to view my submitted application's
status so that I can understand its progress.

Weak criteria:

-   The page should look good.
-   It should be easy to use.
-   It should work properly.

These statements are vague. Different people may interpret them
differently.

Stronger criteria:

1.  A signed-in applicant can view the status of their own submitted
    application.
2.  The page displays the latest status recorded for that application.
3.  An applicant cannot view another applicant's application.
4.  If the applicant has not submitted an application, the portal
    displays an agreed message explaining that no submitted application
    is available.

These criteria describe behavior that can be checked.

## 6.2 Acceptance criteria are not design instructions

A criterion should normally state the outcome, not prescribe every
technical detail.

Overly prescriptive: \> The portal must use a blue button at the
top-right corner and call a Java method named `getStatus()`.

Outcome-focused: \> The applicant can access the current status of their
own submitted application after signing in.

A design detail may be required if the business has an approved design
standard or a specific accessibility need. Otherwise, leave
implementation choices to the appropriate design and engineering
discussions.

------------------------------------------------------------------------

# 7. Given--When--Then format

A common way to write scenario-based acceptance criteria is
**Given--When--Then**.

-   **Given** --- the starting context or precondition.
-   **When** --- the action or event.
-   **Then** --- the expected outcome.

Template:

``` text
Given [starting condition]
When [user action or event]
Then [expected result]
```

## 7.1 Example: successful application submission

**User story**

> As an applicant, I want to submit my completed application so that it
> can be considered for admission.

**Scenario**

``` text
Given I am signed in
And all mandatory application fields are complete
And all required documents are uploaded
When I select Submit Application
Then the application is recorded as submitted
And a unique application reference is displayed
```

Interpretation:

-   Given: the applicant is signed in and the required information is
    complete.
-   When: the applicant submits.
-   Then: the system records the submission and displays a reference.

## 7.2 Example: incomplete application

``` text
Given I am signed in
And one or more mandatory fields are incomplete
When I attempt to submit the application
Then the application is not submitted
And the portal identifies the fields that need attention
```

This describes an alternate or exception scenario.

## 7.3 Example: viewing another applicant's record

``` text
Given I am signed in as Applicant A
And the application belongs to Applicant B
When I attempt to access Applicant B's application
Then access is denied
And the application information is not displayed
```

This scenario describes an important access-control outcome. The exact
expected response and audit behavior should be confirmed with the
security and business stakeholders.

## 7.4 Example: no submitted application

``` text
Given I am signed in
And I have not submitted an application
When I open the application-status page
Then the portal displays an agreed message
And it does not display another applicant's information
```

## 7.5 A story can have multiple scenarios

A story may need several acceptance criteria or scenarios to cover:

-   Successful behavior.
-   Invalid input.
-   Missing information.
-   Permission restrictions.
-   Boundary conditions.
-   Error or exception situations.

Do not add every imaginable technical edge case to every story. Focus on
relevant behavior and agreed scope.

------------------------------------------------------------------------

# 8. Acceptance criteria versus Definition of Done

These concepts are related but different.

  -----------------------------------------------------------------------
  Acceptance criteria                 Definition of Done
  ----------------------------------- -----------------------------------
  Specific to a user story            Shared across the team's work

  Describe what this story must       Describes the team's minimum
  satisfy                             completion standard

  Can differ from story to story      Usually applies consistently to all
                                      applicable backlog items

  Example: applicant sees a unique    Example: code reviewed, automated
  reference after submission          tests passed and required
                                      documentation updated
  -----------------------------------------------------------------------

Example:

**Story acceptance criterion:** A successfully submitted application
displays a unique reference number.

**Possible Definition of Done:** The code is reviewed, relevant tests
pass, security checks are completed, and the feature is demonstrated in
the agreed environment.

The team defines its Definition of Done. Do not assume that one team's
checklist applies to every organization.

------------------------------------------------------------------------

# 9. INVEST principles

INVEST is a checklist for evaluating user-story quality.

  -----------------------------------------------------------------------
  Letter            Principle         Meaning           Example /
                                                        question
  ----------------- ----------------- ----------------- -----------------
  I                 Independent       The story should  Can it be planned
                                      be as independent without being
                                      as reasonably     tightly coupled
                                      possible from     to another story?
                                      other stories     

  N                 Negotiable        The story is a    Can the team
                                      basis for         discuss different
                                      discussion, not a ways to meet the
                                      fixed technical   need?
                                      contract          

  V                 Valuable          It should provide Who benefits and
                                      value to a user   why?
                                      or another        
                                      identified        
                                      stakeholder       

  E                 Estimable         The team should   Is the scope
                                      have enough       understood well
                                      information to    enough to
                                      estimate the work estimate?

  S                 Small             It should be      Does it contain
                                      small enough to   too many
                                      complete within   capabilities?
                                      the team's        
                                      delivery approach 

  T                 Testable          There should be a Can clear
                                      way to verify     acceptance
                                      that it is        criteria be
                                      satisfied         written?
  -----------------------------------------------------------------------

## 9.1 I --- Independent

Stories should be structured so that they can be planned and delivered
with as few unnecessary dependencies as possible.

Example:

-   Story A: Applicant can create an account.
-   Story B: Applicant can view submitted application status.

Story B depends on the existence of an account and a submitted
application. That dependency may be unavoidable. The aim is not to
eliminate every dependency, but to make dependencies visible and avoid
artificial coupling.

## 9.2 N --- Negotiable

A user story should leave room for conversation about the best solution.

Less negotiable: \> As an applicant, I want the portal to use a specific
database table and a particular API endpoint.

More negotiable: \> As an applicant, I want to save my application as a
draft so that I can continue later.

The second statement describes the need without unnecessarily
prescribing the implementation.

## 9.3 V --- Valuable

The story should deliver value to a user, customer, business or another
identified stakeholder.

Weak: \> As a user, I want a new button.

Stronger: \> As an applicant, I want to save an incomplete application
so that I can return to it later without entering the information again.

Ask: What problem does this solve? Who benefits? What outcome improves?

## 9.4 E --- Estimable

The team should understand the story well enough to estimate its
relative size or effort.

A story may not be estimable when:

-   The user role is unclear.
-   The expected behavior is unknown.
-   A key integration has not been investigated.
-   Business rules are missing.
-   The story contains too many unrelated capabilities.

The next step may be clarification, a technical investigation or
splitting the story.

## 9.5 S --- Small

A story should be manageable for the team's delivery cycle.

Too large: \> As an applicant, I want to complete the entire admission
process online.

Possible smaller stories:

-   Register an account.
-   Complete personal details.
-   Enter academic details.
-   Upload documents.
-   Review the application.
-   Submit the application.
-   View application status.

The correct split depends on the team's workflow and how it can deliver
meaningful value.

## 9.6 T --- Testable

A story must have observable outcomes that can be verified.

Not testable: \> As an applicant, I want a great experience.

More testable: \> As an applicant, I want to see a confirmation message
and application reference after successful submission so that I know my
application was received.

The team can define criteria to check the confirmation and reference
behavior.

------------------------------------------------------------------------

# 10. Applying INVEST: a worked review

Consider this draft:

> As a student, I want to manage everything in the admission portal so
> that the portal is useful.

Review it using INVEST:

  -----------------------------------------------------------------------
  Principle               Review                  Improvement needed
  ----------------------- ----------------------- -----------------------
  Independent             "Everything" contains   Split into smaller
                          many capabilities       stories

  Negotiable              No implementation is    Keep it outcome-focused
                          prescribed              

  Valuable                "Useful" does not       Identify a real user
                          explain a specific      benefit
                          benefit                 

  Estimable               Scope is too broad      Define one capability

  Small                   Clearly too large       Separate registration,
                                                  application, documents
                                                  and status

  Testable                No observable outcome   Write measurable or
                                                  observable acceptance
                                                  criteria
  -----------------------------------------------------------------------

Improved story:

> As an applicant, I want to save my incomplete application as a draft
> so that I can continue completing it later.

Possible acceptance criteria:

1.  A signed-in applicant can save an application that is not yet
    complete.
2.  The saved application is marked as a draft.
3.  The applicant can reopen their own draft.
4.  The saved information is available when the applicant returns.
5.  Another applicant cannot access the draft.

The exact retention period, autosave behavior and editable fields should
be clarified if they are in scope.

------------------------------------------------------------------------

# 11. Splitting large user stories

A story that is too large may be called an **epic** or may simply need
refinement. An epic is a large body of related work that is usually
divided into smaller stories.

Example epic:

> Manage admission applications.

Possible stories:

1.  As an applicant, I want to create an account so that I can access
    the portal.
2.  As an applicant, I want to enter my personal details so that the
    college can identify me.
3.  As an applicant, I want to enter my academic details so that the
    college can assess my eligibility.
4.  As an applicant, I want to upload required documents so that the
    admissions team can verify my information.
5.  As an applicant, I want to save my application as a draft so that I
    can continue later.
6.  As an applicant, I want to submit my completed application so that
    it can be reviewed.
7.  As an admission officer, I want to review submitted applications so
    that I can make admission decisions.
8.  As an applicant, I want to view my application status so that I know
    its progress.

## 11.1 Useful splitting approaches

  -----------------------------------------------------------------------
  Approach                How to split            Example
  ----------------------- ----------------------- -----------------------
  By workflow step        Separate stages of a    Create, complete,
                          process                 submit and review

  By user role            Separate capabilities   Applicant view and
                          for different actors    staff review

  By business rule        Separate materially     Standard application
                          different rules         and late application

  By data variation       Separate meaningful     Upload identity proof
                          data or document types  and academic records

  By happy path and       Separate normal and     Successful submission
  exception               exceptional behavior    and handling incomplete
                          when appropriate        submission
  -----------------------------------------------------------------------

Do not split a story into technical fragments that provide no
independently understandable user or business outcome unless the team
has a clear reason to track technical work separately.

------------------------------------------------------------------------

# 12. Common user-story and acceptance-criteria mistakes

  -----------------------------------------------------------------------
  Mistake                 Why it is a problem     Better approach
  ----------------------- ----------------------- -----------------------
  Writing from the        The user need and       Identify the user or
  system's perspective    benefit may be hidden   stakeholder who needs
  only                                            the outcome

  Missing the benefit     The reason for the      Complete the "so that"
                          story is unclear        part meaningfully

  Using vague words       The team may interpret  Clarify terms and
                          the story differently   expected outcomes

  Writing an entire       It is difficult to      Split it into smaller
  project as one story    estimate and deliver    capabilities

  Prescribing technical   It limits solution      Describe the user
  design too early        discussion              outcome

  Writing acceptance      They cannot be checked  Use observable
  criteria as opinions    consistently            conditions

  Forgetting exception    Important behavior may  Consider invalid,
  scenarios               remain undefined        missing and
                                                  unauthorized situations

  Confusing acceptance    Implementation work is  Keep outcomes and
  criteria with tasks     mistaken for user value technical tasks
                                                  distinct

  Treating INVEST as a    Some real stories have  Use INVEST as a
  rigid pass/fail law     unavoidable             discussion and
                          dependencies            improvement checklist

  Writing too many        The story becomes       Include relevant
  criteria                difficult to understand conditions for the
                                                  agreed scope
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 13. Industry scenario --- online admission portal

A college wants applicants to complete and submit admission applications
online.

Stakeholders have requested:

-   Applicants can create accounts.
-   Applicants can enter personal and academic details.
-   Applicants can upload documents.
-   Applicants can save incomplete applications.
-   Applicants can submit completed applications.
-   Applicants can view application status.
-   Admission officers can review applications.
-   Admission officers can request missing information.

### Example user story set

  -----------------------------------------------------------------------
  ID                User story        Example role      Intended benefit
                    summary                             
  ----------------- ----------------- ----------------- -----------------
  US-01             Create an account Applicant         Access the portal

  US-02             Enter personal    Applicant         Provide identity
                    details                             information

  US-03             Enter academic    Applicant         Provide
                    details                             information for
                                                        eligibility
                                                        review

  US-04             Upload required   Applicant         Supply supporting
                    documents                           evidence

  US-05             Save a draft      Applicant         Continue later

  US-06             Submit completed  Applicant         Begin admission
                    application                         review

  US-07             View application  Applicant         Understand
                    status                              progress

  US-08             Review submitted  Admission officer Assess applicants
                    applications                        

  US-09             Request missing   Admission officer Complete the
                    information                         review record
  -----------------------------------------------------------------------

### Example detailed story

**US-06 --- Submit completed application**

> As an applicant, I want to submit my completed application so that it
> can be considered by the admissions team.

**Acceptance criteria**

-   Given the applicant is signed in and all mandatory information is
    complete, when the applicant submits the application, then the
    application is recorded as submitted.
-   Given required documents are missing, when the applicant attempts to
    submit, then submission is prevented and the missing items are
    identified.
-   Given submission succeeds, when the confirmation is displayed, then
    a unique application reference is shown.
-   Given the application is submitted, when the applicant returns to
    the application page, then the application is shown with its current
    status.

### Questions that remain for stakeholder confirmation

-   Which fields are mandatory?
-   Which documents are required for each applicant category?
-   Can an applicant edit a submitted application?
-   Is there a submission deadline?
-   What happens if submission fails because of a network interruption?
-   Is there a limit on the number of applications per applicant?
-   What is the expected behavior if the applicant submits twice?

The BA should record these questions and obtain answers. The examples do
not establish the college's actual admission policy.

------------------------------------------------------------------------

# 14. Quick revision sheet

  -----------------------------------------------------------------------
  Concept                             Remember
  ----------------------------------- -----------------------------------
  User story                          Short description of a need from a
                                      user's perspective

  Standard format                     As a \[role\], I want \[goal\], so
                                      that \[benefit\]

  Role                                Who needs the capability

  Goal                                What the user wants to accomplish

  Benefit                             Why the goal matters

  Acceptance criteria                 Conditions the story must satisfy

  Given                               Starting context or condition

  When                                Action or event

  Then                                Expected result

  Epic                                Large body of related work,
                                      normally split into stories

  Refinement                          Clarify and prepare backlog items

  INVEST                              Independent, Negotiable, Valuable,
                                      Estimable, Small, Testable

  Definition of Done                  Shared team-wide completion
                                      standard

  Task                                Work performed to implement a
                                      capability
  -----------------------------------------------------------------------

**Memory aid:** A story explains the need. Acceptance criteria explain
what must be true. INVEST helps assess story quality.

------------------------------------------------------------------------

# 15. Interview preparation --- questions and answers

## Q1. What is a user story?

**Answer:**

A user story is a short description of a requirement from the
perspective of a user or stakeholder. It explains who needs a
capability, what they want to do and why it provides value.

**Example:** As an applicant, I want to view my application status so
that I can understand its progress.

**Follow-up:** Is a user story a complete specification?

**Answer:** No. It is a starting point for discussion and refinement.
The team adds acceptance criteria and clarifies business rules,
dependencies and open questions.

## Q2. What is the standard format of a user story?

**Answer:**

"As a \[user role\], I want \[goal\], so that \[benefit\]."

The role identifies who needs it, the goal describes the capability and
the benefit explains why it matters.

**Follow-up:** What if the benefit is unclear?

**Answer:** Ask the stakeholder why the capability is needed and what
outcome it is expected to improve. Do not invent a benefit.

## Q3. What are acceptance criteria?

**Answer:**

Acceptance criteria are specific conditions that a user story must
satisfy to be accepted. They make expected behavior clear and provide a
basis for review and testing.

**Example:** After a successful application submission, the portal
displays a unique application reference.

**Follow-up:** Can a story have multiple acceptance criteria?

**Answer:** Yes. A story may need multiple criteria to cover successful
behavior, validation, permissions and relevant exception scenarios.

## Q4. Explain Given--When--Then.

**Answer:**

Given--When--Then is a structured way to describe a scenario. Given
states the starting condition, When states the action or event, and Then
states the expected result.

**Example:** Given an applicant is signed in, when they submit a
complete application, then the application is recorded as submitted.

**Follow-up:** Why is this format useful?

**Answer:** It helps business stakeholders, developers and testers
discuss the same expected behavior in a clear, structured way.

## Q5. What does INVEST stand for?

**Answer:**

INVEST stands for Independent, Negotiable, Valuable, Estimable, Small
and Testable. It is a checklist used to review and improve user stories.

**Follow-up:** Which principle is most difficult to satisfy?

**Answer:** It depends on the story. For example, independence may be
difficult where a capability relies on an existing account or
integration. INVEST is a guide, not a rule that every dependency can be
removed.

## Q6. What is the difference between a user story and a use case?

**Answer:**

A user story is a concise description of a user's need and benefit. A
use case generally provides a more structured description of
interactions between an actor and a system, including normal and
alternate flows.

**Follow-up:** Can both be used in one project?

**Answer:** Yes. A team may use user stories for backlog planning and
more detailed use cases for complex interactions or documentation needs.

## Q7. What is the difference between acceptance criteria and Definition of Done?

**Answer:**

Acceptance criteria are specific to a story and define its expected
behavior. Definition of Done is a shared team standard for considering
work complete, such as code review and required testing.

**Follow-up:** Can acceptance criteria replace the Definition of Done?

**Answer:** No. They serve different purposes and may both apply to the
same story.

## Q8. How do you handle a story that is too large?

**Answer:**

I would clarify the overall goal and split the story into smaller,
meaningful capabilities. I may split by workflow step, user role,
business rule or normal and exception behavior.

**Follow-up:** What is an epic?

**Answer:** An epic is a large body of related work that is usually
divided into smaller user stories.

## Q9. What makes acceptance criteria testable?

**Answer:**

They describe observable or measurable outcomes with enough detail for
someone to determine whether the condition is satisfied.

**Example:** "The portal displays a unique application reference after
successful submission" is more testable than "submission should work
well."

**Follow-up:** Should acceptance criteria specify the programming
language or database?

**Answer:** Usually not. They should focus on expected behavior unless a
technical constraint is explicitly part of the agreed requirement.

## Q10. What would you do if developers say a story is not estimable?

**Answer:**

I would ask what information is missing, revisit the story with the
relevant stakeholders and clarify the user, expected behavior, rules,
dependencies or integration details. If it is too large, I would help
split it. A technical investigation may be needed for unknowns.

**Follow-up:** Should the BA guess an estimate?

**Answer:** No. The team responsible for estimation should estimate
based on its understanding. The BA helps make the requirement clearer.

## Q11. Can a user story contain non-functional requirements?

**Answer:**

Yes. Quality expectations such as performance, security, accessibility
or availability may be captured as acceptance criteria or linked
non-functional requirements, depending on the team's documentation
approach. They should not be lost simply because the team uses user
stories.

**Follow-up:** Give an example.

**Answer:** A story about viewing application status may include an
agreed response-time criterion or access-control condition.

## Q12. What happens during story refinement?

**Answer:**

The team clarifies the story, discusses acceptance criteria, identifies
dependencies and open questions, considers whether it is small enough,
and prepares it for planning. Estimation may also happen as part of the
team's process.

**Follow-up:** Is refinement a one-time activity?

**Answer:** Not necessarily. Stories may be refined over multiple
discussions as the team learns more.

------------------------------------------------------------------------

# 16. Daily quiz

Try each question before checking the answer key.

### Question 1

Which is the best user story format?

A. The system should have a dashboard.\
B. As a \[role\], I want \[goal\], so that \[benefit\].\
C. Build the database and API.\
D. The feature must be completed quickly.

### Question 2

In Given--When--Then, what does "Then" describe?

A. The starting condition.\
B. The user role.\
C. The expected result.\
D. The implementation task.

### Question 3

Which INVEST principle asks whether a story provides meaningful benefit?

A. Independent.\
B. Negotiable.\
C. Valuable.\
D. Estimable.

### Question 4

Which is the strongest acceptance criterion for successful application
submission?

A. The page should look nice.\
B. The system should be user-friendly.\
C. The application is recorded as submitted and a unique reference is
displayed.\
D. Developers should use a suitable database.

### Question 5

What is the main difference between acceptance criteria and Definition
of Done?

A. They are exactly the same.\
B. Acceptance criteria are story-specific; Definition of Done is a
shared team completion standard.\
C. Definition of Done describes the user's business benefit.\
D. Acceptance criteria are only for developers.

## Answer key with explanations

1.  **B** --- The format identifies the user, goal and benefit.
2.  **C** --- Then describes the expected outcome after the action.
3.  **C** --- Valuable asks whether the story provides value to a user
    or stakeholder.
4.  **C** --- It describes observable outcomes that can be verified.
5.  **B** --- One applies to the specific story; the other is a broader
    team standard.

------------------------------------------------------------------------

# 17. Knowledge check --- explain in your own words

1.  What is a user story, and why is it written from a user's
    perspective?
2.  Identify the role, goal and benefit in a user story you create.
3.  How is a user story different from a functional requirement?
4.  What are acceptance criteria, and why are they important?
5.  Write one Given--When--Then scenario for a successful application
    submission.
6.  Write one scenario for an applicant attempting to submit an
    incomplete application.
7.  Explain all six INVEST principles.
8.  What would you do if a story is too large to estimate?
9.  How are acceptance criteria different from Definition of Done?
10. Why should a BA record open questions instead of guessing?

## Suggested answers

1.  It is a concise description of a user's need and benefit; the user
    perspective keeps the focus on the outcome.
2.  Example: "As an applicant, I want to save my application as a draft
    so that I can continue later." Role: applicant; goal: save a draft;
    benefit: continue later.
3.  A user story expresses a need in a user-centered format; a
    functional requirement states a specific behavior the solution must
    provide.
4.  They define conditions for accepting the story and support
    consistent validation.
5.  Given a signed-in applicant with required information complete, when
    they submit, then the application is recorded and a reference is
    displayed.
6.  Given a signed-in applicant with a required field missing, when they
    submit, then submission is prevented and the missing field is
    identified.
7.  Independent, Negotiable, Valuable, Estimable, Small and Testable.
8.  Clarify missing details, investigate uncertainty or split the story
    into smaller meaningful items.
9.  Acceptance criteria are specific to a story; Definition of Done is
    the team's shared completion standard.
10. Guessing can create incorrect assumptions and lead to a solution
    that does not meet the real business need.

------------------------------------------------------------------------

# 18. Day 10 completion checklist

-   [ ] I can explain a user story in plain English.
-   [ ] I can write a story using role, goal and benefit.
-   [ ] I can distinguish stories, requirements, tasks and use cases.
-   [ ] I can write clear, observable acceptance criteria.
-   [ ] I can write Given--When--Then scenarios.
-   [ ] I can distinguish acceptance criteria from Definition of Done.
-   [ ] I can explain all six INVEST principles.
-   [ ] I can identify and split an oversized story.
-   [ ] I can identify missing information and record open questions.
-   [ ] I have answered the five-question quiz and reviewed incorrect
    answers.
-   [ ] I can answer at least two interview questions without reading
    the answers.

------------------------------------------------------------------------

**Next syllabus topic --- Day 11: Use cases, actors, preconditions,
flows and alternate scenarios.**
