# Day 35: Figma Fundamentals and Screen-Flow Design

**Phase:** 6 — Tools, Testing and Solution Validation  
**Approved topic:** Figma fundamentals and screen-flow design  
**Approved mini-project:** Customer Portal Prototype  
**Estimated time:** 2–3 hours

---

## 1. Why Figma matters to a Business Analyst

A wireframe shows the structure of a screen. A clickable prototype helps stakeholders understand how a customer moves from one screen to another.

For example, a customer portal may contain:
1. Sign in.
2. View orders.
3. Open an order.
4. View tracking information.
5. Return to the order list.

Figma allows you to create screens and connect them into a prototype. Stakeholders can try the proposed journey before the application is developed.

A BA can use prototypes to:
- Make requirements easier to understand.
- Validate navigation and user journeys.
- Identify missing steps and alternate paths.
- Collect feedback before development.
- Communicate proposed behavior to developers and testers.

**Important:** A clickable prototype is not a working application. It does not automatically implement authentication, APIs, databases or business rules.

## 2. Learning objectives

By the end of this lesson, you should be able to:
- Explain Figma's role in business analysis.
- Create and organize a design file.
- Understand pages, frames, layers, shapes, text and components.
- Build simple desktop and mobile screens.
- Use alignment, spacing, constraints and Auto Layout.
- Create reusable components and variants.
- Connect screens using prototype interactions.
- Define navigation, overlays and transitions.
- Test a prototype and record feedback.
- Complete the Customer Portal Prototype mini-project.

## 3. Figma vocabulary

| Term | Meaning | Example |
|---|---|---|
| Workspace/team | Shared area for a group | Product design team |
| Project | Container for related files | Customer Portal |
| Design file | File containing screens and assets | Customer Portal UI |
| Page | Section inside a design file | Wireframes, components |
| Canvas | Working area where objects are placed | Area around screens |
| Frame | Container representing a screen or section | Desktop sign-in |
| Layer | Individual object or group | Heading, button, icon |
| Shape | Basic visual object | Rectangle, line, ellipse |
| Text layer | Text placed on the canvas | “Sign in” |
| Component | Reusable design element | Primary button |
| Instance | A use of a component | Button on another screen |
| Variant | Related version of a component | Default, disabled |
| Auto Layout | Layout that arranges items and responds to content | Button with padding |
| Constraints | Rules for an object's behavior when its parent resizes | Keep logo left-aligned |
| Prototype | Connected screens and interactions | Click Sign in to open My Orders |
| Overlay | Temporary content above a screen | Confirmation dialog |
| Starting point | Beginning of a prototype flow | Sign-in screen |

Figma's interface and panel positions can change. Learn the concepts rather than memorizing a particular toolbar location.

## 4. Set up Figma

### 4.1 Access and create a file

1. Open https://www.figma.com/
2. Create an account or sign in.
3. Choose an available starter/free option for learning.
4. Create a new design file.
5. Name it Customer Portal Prototype — Day 35.

Plan limits and available features can change. If a feature is unavailable in your account, use an available basic alternative.

### 4.2 Organize the file

Create these pages:
- 00 — Project Overview
- 01 — Wireframes
- 02 — Components
- 03 — Desktop Screens
- 04 — Mobile Screens
- 05 — Prototype Flow

Organization makes it easier for stakeholders to find screens, distinguish early wireframes from refined screens and locate reusable elements.

### 4.3 Understand the editor

- **Toolbar:** Select, draw, add text and create frames.
- **Layers panel:** Shows the hierarchy of objects.
- **Canvas:** Main working area.
- **Properties panel:** Controls layout, size, color and typography for the selected object.
- **Prototype controls:** Configure interactions between frames.
- **Share/present controls:** Share the design or preview the prototype.

## 5. Create your first screen

A frame is a container that can represent a screen.

Follow along:
1. Open the Wireframes page.
2. Select the Frame tool.
3. Choose a desktop preset or draw a suitably sized frame.
4. Rename it 01 — Sign In.
5. Add a text layer for the portal name.
6. Add a heading: Welcome back.
7. Add labeled input placeholders: Email address and Password.
8. Add a Sign in button.
9. Add a Forgot password? link.
10. Keep the design simple; use basic shapes and text.

Create two more frames:
- 02 — My Orders
- 03 — Order Details

