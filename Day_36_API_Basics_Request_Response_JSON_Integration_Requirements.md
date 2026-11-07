# Day 36: API Basics, Request/Response, JSON and Integration Requirements

## Learning outcomes

By the end of this lesson, you should be able to:

- Explain what an API is and how two software systems communicate.
- Read an endpoint and identify its HTTP method, path, parameters, headers and body.
- Understand the request/response lifecycle and common HTTP status codes.
- Read, write and validate JSON.
- Describe authentication, authorization, pagination, filtering, rate limits and error handling.
- Gather business and integration requirements without making unsupported technical assumptions.
- Prepare an API Requirement Document that developers and testers can use.

## 1. What is an API?

API stands for **Application Programming Interface**. It is a defined way for one software application to request data or an action from another application.

Think of an online shopping application:

1. A customer opens the My Orders screen.
2. The application asks the order service for that customer's orders.
3. The service checks the request and retrieves the relevant data.
4. The service sends a response.
5. The application displays the orders.

The API is the agreed interface used for that communication. It defines what can be requested, what information must be supplied and what response can be expected.

### 1.1 Everyday analogy

A restaurant customer does not enter the kitchen and operate the cooking equipment. The customer gives an order to the waiter. The waiter communicates it to the kitchen and returns the result.

| Restaurant | Software |
|---|---|
| Customer | Client application |
| Menu | API documentation |
| Waiter/order process | API interface |
| Kitchen | Server or service |
| Order details | Request |
| Prepared meal or explanation | Response |

The analogy helps explain the interaction, but an API is a formal technical contract rather than a person.

### 1.2 Important API terms

- **Client:** The application or system making a request.
- **Server:** The system receiving and processing the request.
- **API:** The interface and rules that allow the systems to communicate.
- **Endpoint:** A particular address where an API operation is available.
- **Resource:** The business object being accessed, such as an order, customer or payment.
- **Payload:** Data sent in a request or response, commonly in JSON.
- **API contract:** The agreed methods, fields, formats, rules and responses.

### 1.3 API versus user interface

A user interface is designed for people. An API is designed for software systems.

For example:
- A customer clicks **View Orders** in a web page.
- The web application sends an API request.
- The order service returns order data.
- The web page converts that data into a readable screen.

The API does not normally decide the screen layout. It supplies or processes information according to its contract.

## 2. How an API request works

A typical HTTP API interaction follows this sequence:

1. A user performs an action or a system event occurs.
2. The client prepares a request.
3. The request is sent to an endpoint over a network.
4. The server receives and validates the request.
5. The server checks permissions and processes the operation.
6. The server sends a response with a status code and, where appropriate, a response body.
7. The client interprets the response and updates its behaviour or display.

### Example: viewing an order

The customer opens order ORD-1042.

- Client: Customer portal
- Server: Order service
- Method: GET
- Endpoint: /api/v1/orders/ORD-1042
- Expected outcome: order details are returned if the order exists and the customer is allowed to view it.

A successful response might contain the order ID, status, total and items. If the order does not exist, the service should return an appropriate error response.

## 3. HTTP and REST API fundamentals

HTTP is a protocol used for communication between clients and servers. Many web APIs use HTTP.

REST (Representational State Transfer) is an architectural style commonly used to design web APIs. A REST-style API commonly exposes resources through URLs and uses HTTP methods to describe operations.

Do not assume every API is REST. Other approaches include SOAP, GraphQL, RPC and event-based interfaces.

### 3.1 HTTP methods

| Method | Typical purpose | Example |
|---|---|---|
| GET | Retrieve information | Get order details |
| POST | Create a resource or trigger an operation | Create a support ticket |
| PUT | Replace a resource representation | Replace a customer's saved address |
| PATCH | Partially update a resource | Change an order's delivery note |
| DELETE | Remove a resource | Delete a saved address |

The exact behaviour must be confirmed in the API contract. A method name alone does not explain every business rule.

### 3.2 Safe and idempotent methods

These concepts are important when discussing retries and duplicate operations.

- **Safe:** The intended operation does not change server state. GET is defined as safe.
- **Idempotent:** Repeating the same request has the same intended effect as making it once. GET, PUT and DELETE are generally defined as idempotent by HTTP semantics.
- POST is not automatically idempotent. Repeating a payment or order-creation request may create a duplicate unless the API has a suitable duplicate-prevention mechanism.
- PATCH may or may not be idempotent depending on the operation.

Example: If a client times out after submitting a payment, it may not know whether the payment succeeded. Retrying blindly can create a duplicate charge. The business and technical teams should define how duplicate submissions are prevented and how the client checks the result.

## 4. Understanding an endpoint URL

Consider this fictional endpoint:

~~~text
https://api.example.com/api/v1/orders/ORD-1042?includeItems=true
~~~

| Part | Meaning |
|---|---|
| https | Communication scheme |
| api.example.com | Host or domain |
| /api/v1 | API path and version |
| /orders | Resource collection |
| /ORD-1042 | Specific order identifier |
| includeItems=true | Query parameter |

### 4.1 Path parameters

