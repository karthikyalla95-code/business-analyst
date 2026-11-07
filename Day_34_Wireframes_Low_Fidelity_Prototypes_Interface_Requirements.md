# Day 34: Wireframes, Low-Fidelity Prototypes and Interface Requirements

**Phase:** 6 — Tools, Testing and Solution Validation  
**Approved topic:** Wireframes, low-fidelity prototypes and interface requirements  
**Approved independent mini-project:** Application Wireframe  
**Estimated time:** 2–3 hours

---

## 1. Why wireframes matter

A stakeholder says, “Customers should be able to track their orders.” This describes a need, but it does not explain what a customer sees, where they click, what information is displayed or what happens when an order cannot be found.

A wireframe makes the proposed screen structure visible so stakeholders, BAs, designers, developers and testers can discuss it before implementation.

## 2. Learning objectives

By the end of this lesson, you should be able to:
- Explain wireframes, mockups and prototypes.
- Choose an appropriate level of fidelity.
- Convert requirements and user stories into screen elements.
- Specify fields, controls, navigation, validation and feedback.
- Design empty, loading, error and success states.
- Consider responsive behavior and accessibility.
- Annotate a wireframe and link it to requirements.
- Review a design and record decisions.
- Complete the **Application Wireframe** mini-project.

## 3. Core concepts

### 3.1 Wireframe

A wireframe is a simplified representation of a screen. It focuses on:
- Page structure and content placement.
- Navigation and information hierarchy.
- Inputs, buttons, links and other controls.
- Basic user interactions.
- Important states and messages.

It is not a finished visual design. Think of it as a floor plan: it explains arrangement before decoration.

### 3.2 Wireframe vs. mockup vs. prototype

| Artifact | Focus | Typical use |
|---|---|---|
| Wireframe | Structure, content, controls and layout | Early requirement and layout discussions |
| Mockup | Detailed visual appearance, colors, typography and branding | Visual design review |
| Prototype | Simulated interaction or navigation between screens | Exploring and validating user flows |

A prototype may be low- or high-fidelity. A clickable wireframe is a low-fidelity prototype.

### 3.3 Fidelity

- **Low fidelity:** Boxes, labels, simple placeholders. Best for early exploration and quick feedback.
- **Medium fidelity:** More realistic content, spacing and component detail. Useful for validating layout and interaction.
- **High fidelity:** Near-final visual styling and detailed components. Useful for visual review before implementation.

Start with low fidelity while requirements are still changing. Do not spend time polishing colors before the team agrees on what the screen must do.

### 3.4 Common interface elements

- Header: product identity, account, help.
- Navigation: menu, tabs, breadcrumbs, side navigation.
- Content: information, lists, tables, cards.
- Input: text, date, number, dropdown, checkbox.
- Actions: buttons and links.
- Feedback: alerts, validation, loading and success messages.
- Footer: supporting links and contact information.

## 4. Start with requirements

### 4.1 Business requirement example

“Customers must be able to view the current status and expected delivery date of an order.”

Possible functional requirements:

| ID | Requirement |
|---|---|
| FR-01 | A signed-in customer can open My Orders. |
| FR-02 | The page displays orders belonging to that customer. |
| FR-03 | Each order displays order number, order date and status. |
| FR-04 | An expected delivery date is shown when a confirmed estimate is available. |
| FR-05 | The customer can open an order to view tracking details. |
| FR-06 | An empty-state message appears when the customer has no orders. |
| FR-07 | An understandable error appears if order information cannot be loaded. |
| FR-08 | The customer can search using an order number, subject to agreed search rules. |

User story:

“As a signed-in customer, I want to view my orders and their delivery status so that I can understand the progress of my purchases.”

Acceptance criteria:
1. Given a signed-in customer with orders, when My Orders opens, then only that customer's orders are displayed.
2. Given an order with a confirmed delivery estimate, when the order is displayed, then the estimate appears in the agreed format.
3. Given a customer with no orders, when My Orders opens, then an empty-state message appears.
4. Given the order service is unavailable, when the page loads, then an error message and retry action are available.

### 4.2 Requirement-to-screen mapping