### 5.1 Name layers meaningfully

Avoid names such as Rectangle 14, Text 8 and Frame 2.

Prefer:
- Header / Portal name
- Form / Email field
- Form / Password field
- Action / Sign in
- Navigation / My Orders

Meaningful names help teammates understand and edit the file.

## 6. Basic design operations

### 6.1 Select, move and group

- Select an object to edit it.
- Drag to reposition it.
- Use alignment controls to line up objects.
- Group related objects when it makes the structure clearer.
- Rename important layers.

### 6.2 Shapes and text

Use shapes for input fields, buttons, cards, dividers and image placeholders.

Use text for headings, field labels, help text, status values, button labels and error messages.

Prefer persistent labels over placeholder-only fields. For example, show Email address above the field rather than relying only on faint placeholder text.

### 6.3 Alignment and spacing

Check that:
- Related elements align.
- Fields have consistent widths.
- Vertical spacing follows a pattern.
- Buttons are near the task they perform.
- Text does not overlap other elements.
- Content has sufficient room around it.

A simple practice spacing scale might be 8, 16, 24 and 32 pixels. This is an exercise convention, not a universal rule.

### 6.4 Frames and hierarchy

A My Orders frame may contain:
- Header
- Navigation
- Page title
- Search section
- Filter section
- Order list
  - Order card 1
  - Order card 2
- Support link

A clear hierarchy makes the file easier to maintain.

## 7. Auto Layout — beginner introduction

Auto Layout arranges items inside a frame and can adapt spacing and sizing as content changes.

Imagine a button containing the label View details. Without Auto Layout, you might manually resize the button when its label changes. With Auto Layout, the button can maintain padding around its content.

### 7.1 Useful situations

- Buttons that fit their labels.
- Forms with consistent vertical spacing.
- Cards whose content can grow.
- Navigation rows.
- Repeated list items.

### 7.2 Main properties

| Property | Meaning |
|---|---|
| Direction | Arrange children horizontally or vertically |
| Gap | Space between child items |
| Padding | Space between container edge and content |
| Alignment | How children line up |
| Resizing | Hug content, fill available space or use a fixed size |

### 7.3 Follow-along: create a button

1. Create a text layer named View details.
2. Apply Auto Layout using the current editor control.
3. Add horizontal and vertical padding.
4. Give the container a visible fill and rounded corners if desired.
5. Change the label to Track this order.
6. Observe how the container adapts.

### 7.4 Hug, fill and fixed

- **Hug contents:** Container sizes itself around its content.
- **Fill container:** Child expands to use available parent space.
- **Fixed:** Uses a specified size.

Example: a button may hug its label, a search field may fill a row, and a logo may use a fixed size.

Do not force Auto Layout everywhere. Use it where content and spacing need to adapt.

## 8. Components and variants

### 8.1 Component

A component is a reusable design element. If five screens use the same primary button, create one component and reuse it.

Benefits:
- Consistent appearance.
- Faster updates.
- Less duplicated work.
- Easier maintenance.

### 8.2 Component vs. instance

- **Component:** Reusable source element.
- **Instance:** A placed use of that component.

Instances can inherit source changes, subject to overrides and component behavior.

### 8.3 Create a button component

1. Create a button with text and padding.
2. Select its container.
3. Use the editor's component-creation command.
4. Name it Button / Primary.
5. Place instances on Sign In and My Orders.
6. Use an appropriate label for each action.

### 8.4 Variants

Variants group related component states or styles.

A button may have:
- Primary.
- Secondary.
- Disabled.
- Loading.

Variants should represent meaningful alternatives of the same component, not unrelated objects.

### 8.5 Why BAs should understand components

A BA may not own the design system, but this knowledge helps when discussing consistency, repeated interface behavior, shared field errors and button states with designers and developers.

## 9. Screen-flow design

A screen flow describes how users move between screens and what conditions cause each transition.

### 9.1 Customer journey

1. Customer opens the portal.
2. Customer enters credentials.
3. Customer selects Sign in.
4. Portal opens My Orders after successful sign-in.
5. Customer selects View details.
6. Portal opens Order Details.
7. Customer selects Track order.
8. Portal displays Tracking Details.
9. Customer returns to My Orders.

### 9.2 Screen-flow diagram