A path parameter identifies a resource or a part of the resource hierarchy.

Example:

~~~text
GET /api/v1/orders/ORD-1042
~~~

Here, ORD-1042 identifies the order.

### 4.2 Query parameters

Query parameters commonly control filtering, sorting, pagination or optional response details.

Examples:

~~~text
GET /api/v1/orders?status=SHIPPED
GET /api/v1/orders?page=1&pageSize=20
GET /api/v1/orders?sortBy=createdAt&sortOrder=desc
~~~

A Business Analyst should confirm:
- Which filters are supported?
- Can multiple filters be combined?
- What is the default sort order?
- What happens when a page number is invalid?
- What is the maximum page size?
- Are query values case-sensitive?

### 4.3 Headers

Headers carry metadata about a request or response.

Common examples:

~~~text
Accept: application/json
Content-Type: application/json
Authorization: Bearer <access-token>
~~~

- Accept tells the server which response media type the client can handle.
- Content-Type describes the format of the request body.
- Authorization carries credentials or an access token according to the security design.

Never put real passwords, API keys or access tokens into public documentation, screenshots, source control or sample requests. Use clearly fake placeholders.

### 4.4 Request body

A request body contains data sent to the server, often when creating or updating a resource.

Example:

~~~http
POST /api/v1/support-tickets
Content-Type: application/json
~~~

~~~json
{
  "orderId": "ORD-1042",
  "category": "DELIVERY_DELAY",
  "description": "The order has not arrived.",
  "preferredContact": "EMAIL"
}
~~~

The API contract should define which fields are required, their data types, allowed values, length limits and validation rules.

## 5. Request and response structure

### 5.1 Request components

A typical HTTP request may contain:

1. Method — the operation being requested.
2. URL — the target endpoint.
3. Headers — metadata and authentication information.
4. Path/query parameters — resource identifiers or request options.
5. Body — input data, when required.

Not every request has a body. A simple GET request commonly uses path and query parameters instead.

### 5.2 Response components

A typical response contains:

1. Status code — the outcome category and result.
2. Headers — metadata such as content type or caching information.
3. Body — returned data or error details, when appropriate.

Example successful response:

~~~http
HTTP/1.1 200 OK
Content-Type: application/json
~~~

~~~json
{
  "orderId": "ORD-1042",
  "status": "SHIPPED",
  "currency": "INR",
  "totalAmount": 1499.00,
  "estimatedDeliveryDate": "2026-11-10"
}
~~~

The example is illustrative. Actual field names, formats and business rules must be agreed by the API-owning team.

## 6. HTTP status codes

Status codes are grouped by their first digit.

| Range | Category | Meaning |
|---|---|---|
| 1xx | Informational | Request processing information |
| 2xx | Success | Request was successfully received, understood and accepted |
| 3xx | Redirection | Further action is needed to complete the request |
| 4xx | Client error | The request has a problem or cannot be fulfilled as sent |
| 5xx | Server error | The server failed to fulfil an apparently valid request |

### 6.1 Common status codes

| Code | Name | Typical use |
|---|---|---|
| 200 | OK | Successful request |
| 201 | Created | A resource was created |
| 202 | Accepted | Request accepted for asynchronous processing |
| 204 | No Content | Successful operation with no response body |
| 400 | Bad Request | Invalid request syntax or input |
| 401 | Unauthorized | Valid authentication is missing or failed |
| 403 | Forbidden | Authenticated caller is not allowed to perform the operation |
| 404 | Not Found | Resource or endpoint was not found |
| 405 | Method Not Allowed | Method is not supported for that resource |
| 409 | Conflict | Request conflicts with the current resource state |
| 415 | Unsupported Media Type | Request body format is not supported |
| 422 | Unprocessable Content | Request is understood but fails semantic validation |
| 429 | Too Many Requests | Rate limit has been exceeded |
| 500 | Internal Server Error | Unexpected server-side failure |
| 502 | Bad Gateway | Gateway received an invalid response from an upstream server |
| 503 | Service Unavailable | Service is temporarily unable to handle the request |
| 504 | Gateway Timeout | Gateway did not receive a timely upstream response |

A 401 and 403 are not interchangeable:
- 401: the caller has not successfully authenticated.
- 403: the caller is authenticated but lacks permission for the requested action.

A 404 may also be used to avoid revealing whether a protected resource exists. Confirm the security and product requirements rather than assuming one universal behaviour.

### 6.2 Why status codes matter to a BA

A BA should describe the expected business outcome for each important scenario.

For example:
- Valid order ID and permitted customer: return order details.
- Unknown order ID: return a defined not-found response.
- Missing authentication: return an authentication error.
- Customer attempts to view another customer's order: enforce access rules and return the agreed denial behaviour.
- Service temporarily unavailable: show a safe message and define whether the client can retry.

Do not write only "API should return an error." Specify the condition, expected status, response structure and user/system behaviour.

## 7. JSON fundamentals

JSON stands for JavaScript Object Notation. It is a lightweight text format commonly used to exchange structured data.

JSON is language-independent. Java, Python, JavaScript and many other languages can read and generate JSON.

### 7.1 JSON data types