| Requirement | Screen element | Behavior |
|---|---|---|
| FR-01 | My Orders navigation | Opens the order list |
| FR-02 | Order list | Displays the signed-in customer's orders |
| FR-03 | Order summary fields | Shows agreed values and date format |
| FR-04 | Delivery estimate | Appears only when confirmed |
| FR-05 | View details action | Opens selected order details |
| FR-06 | Empty-state panel | Explains that no orders exist |
| FR-07 | Error panel and Retry | Explains the problem and retries the request |
| FR-08 | Search field and action | Searches according to approved rules |

Maintain traceability between requirement IDs and screen annotations. Do not let a requirement disappear when translating it into a design.

## 5. Wireframing process

### Step 1 — Identify user and goal
Ask who uses the screen, what they want to accomplish, what information they need and what action they should take.

### Step 2 — Identify the entry point
Determine whether the user reaches the screen through navigation, a dashboard, search results, a notification or a previous workflow step.

### Step 3 — List screen content
Separate:
- Information to display.
- Information the user enters.
- Actions the user can take.
- Feedback the system must provide.

### Step 4 — Group related elements
Group page title, search/filter controls, order summaries, tracking information and support actions logically.

### Step 5 — Arrange the layout
Place important information first. Use consistent alignment, clear labels and sensible spacing. Keep related controls near the information they affect.

### Step 6 — Define states
Consider default, loading, empty, no-results, validation-error, service-error, success, disabled and access-denied states.

### Step 7 — Annotate and review
Explain rules that are not obvious from the drawing. Link annotations to requirements. Record stakeholder feedback, decisions and open questions.

## 6. Interface requirements

A wireframe shows the layout; interface requirements explain what each element does.

### 6.1 Categories

| Category | Questions |
|---|---|
| Layout | Which sections and elements appear, and in what order? |
| Navigation | How does the user enter, move through and leave the screen? |
| Content | Which labels, values and messages are displayed? |
| Input | What data can the user enter? |
| Validation | Which values are allowed? What happens when input is invalid? |
| Actions | What happens when a control is selected? |
| Feedback | How is progress, success or failure communicated? |
| Permissions | Who can see or perform each action? |
| Accessibility | Can users operate and understand the interface with different abilities and input methods? |
| Responsive behavior | How does the layout adapt to smaller screens? |
| Integration | Which data comes from another system? |
| Security and privacy | What information is shown, masked or protected? |

### 6.2 Field specification example

| Attribute | Order-number search |
|---|---|
| Field ID | UI-ORD-01 |
| Label | Search order number |
| Purpose | Find a specific order |
| Type | Text |
| Required | No |
| Placeholder | Enter order number |
| Maximum length | Confirm with product/technical owner |
| Allowed characters | Confirm approved order-number format |
| Validation | Check format before submission |
| Error message | “Enter a valid order number.” |
| Action | Search orders belonging to the signed-in customer |
| Security | Never reveal another customer's order |

Do not invent technical limits or business rules. Record unanswered questions and confirm them.

### 6.3 Validation rules

Examples:
- Required: field must not be blank.
- Format: email must follow the agreed format.
- Range: quantity must be within the approved range.
- Length: identifier must meet its defined length.
- Relationship: end date must not be earlier than start date.
- Authorization: user must have permission to access the record.

For each validation rule, specify what is checked, when it is checked, the message shown, whether entered data is retained and what the user can do next.

Use clear messages. “Invalid input” is less useful than “Enter a date on or after 1 January 2026.”

### 6.4 Screen states

| State | Example | Expected behavior |
|---|---|---|
| Empty | Customer has no orders | Explain no orders are available and offer a useful next step |
| No results | Search finds no match | Explain no match was found and allow search editing |
| Validation error | Search format is invalid | Identify field and explain correction |
| Loading | Orders are being retrieved | Show progress; prevent accidental duplicate actions where needed |
| Service error | Order service is unavailable | Explain data could not load and offer retry |
| Access denied | User tries to view another customer's order | Do not expose protected information |
| Success | Search returns a match | Show result and next action |

Never show stack traces, secrets or sensitive technical details to end users.

## 7. Layout, usability and accessibility

### 7.1 Visual hierarchy
Use a clear page title, descriptive section headings, consistent alignment, readable labels, sensible spacing and clear primary/secondary actions.

Avoid too many competing buttons, unexplained icons, dense paragraphs and inconsistent labels.

### 7.2 Navigation
Navigation should answer:
- Where am I?
- What can I do?
- Where can I go next?
- How can I return?