~~~text
[Sign In]
    |
    | Valid credentials
    v
[My Orders] <--------------------------+
    |                                  |
    | Select View details              | Back to orders
    v                                  |
[Order Details]                        |
    |                                  |
    | Select Track order                |
    v                                  |
[Tracking Details] --------------------+

Alternate paths:
[Sign In] -- Invalid credentials --> [Sign In + Error]
[My Orders] -- No orders ----------> [Empty State]
[My Orders] -- Service failure ----> [Error State]
~~~

### 9.3 Questions for the BA

- What is the starting screen?
- What action moves the user forward?
- What conditions must be met?
- What happens when a condition fails?
- Can the user go back?
- Is previous data retained?
- Does the user need permission?
- What happens if a service is unavailable?
- Can the user abandon or restart the flow?

### 9.4 Navigation vs. business logic

A prototype can show that a button navigates to another screen. It does not prove the business rule or authentication works.

Document separately:

| Aspect | Example |
|---|---|
| Interaction | Customer selects Sign in |
| Navigation | My Orders appears after successful authentication |
| Business rule | Only an authenticated customer can access their own orders |
| System behavior | Authentication service validates credentials and establishes a session |

## 10. Build a clickable prototype

### 10.1 Connect screens

1. Open the Desktop Screens page.
2. Select the Sign In frame.
3. Open the Prototype controls.
4. Select the Sign in button or its layer.
5. Create an interaction connection to My Orders.
6. Set a click/tap trigger and a navigate-to action.
7. Connect View details to Order Details.
8. Connect Track order to Tracking Details.
9. Add a Back to orders interaction.
10. Set Sign In as the flow starting point.

The exact control labels may change. The core task is to connect a source element to a destination frame and define its trigger and action.

### 10.2 Interaction concepts

| Concept | Meaning | Example |
|---|---|---|
| Trigger | What starts interaction | Click or tap |
| Action | What happens | Navigate to a frame |
| Destination | Target screen/state | My Orders |
| Transition | How change is presented | Instant, dissolve, slide |
| Overlay | Temporary content above current screen | Confirmation dialog |
| Back | Return to a previous or defined destination | Back to My Orders |
| Starting point | Beginning of a prototype flow | Sign In |

### 10.3 Create an error-state interaction

1. Duplicate the Sign In frame.
2. Name it Sign In — Error.
3. Add a clear message: We couldn't sign you in. Check your details and try again.
4. Add a way to return and retry.
5. Connect a clearly labeled demo interaction to this error frame.

This demonstrates a state only. It does not validate real credentials.

### 10.4 Test the prototype

Use presentation/preview mode:
- Start at Sign In.
- Follow the successful path.
- Open order details and tracking.
- Return to My Orders.
- Try the error path.
- Check that every important button has an intentional result.
- Look for dead ends and missing back navigation.

A control that looks clickable but has no behavior should be connected or clearly marked out of scope.

## 11. Stakeholder review

Ask stakeholders:
- Can you identify each screen's purpose?
- Is the screen order logical?
- Are labels and actions understandable?
- Is required information missing?
- Are there unnecessary steps?
- What happens when data is missing?
- Can users recover from errors?
- Is back navigation clear?
- Are permission and privacy concerns addressed?
- Does the flow match the business process?

Capture feedback:

| ID | Screen | Feedback | Decision | Owner | Status |
|---|---|---|---|---|---|
| FB-01 | Sign In | Add password visibility control | Confirm design/security standard | Designer | Open |
| FB-02 | My Orders | Put status near order number | Accepted | BA | Done |
| FB-03 | Order Details | Add return-to-orders action | Accepted | Designer | Done |
| FB-04 | Tracking | Show delivery estimate only when confirmed | Accepted | Product Owner | Done |

Record whether feedback is accepted, rejected or unresolved. Do not silently change a design when the change affects requirements.

## 12. Independent mini-project: Customer Portal Prototype

### 12.1 Problem statement

Create a clickable prototype for a customer portal. A signed-in customer should be able to view orders, open an order and see tracking details.

**Goal:** Demonstrate the main customer journey and alternate states using Figma.

### 12.2 Required screens

Create these seven frames:

1. 01 — Sign In
2. 02 — Sign In Error
3. 03 — My Orders
4. 04 — My Orders Empty
5. 05 — My Orders Error
6. 06 — Order Details
7. 07 — Tracking Details