JSON supports these value types:

| Type | Example |
|---|---|
| String | "Karthik" |
| Number | 1499 or 1499.50 |
| Boolean | true or false |
| Object | { "city": "Hyderabad" } |
| Array | ["NEW", "SHIPPED"] |
| Null | null |

Important:
- JSON strings use double quotation marks.
- Property names must be double-quoted strings.
- JSON does not support comments.
- JSON does not support trailing commas.
- JSON has no separate date or currency data type. Those are usually represented as strings or numbers under an agreed convention.

### 7.2 JSON object

An object stores related properties as name-value pairs.

~~~json
{
  "customerId": "CUS-1001",
  "name": "Asha",
  "active": true
}
~~~

### 7.3 JSON array

An array stores an ordered list of values.

~~~json
{
  "orderId": "ORD-1042",
  "items": [
    {
      "productId": "P-101",
      "quantity": 2
    },
    {
      "productId": "P-205",
      "quantity": 1
    }
  ]
}
~~~

The items property contains an array of objects.

### 7.4 Nested JSON

Objects and arrays can be nested to represent relationships.

~~~json
{
  "orderId": "ORD-1042",
  "customer": {
    "customerId": "CUS-1001",
    "name": "Asha"
  },
  "delivery": {
    "city": "Hyderabad",
    "postalCode": "500081"
  }
}
~~~

A BA should be able to identify the parent object, nested object, array and individual fields.

### 7.5 Null, missing and empty values

These are not necessarily equivalent:

- Missing property: the property is not included.
- Null: the property is included with no value.
- Empty string: the property exists and contains "".
- Empty array: the property exists and contains [].

Example:

~~~json
{
  "middleName": null,
  "alternatePhone": "",
  "previousAddresses": []
}
~~~

The API contract must define when each representation is used and what it means to the business.

### 7.6 Valid and invalid JSON

Valid:

~~~json
{
  "name": "Asha",
  "age": 25,
  "active": true
}
~~~

Invalid because property names and string values use single quotes:

~~~text
{ 'name': 'Asha' }
~~~

Invalid because there is a trailing comma:

~~~text
{
  "name": "Asha",
}
~~~

Invalid because the value is not quoted as a JSON string and is not a valid JSON literal:

~~~text
{
  "status": SHIPPED
}
~~~

Correct:

~~~json
{
  "status": "SHIPPED"
}
~~~

### 7.7 Dates, times and currency

Agree formats explicitly.

Examples:

~~~json
{
  "createdAt": "2026-11-07T10:30:00Z",
  "deliveryDate": "2026-11-10",
  "currency": "INR",
  "amount": 1499.00
}
~~~

Questions to clarify:
- Is the timestamp UTC or local time?
- Does the date include a time zone?
- Is the amount represented in rupees or paise?
- How many decimal places are supported?
- How are rounding and negative amounts handled?

Never assume a numeric amount is self-explanatory without a currency and precision rule.

## 8. Authentication and authorization

These are related but different security concepts.

- **Authentication:** Establishes who or what is making the request.
- **Authorization:** Determines what that authenticated identity is allowed to do.

Example:
A customer signs in successfully. Authentication confirms the customer's identity. Authorization checks whether that customer can view order ORD-1042.

Common API security approaches include:
- API keys, often used to identify or control access for an application.
- Bearer access tokens.
- OAuth 2.0-based authorization flows.
- Mutual TLS in some system-to-system integrations.

A BA does not need to select a security architecture without the technical/security team. The BA should capture:
- Which system or user calls the API?
- Is the API public, partner-only or internal?
- Which roles or systems can access each operation?
- What data is sensitive?
- What happens when a token expires?
- How are credentials provisioned, rotated and revoked?
- Are audit records required?
- Are there privacy, retention or regulatory requirements?

Never record actual credentials in an API requirement document.

## 9. API validation and error handling

Validation checks whether the request satisfies the API's rules.

Examples:
- Required order ID is missing.
- Email address has an invalid format.
- Quantity is zero or negative.
- Status is not one of the permitted values.
- Description exceeds the maximum length.
- Date is earlier than the permitted business date.
- Customer is not permitted to access the requested record.

### 9.1 Field-level validation table

| Field | Type | Required? | Example rule |
|---|---|---|---|
| orderId | String | Yes | Must identify an existing order |
| category | String | Yes | Must match an allowed category |
| description | String | Yes | 10–1000 characters |
| preferredContact | String | No | EMAIL, SMS or PHONE |

The real rules must come from the product owner and system owners.

### 9.2 Error response example

~~~json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "The request contains invalid fields.",
    "details": [
      {
        "field": "description",
        "issue": "Description must contain at least 10 characters."
      }
    ],
    "correlationId": "REQ-EXAMPLE-001"
  }
}
~~~

A good error contract should define:
- Stable machine-readable error code.
- Human-readable but safe message.
- Field-level details where useful.
- Correlation or request ID for support and troubleshooting.
- Whether the client may retry.
- Whether the response can reveal sensitive information.

Do not expose stack traces, passwords, tokens or internal secrets in client-facing errors.