Common patterns include top navigation, side navigation, tabs and breadcrumbs. Use tabs for related views within a section, not as a substitute for a coherent navigation structure.

### 7.3 Responsive design
Do not simply shrink a desktop design to fit a phone. Consider:
- Stacking columns vertically.
- Replacing wide tables with readable cards or carefully designed scrollable regions.
- Keeping primary actions easy to reach.
- Maintaining readable text and touch targets.
- Preventing clipped content.
- Keeping labels visible.

Confirm exact breakpoints with the design and development team.

### 7.4 Accessibility basics
Raise accessibility requirements early:
- Form fields need programmatic labels, not only placeholder text.
- Do not communicate information by color alone.
- Ensure sufficient text and control contrast.
- Keyboard users must be able to reach and operate controls.
- Focus order should be logical and visible.
- Error messages should identify the field and explain correction.
- Informative images need appropriate alternative text.
- Headings should describe content structure.
- Controls need clear accessible names and states.

For compliance, consult the applicable standard and accessibility specialists. A wireframe review does not replace accessibility testing.

## 8. Wireframe annotations

Annotations explain behavior that a drawing cannot fully communicate.

Example:

| Annotation | Requirement / rule |
|---|---|
| A1 | Display orders belonging to the authenticated customer only. |
| A2 | Sort by order date, newest first, unless another default is approved. |
| A3 | Show delivery date only when a confirmed estimate exists. |
| A4 | View Details opens the selected order. |
| A5 | Empty state appears after a successful response containing no orders. |
| A6 | Service error appears when the order request fails; Retry repeats the request. |
| A7 | On narrow screens, order information is presented in a readable stacked layout. |

Use requirement IDs in annotations to support review and testing.

## 9. Worked example: My Orders screen

Low-fidelity layout:

~~~text
+----------------------------------------------------------+
| BRAND / CUSTOMER PORTAL                  Help   Account  |
+----------------------------------------------------------+
| Home  | My Orders  | Profile  | Support                  |
+----------------------------------------------------------+
| My Orders                                                |
| View your recent purchases and delivery progress.        |
|                                                          |
| [ Search order number________________ ] [ Search ]       |
|                                                          |
| Filters: [All statuses v]       Sort: [Newest first v]   |
|                                                          |
| ORDER #       ORDER DATE     STATUS       DELIVERY       |
| ORD-1042      12 May         In transit   16 May         |
| [View details]                                           |
|----------------------------------------------------------|
| ORD-1038      08 May         Delivered    11 May         |
| [View details]                                           |
|----------------------------------------------------------|
| ORD-1029      02 May         Processing   To be confirmed|
| [View details]                                           |
|                                                          |
| Need help with an order? [Contact support]               |
+----------------------------------------------------------+
~~~

These are sample values, not approved business data.

Questions to clarify:
- How many orders appear per page?
- Is pagination or infinite scrolling required?
- Which order statuses are valid?
- Is delivery date a date or date-time?
- What does “To be confirmed” mean?
- Is partial order-number search supported?
- What happens if multiple orders match?
- Are cancelled orders included in filters?
- What is the approved mobile layout?

Create at least four variants: default, empty, no-results and service-error. A loading state is also useful.

## 10. Stakeholder review

Ask:
- Does the screen support the user's goal?
- Is the information complete and accurate?
- Are labels understandable?
- Are primary actions visible?
- Are alternate states covered?
- Are permissions and sensitive data considered?
- Does the screen match business rules?
- Are mobile and accessibility needs considered?
- Are any scenarios missing?

Record feedback:

| Feedback ID | Element | Feedback | Decision | Owner | Status |
|---|---|---|---|---|---|
| WF-01 | Order status | Add “Out for delivery” as a separate status | Confirm with status owner | Product Owner | Open |
| WF-02 | Search | First release searches by order number only | Accepted | BA | Done |
| WF-03 | Delivery date | Hide estimate if provider has not supplied one | Accepted | Product Owner | Done |

Record what was discussed, decisions, unresolved questions, owners and requirement changes. Silence is not approval; follow the agreed review process.

## 11. Follow-along exercise

Use paper, a whiteboard, PowerPoint, diagrams.net or Figma.

1. Draw a desktop frame.
2. Add header, navigation and main content.
3. Add page title, search field, search action, filters and order list.
4. Add a View Details action for each order.
5. Add support/help area.
6. Add numbered annotations.
7. Duplicate the screen and create empty, no-results, loading and error states.
8. Ask another person to find order ORD-1042 and explain its status using only your wireframe.
9. Record where they hesitate and improve unclear labels or missing information.