A mobile version of the main screens is an optional extension.

### 12.3 Screen requirements

**Screen 1 — Sign In**
- Portal name and page heading.
- Labeled email field.
- Labeled password field.
- Sign in button.
- Forgot password link (destination may be marked out of scope).

**Screen 2 — Sign In Error**
- Same form structure.
- Clear error message.
- User can correct information and try again.
- State that no real credential validation occurs.

**Screen 3 — My Orders**
- Page title.
- Search order number field and action.
- Order list with number, date, status and delivery estimate when available.
- View Details action.
- Support link/action.

**Screen 4 — My Orders Empty**
- Explain that no orders are available.
- Provide a useful next step if in scope.

**Screen 5 — My Orders Error**
- Explain that orders could not be loaded.
- Provide a retry action.
- Do not expose technical error details.

**Screen 6 — Order Details**
- Order number and date.
- Item summary with synthetic sample content.
- Current status.
- Delivery estimate only if confirmed.
- Track order and Back to orders actions.

**Screen 7 — Tracking Details**
- Order reference.
- Current delivery status.
- Progress steps such as Confirmed, Packed, Shipped, Out for delivery and Delivered.
- Show dates only when known sample values exist.
- Back to order details action.

### 12.4 Sample data

Use synthetic values:

| Order | Date | Status | Delivery estimate |
|---|---|---|---|
| ORD-1042 | 12 May 2026 | In transit | 16 May 2026 |
| ORD-1038 | 08 May 2026 | Delivered | 11 May 2026 |
| ORD-1029 | 02 May 2026 | Processing | Not confirmed |

These values are for the exercise only, not live order data.

### 12.5 Required interactions

| From | User action | To |
|---|---|---|
| Sign In | Demonstration successful sign-in | My Orders |
| Sign In | Demo invalid sign-in | Sign In Error |
| Sign In Error | Try again | Sign In |
| My Orders | View Details for ORD-1042 | Order Details |
| My Orders | Demo no orders | My Orders Empty |
| My Orders | Demo service failure | My Orders Error |
| My Orders Error | Retry | My Orders |
| Order Details | Track order | Tracking Details |
| Order Details | Back to orders | My Orders |
| Tracking Details | Back | Order Details |

Alternate-state links may be placed in a clearly labeled demo-only area so reviewers can inspect each state. Do not confuse them with real production features.

### 12.6 Project evidence structure

~~~text
Day_35_Customer_Portal_Prototype/
├── README.md
├── screen_inventory.md
├── screen_flow.png
├── prototype_screenshots/
│   ├── 01_sign_in.png
│   ├── 02_sign_in_error.png
│   ├── 03_my_orders.png
│   ├── 04_empty_state.png
│   ├── 05_error_state.png
│   ├── 06_order_details.png
│   └── 07_tracking_details.png
├── interaction_map.md
└── stakeholder_feedback.md
~~~

The Figma design file and share link are the primary prototype deliverables. This folder stores supporting evidence.

### 12.7 Screen inventory template

Save as screen_inventory.md:

~~~markdown
# Customer Portal — Screen Inventory

| Screen ID | Screen name | User goal | Entry point | Main actions | Alternate states |
|---|---|---|---|---|---|
| SCR-01 | Sign In | Access portal | Portal URL | Sign in | Invalid credentials |
| SCR-02 | Sign In Error | Correct sign-in information | Sign In | Try again | Repeated failure |
| SCR-03 | My Orders | View recent orders | Successful sign in | Search, view details | Empty, service error |
| SCR-04 | My Orders Empty | Understand no orders exist | My Orders | Follow next step | N/A |
| SCR-05 | My Orders Error | Recover from load failure | My Orders | Retry | Repeated failure |
| SCR-06 | Order Details | Understand selected order | View Details | Track, go back | Missing estimate |
| SCR-07 | Tracking Details | Understand delivery progress | Track order | Back | Delayed/unknown status |
~~~

### 12.8 Interaction map template

Save as interaction_map.md:

~~~markdown
# Customer Portal — Interaction Map