## 10. Pagination, filtering and sorting

An API may return thousands of records. Returning everything in one response can be slow and expensive.

### 10.1 Pagination

Pagination divides a large result set into smaller pages.

Example:

~~~text
GET /api/v1/orders?page=1&pageSize=20
~~~

A possible response:

~~~json
{
  "items": [
    {
      "orderId": "ORD-1042",
      "status": "SHIPPED"
    }
  ],
  "page": 1,
  "pageSize": 20,
  "totalItems": 135,
  "totalPages": 7
}
~~~

This is an illustrative page-number design. Some APIs use cursor-based pagination instead.

BA questions:
- What is the default page size?
- What is the maximum?
- Is page numbering zero-based or one-based?
- What happens when the requested page is beyond the last page?
- Can records change while the user moves between pages?
- Is the API using page numbers or continuation cursors?

### 10.2 Filtering

Filtering returns only records matching specified conditions.

~~~text
GET /api/v1/orders?status=SHIPPED
~~~

Possible combined filters:

~~~text
GET /api/v1/orders?status=SHIPPED&fromDate=2026-11-01&toDate=2026-11-07
~~~

Define supported fields, allowed values, date boundaries and how multiple filters combine.

### 10.3 Sorting

Sorting controls result order.

~~~text
GET /api/v1/orders?sortBy=createdAt&sortOrder=desc
~~~

Define:
- Supported sort fields.
- Ascending and descending values.
- Default sort.
- Tie-breaking behaviour where order must be stable.

## 11. Rate limits, timeouts and retries

### Rate limiting

A rate limit restricts how many requests a client can make during a period.

Example: A partner may be allowed a defined number of requests per minute. The exact limit is a system and commercial requirement, not something a BA should invent.

Clarify:
- Which client or account is limited?
- What is the request limit and time window?
- What response is returned when the limit is exceeded?
- Is a reset time or retry guidance provided?
- Are different limits needed for different endpoints?

### Timeout

A timeout defines how long a client waits before treating a request as taking too long.

Clarify acceptable response time by operation and business impact. A user-facing search and a background bulk export may have different expectations.

### Retry

A retry attempts an operation again after a temporary failure.

Retries should be controlled:
- Do not retry every error automatically.
- Define which failures are retryable.
- Define maximum attempts and delay strategy.
- Avoid retrying non-idempotent operations blindly.
- Use idempotency or duplicate-detection controls where required for operations such as payment or order creation.

## 12. Integration requirements

An integration connects two or more systems so that data or events can move between them.

Example:
A customer portal needs to show delivery updates from a logistics provider.

~~~text
Customer Portal
      |
      | Request order tracking
      v
Order Service
      |
      | Retrieve shipment reference
      v
Logistics Provider API
      |
      | Tracking status and event time
      v
Order Service
      |
      | Normalized tracking information
      v
Customer Portal
~~~

### 12.1 Integration requirement dimensions

A BA should capture the following:

| Dimension | Questions to answer |
|---|---|
| Business purpose | Why is the integration needed? |
| Source system | Which system owns or sends the data? |
| Target system | Which system receives or consumes it? |
| Direction | One-way, two-way or event notification? |
| Trigger | User action, scheduled job or business event? |
| Frequency | Real-time, near-real-time, hourly or daily? |
| Data scope | Which records and fields are exchanged? |
| Mapping | How do source fields map to target fields? |
| Validation | What data must be checked? |
| Security | How are identity, access and sensitive data handled? |
| Failure handling | What happens if the call fails? |
| Reconciliation | How are missing or mismatched records detected? |
| Monitoring | What must be logged, alerted or measured? |
| Ownership | Who supports each system and the integration? |

### 12.2 Synchronous versus asynchronous integration

**Synchronous:** The caller waits for a response during the interaction.

Example: The customer opens an order detail page and the portal requests the latest order information.

**Asynchronous:** The initiating system does not need to wait for the entire process to finish. Work may be handled through a queue, event or background process.

Example: A newly created order triggers a background notification to a fulfilment system.

Business questions:
- Must the user receive an immediate result?
- Can processing take place in the background?
- How will the user or calling system learn that processing completed?
- What happens if the receiving system is unavailable?
- Can messages be delivered more than once?
- How are duplicate events handled?

### 12.3 Field mapping

Field mapping documents how data in one system corresponds to data in another.

| Source field | Target field | Example transformation | Rule |
|---|---|---|---|
| shipment_ref | trackingNumber | Direct mapping | Required |
| delivery_state | trackingStatus | Convert provider value to agreed status | Mapping table required |
| event_time | lastUpdatedAt | Normalize to agreed timestamp format | Time zone must be preserved |
| expected_date | estimatedDeliveryDate | Convert to YYYY-MM-DD | Optional if provider has no estimate |

Do not assume that two fields with similar names have identical meaning. Confirm definition, format, allowed values, ownership and null handling.

### 12.4 Failure scenarios

Plan for more than the successful path.