## 12. Independent mini-project: Application Wireframe

### 12.1 Problem statement

A business wants a customer portal where signed-in customers can locate an order, understand its status and open tracking information.

**Objective:** Create a low-fidelity Application Wireframe for the order-list screen, including its controls, important states, interface requirements and traceability to the business requirements.

### 12.2 Scenario and constraints

- A customer can view only their own orders.
- An order has an order number, order date and status.
- An estimated delivery date may or may not be available.
- A customer can open order details.
- The service may return no orders or an error.
- Status list, search format and pagination rules need confirmation.
- Use synthetic data only.

### 12.3 Workspace

~~~text
Day_34_Application_Wireframe/
├── README.md
├── requirements.md
├── wireframe_order_list.png
├── wireframe_empty_state.png
├── wireframe_error_state.png
├── interface_requirements.xlsx
├── annotations.md
└── review_feedback.md
~~~

### 12.4 Requirements input

Save as requirements.md:

~~~markdown
# Customer Portal — Order Tracking Requirements

## Business objective
Allow signed-in customers to find orders and understand delivery progress.

## User story
As a signed-in customer, I want to view my orders and their delivery status so that I can understand the progress of my purchases.

## Functional requirements
- FR-01: Customer can open My Orders after signing in.
- FR-02: Page displays orders belonging to the signed-in customer.
- FR-03: Each order displays order number, order date and status.
- FR-04: Expected delivery date appears when a confirmed estimate is available.
- FR-05: Customer can open an order to view tracking details.
- FR-06: Empty state appears when no orders are available.
- FR-07: Understandable error appears if order information cannot load.
- FR-08: Customer can search using an order number, subject to approved search rules.

## Non-functional considerations
- Protect customer and order information.
- Support keyboard navigation and readable labels.
- Provide usable desktop and mobile layouts.
- Do not expose technical error details to customers.

## Open questions
- What is the approved order status list?
- What is the order-number format?
- Is partial search supported?
- How many orders appear per page?
- What is the approved date format?
- What is the mobile table/card behavior?
~~~

### 12.5 Tasks

1. Identify the user's primary goal.
2. Create a low-fidelity desktop My Orders wireframe.
3. Create empty-state and error-state variants.
4. Include search, order information and View Details.
5. Add at least eight numbered annotations.
6. Document at least six interface elements.
7. Link interface elements to FR IDs.
8. Identify at least five unanswered stakeholder questions.
9. Create or sketch a mobile layout and explain the changes.
10. Conduct a review and record decisions.

### 12.6 Interface requirements template

Create a spreadsheet with columns:

~~~text
UI_ID,Screen,Element,Type,Requirement_ID,Label_or_Content,Behavior,Validation_or_Rule,Error_or_Alternate_State,Accessibility_Note,Open_Question
~~~

Example:

| UI ID | Element | Type | Requirement | Behavior |
|---|---|---|---|---|
| UI-01 | Page heading | Text | FR-01 | Displays “My Orders” |
| UI-02 | Order search | Text input | FR-08 | Accepts order number using approved format |
| UI-03 | Search | Button | FR-08 | Submits search |
| UI-04 | Order list | Table/cards | FR-02, FR-03 | Shows only customer's orders |
| UI-05 | Delivery estimate | Text | FR-04 | Shows only confirmed estimate |
| UI-06 | View Details | Link/button | FR-05 | Opens selected order |
| UI-07 | Empty-state panel | Message | FR-06 | Appears when successful response has no orders |
| UI-08 | Error panel | Message/action | FR-07 | Explains failure and offers retry |

### 12.7 Annotation template

Save as annotations.md:

~~~markdown
# My Orders Wireframe — Annotations

| Annotation | Element | Requirement ID | Rule / behavior | Open question |
|---|---|---|---|---|
| A1 | Order list | FR-02 | Only signed-in customer's orders are shown | Confirm authorization |
| A2 | Order date | FR-03 | Display approved date format | Which format? |
| A3 | Delivery estimate | FR-04 | Hide if no confirmed estimate exists | What wording should appear? |
| A4 | View Details | FR-05 | Open selected order | Same page or new page? |
| A5 | Empty state | FR-06 | Show when no orders are returned | What next action? |
| A6 | Error state | FR-07 | Show message and retry action | Confirm retry behavior |
~~~