| Source | Element | Trigger | Action | Destination | Note |
|---|---|---|---|---|---|
| Sign In | Sign in | Click | Navigate | My Orders | Demo only |
| Sign In | Demo invalid sign-in | Click | Navigate | Sign In Error | No credential check |
| Sign In Error | Try again | Click | Navigate | Sign In | Retry |
| My Orders | View Details | Click | Navigate | Order Details | Selected order |
| Order Details | Track order | Click | Navigate | Tracking Details | Tracking view |
| Order Details | Back to orders | Click | Navigate | My Orders | Return to list |
| Tracking Details | Back | Click | Navigate | Order Details | Return to order |
~~~

Add the empty and service-error paths.

### 12.9 README template

~~~markdown
# Customer Portal Prototype — Day 35

## Objective
Demonstrate the customer journey from sign-in to order tracking.

## Figma file
Paste your Figma file link here.

## Prototype starting point
Sign In.

## Screens included
List the seven screens and their purpose.

## Main flow
Sign In → My Orders → Order Details → Tracking Details.

## Alternate paths
Invalid sign-in, empty orders and order-service failure.

## Prototype limitations
This is a clickable design prototype. It does not authenticate users,
retrieve live orders, call APIs or update a database.

## Review feedback
Summarize feedback, decisions and unresolved questions.
~~~

### 12.10 Expected result

A reviewer should be able to:
- Start at Sign In.
- Follow the demonstration successful path.
- View the order list.
- Open an order.
- View tracking progress.
- Navigate back.
- Inspect invalid sign-in, empty and service-error states.
- Understand which interactions are illustrative, not functional.

### 12.11 Quality checklist

- [ ] File and pages have clear names.
- [ ] All seven required screens exist.
- [ ] Text and controls are readable.
- [ ] Fields have visible labels.
- [ ] Primary actions are easy to identify.
- [ ] Main successful path is connected.
- [ ] Alternate paths are connected.
- [ ] Back navigation works.
- [ ] No important button is a dead end.
- [ ] Sample data is synthetic.
- [ ] Prototype limitations are documented.
- [ ] Screen inventory is complete.
- [ ] Interaction map is complete.
- [ ] Feedback and open questions are recorded.
- [ ] Prototype starts at the correct screen.

### 12.12 Common mistakes

| Mistake | Why it matters | Better approach |
|---|---|---|
| Screens without a user journey | No coherent experience | Draw the flow before connecting screens |
| Wrong button connection | Misleading behavior | Test every interaction |
| Missing alternate states | Only ideal journey is visible | Include error and empty paths |
| Treating prototype as a working app | Creates false expectations | Document simulated behavior |
| Inconsistent button styles | Reduces clarity | Reuse components |
| Unclear layer names | Collaboration is difficult | Use meaningful names |
| Over-designing too early | Wastes effort before flow is validated | Start simple, refine after feedback |
| No back navigation | User reaches a dead end | Define a return path |
| Real customer data | Privacy risk | Use synthetic data |
| Unrecorded feedback | Decisions are lost | Maintain a feedback log |

### 12.13 Stuck ladder

1. Create the seven frames first; do not connect them yet.
2. Add headings, labels, sample information and primary actions.
3. Sketch the flow using the interaction table.
4. Connect Sign In → My Orders → Order Details → Tracking Details.
5. Test that path in presentation mode.
6. Add error and empty-state paths.
7. Use the quality checklist to find missing connections.

## 13. BA responsibilities when using prototypes

A BA should:
- Keep the prototype aligned with approved requirements.
- Identify assumptions and sample content.
- Make alternate paths visible.
- Record stakeholder feedback.
- Update requirements when design decisions change behavior.
- Coordinate with UX designers, developers and testers.
- Avoid promising functionality the prototype does not demonstrate.
- Maintain traceability between requirements, screens and interactions.

A designer may own visual design decisions. The BA helps ensure the proposed experience addresses business and user requirements. Responsibilities vary by organization.

## 14. Daily quiz

**Q1. What is a Figma frame commonly used to represent?**

A. A database table  
B. A screen or design container  
C. A production API  
D. A user password  

**Q2. What is a component?**

A. A reusable design element  
B. A completed backend service  
C. A stakeholder meeting  
D. A database record  

**Q3. What does a prototype connection define?**

A. A database schema  
B. A source interaction and its destination/action  
C. A deployment pipeline  
D. A real authentication result  

**Q4. What is the purpose of Auto Layout?**