| Scenario | Requirement to clarify |
|---|---|
| Source system unavailable | Retry policy, fallback and user message |
| Invalid response | Validation, logging and alerting |
| Missing mandatory field | Reject, quarantine or apply an approved fallback |
| Duplicate event | Detect and prevent duplicate business action |
| Delayed update | Display last-updated time and define freshness target |
| Data mismatch | Reconciliation and ownership for correction |
| Authentication expires | Token renewal or controlled failure |
| Partial processing | Track completed and failed records |

## 13. API documentation and tools

### 13.1 API documentation

API documentation explains how an API can be used. It commonly includes:
- Endpoint and HTTP method.
- Purpose and business description.
- Parameters and headers.
- Request schema and examples.
- Response schema and examples.
- Status codes and error models.
- Authentication requirements.
- Rate limits and operational notes.

### 13.2 OpenAPI and Swagger

**OpenAPI** is a specification for describing HTTP APIs in a machine-readable format.

**Swagger** is a family of tools commonly used to work with OpenAPI descriptions, including tools for viewing documentation and trying API requests.

A BA may review an OpenAPI document to understand:
- Available endpoints.
- Request and response fields.
- Required versus optional fields.
- Data types and allowed values.
- Error responses.
- Authentication schemes.

A BA should compare the documented API contract with approved business requirements and raise gaps. The BA does not need to author the full technical specification unless that is part of the role.

### 13.3 API testing tools

Tools such as Postman can help teams send requests and inspect responses.

A BA can use an approved test environment to:
1. Select the HTTP method.
2. Enter the endpoint.
3. Add required headers and parameters.
4. Supply a sample request body.
5. Send the request.
6. Inspect status code, response headers and response body.
7. Compare the observed behaviour with the approved requirement.

Use only authorized environments and test data. Never test against production or use real customer information without explicit authorization.

## 14. API contracts, versioning and backward compatibility

An API contract is an agreement between the API provider and its consumers.

It should define:
- Operations and endpoint paths.
- Request and response schemas.
- Required and optional fields.
- Data types and formats.
- Validation rules.
- Error responses.
- Security and permission rules.
- Operational expectations.

### 14.1 Versioning

An API may include a version in its path:

~~~text
/api/v1/orders
/api/v2/orders
~~~

Versioning helps teams introduce changes while managing existing consumers.

### 14.2 Breaking and non-breaking changes

Potentially breaking changes:
- Removing a field consumers rely on.
- Renaming a field.
- Changing a field's data type.
- Making an optional field mandatory.
- Changing the meaning of an existing status value.
- Changing authentication requirements without a migration plan.

Potentially non-breaking changes may include adding an optional response field, but even additive changes can affect poorly designed consumers. The API owner must assess compatibility.

BA responsibilities:
- Identify affected consumers and stakeholders.
- Document the business reason for the change.
- Confirm migration and support timelines.
- Capture old and new behaviour.
- Define acceptance criteria.
- Ensure communication and sign-off.

## 15. The Business Analyst's role in API work

A BA connects business needs with technical implementation. The BA should not invent endpoint designs or security decisions, but should make the required business behaviour precise.

### 15.1 Requirement discovery

Ask:
- What business problem does this integration solve?
- Which user or system needs the capability?
- What starts the interaction?
- What information is needed?
- Which system is the source of truth for each field?
- What should happen when data is missing or invalid?
- How quickly must the information be available?
- What permissions apply?
- What happens during an outage?
- How will the business confirm the integration works?

### 15.2 Convert a business need into requirements

Business statement:

"Customers should be able to view the latest delivery status for their orders."

Clarified requirements:
1. An authenticated customer can request tracking information for an order they are permitted to access.
2. The system retrieves the shipment reference associated with the order.
3. The integration retrieves the latest available tracking status from the logistics provider.
4. The portal displays the status and the time it was last updated.
5. If no tracking information is available, the portal displays an approved explanatory message.
6. If the provider is temporarily unavailable, the system follows the agreed fallback and retry behaviour.
7. A customer cannot access another customer's tracking information.

### 15.3 Functional and non-functional requirements

**Functional requirements** describe what the system must do:
- Retrieve an order's tracking information.
- Validate that the customer can access the order.
- Map provider statuses to portal statuses.
- Display the last update time.

**Non-functional requirements (NFRs)** describe quality or operating expectations:
- Performance: response time target.
- Availability: service availability target.
- Security: authentication, authorization and data protection.
- Reliability: recovery and retry behaviour.
- Scalability: expected request volume.
- Observability: logging, monitoring and traceability.
- Privacy: permitted use and retention of personal data.

Targets such as response time, availability and volume must be agreed with stakeholders and technical owners. Do not invent them.

### 15.4 Acceptance criteria

Good acceptance criteria describe observable outcomes.

Example:

**Given** an authenticated customer is viewing an order they are authorized to access,

**When** the customer opens the tracking details and tracking data is available,

**Then** the portal displays the mapped tracking status and last-updated timestamp.

Additional scenarios:
- The order has no shipment reference.
- The provider returns an unknown status.
- The provider times out.
- The customer is not authorized to view the order.
- The provider returns an empty tracking history.
- A duplicate tracking event is received.

## 16. Practical example: customer order tracking API