Add at least two further annotations.

### 12.8 Review template

Save as review_feedback.md:

~~~markdown
# Wireframe Review

- Date:
- Reviewer(s):
- Screen version:

| ID | Element | Feedback | Decision | Owner | Status |
|---|---|---|---|---|---|

## Unresolved questions
1.
2.

## Changes made
1.
2.

## Review outcome
- [ ] Ready for detailed design
- [ ] Changes required
- [ ] Requirements clarification required
~~~

### 12.9 Expected result

A reviewer should be able to understand:
- Where the customer is.
- Which orders are displayed.
- How to search.
- How to open order details.
- What happens when there are no orders.
- What happens when the service fails.
- Which information is conditional.
- How the layout adapts to mobile.

Final colors and branding are not required. Clarity and traceability matter more than decoration.

### 12.10 Validation checklist

- [ ] Clear screen title and purpose.
- [ ] Navigation and entry point are understandable.
- [ ] Search field and action are visible.
- [ ] Order number, date and status are represented.
- [ ] Delivery estimate behavior is specified.
- [ ] View Details action is clear.
- [ ] Empty and error states are designed.
- [ ] At least eight annotations are present.
- [ ] Interface requirements link to functional requirements.
- [ ] Open questions are recorded rather than guessed.
- [ ] Mobile behavior is considered.
- [ ] Accessibility considerations are documented.
- [ ] Review feedback and decisions are recorded.

### 12.11 Common mistakes

| Mistake | Why it is a problem | Better approach |
|---|---|---|
| Starting with colors | Hides unresolved requirements | Start with user goal and structure |
| Drawing only the happy path | Alternate states are missed | Design empty, loading and error states |
| Using placeholder as label | Placeholder disappears during entry | Provide persistent labels |
| Unclear button names | Users cannot predict the result | Use action-specific labels |
| Guessing business rules | Design may contradict stakeholder needs | Record and confirm open questions |
| No annotations | Developers infer behavior | Add numbered notes and requirement IDs |
| Desktop-only design | Mobile users may lose actions | Review a narrow-screen layout |
| No traceability | Requirements may be omitted | Map elements to requirement IDs |
| Treating wireframe approval as final sign-off | Behavior may remain unresolved | Follow the agreed approval process |

### 12.12 Stuck ladder

1. List each requirement before drawing.
2. Hint: draw one box for each major page region, then place controls in the appropriate region.
3. Compare your layout with the worked example in Section 9.
4. Ask whether a user can complete the task without guessing.
5. Review empty, error and loading states separately.
6. Use the expected-result checklist only after attempting the work.

### 12.13 Submission evidence

Submit:
- Desktop My Orders wireframe.
- Empty-state and error-state wireframes.
- Interface requirements spreadsheet.
- Annotation list with requirement links.
- Mobile layout or adaptation notes.
- Stakeholder review feedback.
- Short explanation of one design decision and one unresolved question.

Optional extension: create a clickable low-fidelity flow from My Orders to Order Details. Day 35 introduces Figma fundamentals and screen-flow design.

## 13. Professional BA habits

1. Start with the user goal and requirements.
2. Show only information needed for the user's task.
3. Use familiar labels and predictable navigation.
4. Design alternate states, not only the ideal screen.
5. Document field rules and validation.
6. Consider privacy, permissions and accessibility early.
7. Link annotations to requirement IDs.
8. Label assumptions and sample data.
9. Record feedback and decisions.
10. Keep the wireframe simple enough to invite discussion.

## 14. Daily quiz

**Q1. What is the main purpose of a low-fidelity wireframe?**

A. Finalize brand colors  
B. Communicate screen structure and content  
C. Prove the application is secure  
D. Replace all requirements  

**Q2. Which statement best distinguishes a prototype from a static mockup?**

A. A prototype may allow interaction or navigation  
B. A prototype must always be fully coded  
C. A mockup always contains working APIs  
D. There is no difference  

**Q3. A customer has no orders. Which state should be shown?**

A. Loading forever  
B. Empty state  
C. Access denied  
D. Defect report  

**Q4. The approved order-number format is unknown. What should the BA do?**

A. Invent a format  
B. Remove search  
C. Record the question and confirm the rule  
D. Ask developers to guess  