A. Execute business logic  
B. Arrange content and help layouts adapt to content  
C. Connect a database  
D. Write user stories automatically  

**Q5. Which statement about a clickable prototype is correct?**

A. It always connects to live APIs  
B. It is the same as a deployed application  
C. It can simulate navigation without implementing backend behavior  
D. It proves security controls work  

### Answers and explanations

1. **B.** A frame can represent a screen or contain a group of design elements.
2. **A.** Components are reusable elements that support consistency.
3. **B.** Prototype interactions define a trigger and what happens next.
4. **B.** Auto Layout arranges elements and responds to content changes.
5. **C.** A prototype can demonstrate an experience without real services or business logic.

## 15. Interview preparation

### Question 1: How can a Business Analyst use Figma?

**Answer:** A BA can use Figma to create or review wireframes, communicate screen requirements, connect screens into a clickable prototype and validate user journeys with stakeholders before development. The BA should keep the prototype aligned with requirements and document assumptions and feedback.

### Question 2: What is the difference between a frame and a component?

**Answer:** A frame is a container that can represent a screen or group of elements. A component is a reusable design element, such as a button or input field, that can be placed as instances on different screens.

### Question 3: What is a screen flow?

**Answer:** A screen flow describes how a user moves between screens, including actions and conditions that cause navigation. It should cover the main path and alternate paths such as validation errors and empty states.

### Question 4: What is Auto Layout?

**Answer:** Auto Layout arranges items inside a container using direction, spacing, padding and alignment. It helps layouts adapt when content changes, such as a button label becoming longer.

### Question 5: How do you validate a prototype with stakeholders?

**Answer:** I give stakeholders a realistic task, ask them to follow the prototype without guidance and observe where they hesitate or become confused. I record feedback, clarify requirements, agree decisions with relevant owners and update the prototype and documentation.

## 16. Revision sheet

- **Figma:** Collaborative interface design and prototyping tool.
- **Frame:** Container commonly used to represent a screen.
- **Layer:** Individual object in a design.
- **Component:** Reusable design element.
- **Instance:** Placed use of a component.
- **Variant:** Related version or state of a component.
- **Auto Layout:** Arranges elements with spacing, padding and alignment.
- **Prototype:** Simulated user journey or interaction.
- **Trigger:** Event that starts an interaction.
- **Destination:** Screen or state reached by the interaction.
- **Overlay:** Temporary layer above a screen.
- **Screen flow:** Sequence of screens and transitions.
- **BA focus:** Ensure the journey meets requirements, alternate paths are covered and feedback is traceable.
- **Critical limitation:** A clickable prototype does not prove backend, API, authentication or database functionality.

## 17. Completion checklist

### Concepts
- [ ] I understand files, pages, frames and layers.
- [ ] I can create and rename a frame.
- [ ] I can add and align shapes and text.
- [ ] I understand Auto Layout basics.
- [ ] I understand components, instances and variants.
- [ ] I understand prototype triggers and navigation.

### Practical work
- [ ] I created the Customer Portal Prototype file.
- [ ] I created all seven required screens.
- [ ] I connected the main customer journey.
- [ ] I connected invalid sign-in, empty and error paths.
- [ ] I tested the flow in presentation mode.
- [ ] I checked back navigation and dead ends.
- [ ] I completed the screen inventory and interaction map.

### BA communication
- [ ] I labeled synthetic data and assumptions.
- [ ] I documented prototype limitations.
- [ ] I captured stakeholder feedback.
- [ ] I can explain how screens map to requirements.
- [ ] I completed the quiz and interview practice.

**Day 35 is complete when a reviewer can start at Sign In, follow the customer journey, inspect alternate states and understand the prototype's limitations without your explanation.**

## 18. References

- Figma — Official product: https://www.figma.com/
- Figma Help Center — Design and prototyping: https://help.figma.com/
- Figma Learn — Learning resources: https://www.figma.com/resource-library/
- Nielsen Norman Group — UX research and usability: https://www.nngroup.com/
- W3C Web Accessibility Initiative: https://www.w3.org/WAI/
- GOV.UK Design System — Components and interaction patterns: https://design-system.service.gov.uk/

---

**Roadmap alignment:** Day 35 follows the approved topic “Figma fundamentals and screen-flow design” and uses the exact approved mini-project title “Customer Portal Prototype”.