The following endpoints are fictional examples for learning. They are not real services.

### 16.1 Endpoint inventory

| ID | Method | Endpoint | Business purpose |
|---|---|---|---|
| API-01 | GET | /api/v1/orders | List orders available to the authenticated customer |
| API-02 | GET | /api/v1/orders/{orderId} | Retrieve one order |
| API-03 | GET | /api/v1/orders/{orderId}/tracking | Retrieve tracking details |
| API-04 | POST | /api/v1/support-tickets | Submit a support request |

### 16.2 Example API-03 request

~~~http
GET /api/v1/orders/ORD-1042/tracking
Accept: application/json
Authorization: Bearer <access-token>
~~~

### 16.3 Example successful response

~~~json
{
  "orderId": "ORD-1042",
  "trackingNumber": "TRK-55021",
  "status": "IN_TRANSIT",
  "lastUpdatedAt": "2026-11-07T10:30:00Z",
  "estimatedDeliveryDate": "2026-11-10",
  "events": [
    {
      "eventCode": "PICKED_UP",
      "description": "Shipment picked up",
      "eventTime": "2026-11-06T08:00:00Z",
      "location": "Hyderabad"
    },
    {
      "eventCode": "IN_TRANSIT",
      "description": "Shipment is moving",
      "eventTime": "2026-11-07T10:30:00Z",
      "location": "Vijayawada"
    }
  ]
}
~~~

### 16.4 Example support-ticket request

~~~http
POST /api/v1/support-tickets
Content-Type: application/json
Authorization: Bearer <access-token>
~~~

~~~json
{
  "orderId": "ORD-1042",
  "category": "DELIVERY_DELAY",
  "description": "The delivery is later than the estimated date.",
  "preferredContact": "EMAIL"
}
~~~

A successful creation might return 201 Created and a ticket identifier. The exact response contract must be agreed.

### 16.5 Questions a BA should ask about this example

- Does the customer see only their own orders?
- Can an order have multiple shipments?
- What is the source of the estimated delivery date?
- How frequently is tracking refreshed?
- Which provider statuses map to the portal's statuses?
- What should be shown if the provider has no events?
- Is tracking history sorted oldest-first or newest-first?
- How long is tracking data retained?
- What happens if a support ticket is submitted twice?
- Which fields are mandatory for each ticket category?

## 17. Mini-project: API Requirement Document

<badge color="success">Day 36 practical project</badge>

### Project objective

Create an API Requirement Document for a customer portal that displays order and delivery tracking information and allows a customer to raise a support ticket.

The document should be clear enough for product owners, developers, testers, integration teams and business stakeholders to review.

### 17.1 Document structure

Use this template:

~~~text
API REQUIREMENT DOCUMENT

1. Document information
   - Project name
   - Document owner
   - Version
   - Date
   - Reviewers and approvers

2. Business background
   - Current problem
   - Business objective
   - Expected benefit
   - Scope and out of scope

3. Stakeholders and systems
   - Business owner
   - Customer portal owner
   - Order service owner
   - Logistics provider
   - Support team

4. Integration overview
   - Source system
   - Target system
   - Direction of data
   - Trigger
   - Frequency
   - Synchronous or asynchronous behaviour

5. API endpoint inventory
   - API ID
   - Method
   - Endpoint
   - Purpose
   - Consumer
   - Priority

6. Request requirements
   - Path parameters
   - Query parameters
   - Headers
   - Request body
   - Required fields
   - Validation rules

7. Response requirements
   - Success status
   - Response fields
   - Data types
   - Error status codes
   - Error response structure

8. Data mapping
   - Source field
   - Target field
   - Definition
   - Data type
   - Transformation
   - Required/optional
   - Validation

9. Business rules
   - Customer access
   - Order eligibility
   - Status mapping
   - Missing data behaviour
   - Duplicate request handling

10. Non-functional requirements
    - Performance
    - Availability
    - Security
    - Reliability
    - Monitoring
    - Privacy and retention

11. Failure and exception handling
    - Timeout
    - Provider unavailable
    - Invalid response
    - Retry
    - Reconciliation
    - Support escalation

12. Acceptance criteria and test scenarios

13. Assumptions, dependencies and constraints

14. Open questions and decisions

15. Approval and sign-off
~~~

### 17.2 Sample endpoint requirement

| Attribute | Requirement |
|---|---|
| API ID | API-03 |
| Name | Retrieve Order Tracking |
| Method | GET |
| Endpoint | /api/v1/orders/{orderId}/tracking |
| Consumer | Customer portal |
| Purpose | Display latest tracking information for an authorized order |
| Path parameter | orderId — required string |
| Authentication | Authenticated customer |
| Success | 200 OK when tracking details are available |
| Not found | Agreed not-found response when the order or tracking record cannot be found |
| Authorization | Customer may access only permitted orders |
| Empty tracking | Return the agreed empty-state response |
| Provider failure | Follow approved timeout, retry and fallback rules |

### 17.3 Sample field dictionary