**Q5. What is the best way to connect a wireframe control to a requirement?**

A. Use a requirement ID in an annotation or interface specification  
B. Use a random color  
C. Add decoration  
D. Leave it undocumented  

### Answers and explanations

1. **B.** Low-fidelity wireframes help people agree on structure, content and layout.
2. **A.** A prototype represents interaction or navigation and may be low or high fidelity.
3. **B.** An empty state explains that there is no data and can offer a useful next step.
4. **C.** Unknown business rules should be clarified, not invented.
5. **A.** Traceability supports coverage review and testing.

## 15. Interview preparation

### Question 1: What is a wireframe, and why does a BA use it?

**Answer:** A wireframe is a simplified representation of a screen showing structure, content, controls and navigation. A BA uses it to make requirements visible, discuss screen behavior with stakeholders and identify missing information before development.

### Question 2: What is the difference between a wireframe, mockup and prototype?

**Answer:** A wireframe focuses on structure and content. A mockup shows visual appearance in more detail. A prototype demonstrates interaction or navigation and can be low- or high-fidelity.

### Question 3: What do you include when documenting an interface requirement?

**Answer:** I document the screen and element, purpose, label, input or display type, linked requirement, behavior, validation rules, error and alternate states, permissions, accessibility considerations and unresolved questions.

### Question 4: How do you handle stakeholder feedback?

**Answer:** I record feedback, clarify the underlying need, assess its effect on requirements and related screens, and agree a decision with the appropriate stakeholder. I update the wireframe and linked requirements, then share the revised version for review.

### Question 5: Why include error and empty states?

**Answer:** Users may have no data, enter invalid information or experience a service failure. Designing these states helps the team specify clear feedback and predictable next steps.

## 16. Revision sheet

- **Wireframe:** Simplified screen structure and content.
- **Mockup:** Detailed static visual representation.
- **Prototype:** Representation of interaction or screen flow.
- **Low fidelity:** Simple boxes and labels for early discussion.
- **Interface requirement:** Specifies what a screen element displays or does.
- **Field specification:** Label, type, required status, rules, validation and feedback.
- **Empty state:** Behavior when no relevant data exists.
- **Error state:** Behavior when an operation fails.
- **Annotation:** Note explaining a rule not obvious from the drawing.
- **Traceability:** Link between requirements, screen elements and tests.
- **Responsive design:** Layout adapts to screen sizes and input methods.
- **Accessibility:** Interface can be understood and operated by people with different abilities.
- **Best habit:** Design from requirements and user goals; do not guess missing business rules.

## 17. Completion checklist

### Concepts
- [ ] I can explain wireframes, mockups and prototypes.
- [ ] I understand low-, medium- and high-fidelity designs.
- [ ] I can convert a requirement into screen elements.
- [ ] I can define interface and field requirements.
- [ ] I can explain empty, loading, error and validation states.
- [ ] I understand basic responsive and accessibility considerations.

### Practical work
- [ ] I created the Application Wireframe.
- [ ] I designed the default My Orders screen.
- [ ] I designed empty and error states.
- [ ] I wrote interface requirements for at least six elements.
- [ ] I added at least eight annotations.
- [ ] I linked screen elements to requirement IDs.
- [ ] I considered mobile behavior.

### Review
- [ ] I recorded open questions.
- [ ] I captured review feedback and decisions.
- [ ] I can explain one important design decision.
- [ ] I completed the quiz and reviewed incorrect answers.
- [ ] I can answer at least three interview questions without reading.

**Day 34 is complete when another person can understand the screen, its key behaviors and its relationship to the requirements without guessing.**

## 18. References

- Nielsen Norman Group — UX and wireframing articles: https://www.nngroup.com/
- Figma Learn — Design and prototyping resources: https://help.figma.com/hc/en-us/categories/360002051613-Learn-design
- W3C Web Accessibility Initiative — Accessibility fundamentals: https://www.w3.org/WAI/fundamentals/
- GOV.UK Design System — Components and patterns: https://design-system.service.gov.uk/
- Material Design — Layout and components: https://m3.material.io/
- IIBA — Business analysis resources: https://www.iiba.org/

---

**Roadmap alignment:** Day 34 follows the approved topic “Wireframes, low-fidelity prototypes and interface requirements” and uses the exact approved mini-project title “Application Wireframe”.