| Field | Type | Required? | Meaning / rule |
|---|---|---|---|
| orderId | String | Yes | Unique order identifier |
| trackingNumber | String | Conditional | Shipment reference, if assigned |
| status | String | Yes when tracking exists | Value from approved status mapping |
| lastUpdatedAt | String/date-time | Yes when tracking exists | Timestamp of latest update |
| estimatedDeliveryDate | String/date | Optional | Provider's current estimate |
| events | Array | Yes | Tracking events; may be empty |

### 17.4 Sample status mapping

| Provider status | Portal status | Business display |
|---|---|---|
| LABEL_CREATED | LABEL_CREATED | Shipment information received |
| PICKED_UP | IN_TRANSIT | Picked up |
| IN_TRANSIT | IN_TRANSIT | In transit |
| OUT_FOR_DELIVERY | OUT_FOR_DELIVERY | Out for delivery |
| DELIVERED | DELIVERED | Delivered |
| DELIVERY_FAILED | DELIVERY_ATTEMPT_FAILED | Delivery attempt failed |

This is a sample mapping only. Confirm actual provider values and business-approved labels before implementation. Define how unknown future values are handled.

### 17.5 Sample acceptance criteria

1. Given a customer is authenticated and authorized to view an order, when tracking data exists, then the portal displays the current mapped status.
2. Given tracking events exist, when the customer opens tracking details, then events are displayed in the agreed chronological order.
3. Given no tracking reference exists, when the customer opens tracking details, then the portal displays the approved not-yet-available message.
4. Given a customer requests an order they cannot access, when the API receives the request, then access is denied according to the agreed security behaviour.
5. Given the logistics provider is unavailable, when the integration cannot retrieve fresh data, then the system follows the agreed fallback and records sufficient diagnostic information.
6. Given the provider returns an unknown status, when the response is processed, then the system does not display a misleading status and follows the agreed exception process.

### 17.6 Review checklist

- [ ] Business objective and scope are clear.
- [ ] All involved systems and owners are identified.
- [ ] Every endpoint has a defined business purpose.
- [ ] Request fields, types and required status are documented.
- [ ] Response fields and status codes are documented.
- [ ] JSON examples are valid and use synthetic data.
- [ ] Source-to-target field mappings are reviewed.
- [ ] Authentication and authorization needs are captured.
- [ ] Empty, invalid, duplicate and failure scenarios are covered.
- [ ] Performance, availability and data freshness targets have owners.
- [ ] Acceptance criteria are testable.
- [ ] Assumptions, dependencies and open questions are visible.
- [ ] Technical and business owners have reviewed the contract.
- [ ] No real credentials or customer secrets appear in the document.

## 18. Common mistakes to avoid

1. Treating an API as a screen or user interface.
2. Assuming every API is REST.
3. Confusing an endpoint with the entire API.
4. Confusing authentication with authorization.
5. Treating 401 and 403 as identical.
6. Assuming every successful request returns 200.
7. Assuming null, missing and empty values mean the same thing.
8. Writing "send customer details" without listing the exact fields and rules.
9. Forgetting error, timeout and duplicate scenarios.
10. Assuming a field's meaning from its name without confirming its definition.
11. Inventing performance or rate-limit targets.
12. Putting real tokens or personal data in examples.
13. Retrying a payment or create operation without considering duplicate processing.
14. Treating an illustrative JSON example as an approved API contract.

## 19. Knowledge check

Try answering before reading the explanations.

**Q1. What is an API?**

A. A database table  
B. A defined interface that allows software systems to communicate  
C. A user interface design tool  
D. A programming language

**Answer: B.** An API defines how a client can interact with another system or service.

**Q2. Which HTTP method is commonly used to retrieve an order?**

A. POST  
B. DELETE  
C. GET  
D. PATCH

**Answer: C.** GET is used to retrieve a representation of a resource.

**Q3. What is the main difference between authentication and authorization?**

A. They are identical  
B. Authentication identifies the caller; authorization checks permitted actions  
C. Authorization identifies the caller; authentication checks permissions  
D. Both only validate JSON

**Answer: B.** First establish identity, then determine access rights.

**Q4. Which is a valid JSON value?**

A. 'SHIPPED'  
B. SHIPPED  
C. true  
D. undefined

**Answer: C.** true is a valid JSON boolean. A string would need double quotes: "SHIPPED".

**Q5. Which status code commonly means the caller is authenticated but not allowed to perform an action?**

A. 200  
B. 401  
C. 403  
D. 500

**Answer: C.** 403 Forbidden indicates that the server refuses the requested operation.

**Q6. Why is blindly retrying a payment-creation request risky?**

A. JSON cannot be repeated  
B. It may create a duplicate payment  
C. GET will be called instead  
D. It changes the API version

**Answer: B.** The first request may have succeeded even if the response was lost. Duplicate prevention must be designed.

**Q7. What does pagination help with?**

A. Encrypting a password  
B. Dividing a large result set into manageable pages  
C. Changing a JSON string into a number  
D. Authenticating a user

**Answer: B.** Pagination limits how many records are returned at one time.

**Q8. What is field mapping?**

A. Assigning colours to a dashboard  
B. Defining how a source field corresponds to a target field  
C. Creating a user password  
D. Deleting duplicate endpoints

**Answer: B.** Field mapping specifies correspondence, transformations and validation between systems.

**Q9. What should a BA do if the logistics provider's status values are not understood?**

A. Guess the meanings  
B. Ignore the field  
C. Ask the provider/system owner for definitions and agree a mapping  
D. Change the values in production

**Answer: C.** The business meaning and mapping must be confirmed with the responsible owners.

**Q10. Which document describes endpoint methods, parameters, schemas and responses in a standard machine-readable format?**

A. OpenAPI description  
B. Meeting agenda  
C. Employee attendance sheet  
D. Wireframe

**Answer: A.** OpenAPI describes HTTP APIs in a machine-readable form.

## 20. Business Analyst interview questions and sample answers

### 1. What is an API?

An API is a defined interface that allows two software systems to communicate. For example, a customer portal can call an order API to retrieve a customer's order details. The API contract defines the request, response, fields, rules and possible errors.

### 2. What is the difference between GET and POST?

GET is commonly used to retrieve information. POST is commonly used to create a resource or trigger an operation. POST requests may change system state, so duplicate handling and validation are important.

### 3. What is JSON?

JSON is a text-based data interchange format. It represents data using objects, arrays, strings, numbers, booleans and null. APIs commonly use JSON to exchange structured request and response data.

### 4. What is the difference between 401 and 403?

401 means the request has not been successfully authenticated. 403 means the caller is authenticated but is not permitted to perform the requested action. The exact security behaviour should be documented by the API owner.

### 5. What information would you gather for a system integration?

I would identify the business objective, source and target systems, data direction, trigger, frequency, fields, mappings, validation rules, security, expected response time, error handling, retries, monitoring, ownership and acceptance criteria. I would also document assumptions and dependencies.

### 6. How would you document an API requirement?

I would document the business purpose, consumer, endpoint and method where known, request and response fields, data types, required fields, validation rules, status and error scenarios, security requirements, integration behaviour, non-functional expectations and testable acceptance criteria. I would review technical details with the API owner.

### 7. What would you do if an API returns incomplete data?

I would identify which fields are missing, whether they are mandatory, which system owns them and whether the issue is caused by source data, mapping or API behaviour. I would document the expected handling, discuss it with the system owners and add test scenarios for missing and partial data.

## 21. Quick revision sheet

| Term | Remember |
|---|---|
| API | Defined interface for software communication |
| Endpoint | Address for a specific API operation |
| Client | System that sends a request |
| Server | System that processes a request |
| GET | Retrieve |
| POST | Create or trigger |
| PUT | Replace |
| PATCH | Partially update |
| DELETE | Delete |
| Header | Request/response metadata |
| Path parameter | Identifies a resource in the path |
| Query parameter | Filters or controls a request |
| JSON | Structured data interchange format |
| 2xx | Success |
| 4xx | Client/request-side problem |
| 5xx | Server-side failure |
| Authentication | Who are you? |
| Authorization | What may you do? |
| Pagination | Split results into pages |
| Rate limit | Restrict request frequency |
| Field mapping | Source-to-target data correspondence |
| OpenAPI | Machine-readable HTTP API description |
| API contract | Agreed request, response and behaviour |

### Five questions to ask whenever an API is discussed

1. What business action or outcome does this API support?
2. What exact information goes in and comes out?
3. What happens when the request is invalid or the service fails?
4. Who is allowed to use it, and how is data protected?
5. How will the business and testing teams prove it works?

## 22. Day 36 completion checklist

- [ ] I can explain an API using a practical example.
- [ ] I can identify client, server, resource and endpoint.
- [ ] I can distinguish GET, POST, PUT, PATCH and DELETE.
- [ ] I can identify URL path and query parameters.
- [ ] I understand headers, request bodies and response bodies.
- [ ] I can explain common HTTP status codes.
- [ ] I can read JSON objects, arrays and nested fields.
- [ ] I understand missing, null and empty values.
- [ ] I can distinguish authentication from authorization.
- [ ] I understand validation, pagination, filtering and sorting.
- [ ] I can describe timeout, retry and duplicate-request risks.
- [ ] I can identify integration source, target, trigger and frequency.
- [ ] I can prepare a field-mapping table.
- [ ] I can write testable API acceptance criteria.
- [ ] I have drafted the API Requirement Document mini-project.

## 23. Official learning references

Use these references to deepen your understanding:

- MDN — HTTP overview: https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview
- MDN — HTTP request methods: https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods
- MDN — HTTP response status codes: https://developer.mozilla.org/en-US/docs/Web/HTTP/Status
- MDN — JSON: https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/JSON
- JSON official website: https://www.json.org/json-en.html
- OpenAPI Specification: https://spec.openapis.org/oas/latest.html
- Swagger documentation: https://swagger.io/docs/
- Postman Learning Center: https://learning.postman.com/

---

**Day 36 outcome:** You can now read basic API requests and responses, understand JSON, identify integration questions and prepare a business-focused API Requirement Document. The next lesson covers software testing fundamentals and the Business Analyst's role in User Acceptance Testing (UAT).
