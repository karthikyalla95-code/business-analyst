# TechPhile.ai — Business Analyst Career Pathway

# Day 24: SQL Joins, Subqueries and Practical Business Questions

**Phase:** 4 — Data Analysis for Business Decisions  
**Estimated learning time:** 2–3 hours  
**Difficulty:** Beginner to Intermediate  
**Prerequisites:** Day 19 requirements documentation; basic computer and spreadsheet familiarity.

## Learning objectives
1. Explain why relational tables are joined.
2. Use INNER JOIN and LEFT JOIN correctly.
3. Understand one-to-many relationships and duplicate row effects.
4. Write subqueries for filtering and comparison.
5. Use table aliases and qualified column names.
6. Translate a business question into a query and validate its result.

## 1. Why this matters
Customer details may be stored separately from orders, and order items may be stored separately from order headers. A manager asks, “Which customers have never ordered?” or “What is the average order value by customer city?” You need to connect related tables without accidentally multiplying totals.

## 2. Table relationships
Example:
- customers: one row per customer.
- orders: one row per order; customer_id points to customers.
- order_items: one row per product line in an order.

A customer can have many orders. An order can have many order-item rows. This is a one-to-many relationship.

Keys:
- Primary key: uniquely identifies a row.
- Foreign key: references a key in another table.
- Join key: column(s) used to match records.

## 3. INNER JOIN
Returns rows with matching keys in both tables.

```sql
SELECT c.customer_id, c.customer_name, o.order_id, o.total_amount
FROM customers AS c
INNER JOIN orders AS o
  ON c.customer_id = o.customer_id;
```

Aliases c and o make queries shorter. Qualify fields such as customer_id because both tables may contain that name.

Use INNER JOIN when you only want customers with matching orders.

## 4. LEFT JOIN
Returns every row from the left table and matching rows from the right table; unmatched right-side fields are NULL.

```sql
SELECT c.customer_id, c.customer_name, o.order_id
FROM customers AS c
LEFT JOIN orders AS o
  ON c.customer_id = o.customer_id;
```

Find customers with no orders:
```sql
SELECT c.customer_id, c.customer_name
FROM customers AS c
LEFT JOIN orders AS o
  ON c.customer_id = o.customer_id
WHERE o.order_id IS NULL;
```

Do not move a right-table filter into WHERE without thinking. For example, WHERE o.status='Delivered' removes NULL rows and can make a LEFT JOIN behave like an INNER JOIN. If you want to retain every customer but match only delivered orders, put the status condition in the ON clause.

## 5. Other join types
- RIGHT JOIN: preserves every row from the right table; often rewritten as LEFT JOIN by swapping table order.
- FULL OUTER JOIN: keeps unmatched rows from both sides; not supported in every database.
- CROSS JOIN: creates every possible pair; row count can grow dramatically.
- SELF JOIN: joins a table to itself, for example employee to manager.

Learn INNER and LEFT JOIN thoroughly first; they cover many BA analysis tasks.

## 6. Join cardinality and duplicate totals
Suppose one order has three order_items. Joining orders to order_items creates three rows for that order. If you then SUM orders.total_amount, the order total may be counted three times.

Before joining, ask:
- What does one row represent in each table?
- Is the relationship one-to-one, one-to-many or many-to-many?
- Which table contains the measure at the grain I need?
- Should I aggregate order items before joining to order-level data?

Example: To calculate order revenue from line items, sum quantity × unit_price at the item grain. Do not repeat the order header total across every item row and sum it.

## 7. Subqueries
A subquery is a query nested inside another query.

Orders above average order value:
```sql
SELECT order_id, total_amount
FROM orders
WHERE total_amount > (
  SELECT AVG(total_amount)
  FROM orders
);
```

Customers who have placed an order:
```sql
SELECT customer_id, customer_name
FROM customers
WHERE customer_id IN (
  SELECT customer_id
  FROM orders
);
```

Customers with no orders can also be found using NOT EXISTS:
```sql
SELECT c.customer_id, c.customer_name
FROM customers AS c
WHERE NOT EXISTS (
  SELECT 1
  FROM orders AS o
  WHERE o.customer_id = c.customer_id
);
```
NOT EXISTS is often safer than NOT IN when the subquery could contain NULL values.

## 8. Correlated subquery
A correlated subquery refers to a value from the outer query:
```sql
SELECT c.customer_id, c.customer_name
FROM customers AS c
WHERE EXISTS (
  SELECT 1
  FROM orders AS o
  WHERE o.customer_id = c.customer_id
    AND o.status = 'Delivered'
);
```
This returns customers with at least one delivered order.

## 9. Practical query-building method
1. Rewrite the business question in plain language.
2. Identify the output grain.
3. Identify required tables and join keys.
4. Decide which records must be retained (INNER or LEFT).
5. Add filters.
6. Aggregate at the correct grain.
7. Check row counts and totals before and after joining.
8. Explain the result and limitations.

## 10. Worked example
Customers:
| customer_id | name | city |
|---|---|---|
| 1 | Asha | Hyderabad |
| 2 | Ravi | Bengaluru |
| 3 | Meera | Hyderabad |

Orders:
| order_id | customer_id | amount |
|---|---|---:|
| 101 | 1 | 500 |
| 102 | 1 | 300 |
| 103 | 2 | 700 |

Query:
```sql
SELECT c.city, COUNT(o.order_id) AS order_count,
       SUM(o.amount) AS order_value
FROM customers AS c
INNER JOIN orders AS o
  ON c.customer_id = o.customer_id
GROUP BY c.city;
```
Expected:
- Hyderabad: 2 orders, 800.
- Bengaluru: 1 order, 700.
Meera is not in this INNER JOIN result because she has no matching order. A LEFT JOIN would preserve her customer row.

## 11. Common mistakes
| Mistake | Fix |
|---|---|
| Joining on customer name | Join using stable keys |
| Missing ON condition | Define the relationship explicitly |
| Unexpected row multiplication | Check table grain/cardinality |
| LEFT JOIN loses unmatched rows | Review filters on right-side columns |
| NOT IN returns unexpected result | Check NULLs; consider NOT EXISTS |
| Ambiguous column name | Use table aliases |
| Double-counted revenue | Aggregate at the correct grain |

## 12. Interview revision
- INNER JOIN keeps matches; LEFT JOIN preserves all left-side rows.
- One-to-many joins can multiply rows.
- Subqueries allow a query result to be used by another query.
- EXISTS checks whether a matching row exists.
- Join keys should be stable identifiers, not display names.
- Always validate grain and totals after a join.

### Interview questions
**Q1. Difference between INNER JOIN and LEFT JOIN?**  
INNER JOIN returns matching rows from both tables. LEFT JOIN returns every left-table row and any matching right-table row; unmatched right values are NULL. For a customer list that must include people with no orders, use LEFT JOIN.

**Q2. How can a join cause duplicate revenue?**  
If one order has several order-item records, the order header amount repeats for each item after the join. Summing that repeated amount overstates revenue. I would calculate at the correct grain or aggregate the item data before joining.

**Q3. What is a subquery?**  
A query nested inside another query. For example, find orders above the overall average by using a SELECT AVG(...) subquery in WHERE.

## 13. Mini-project — Customer Operations Analysis
**Time:** 60–75 minutes.

Workspace:
```text
Day_24_Customer_Operations_Analysis/
├── README.md
├── schema.sql
├── inputs/
│   └── sample_data.sql
├── analysis_queries.sql
├── expected_results.md
└── checker_checklist.md
```

Schema and sample data:
```sql
CREATE TABLE customers (
  customer_id INT PRIMARY KEY,
  customer_name VARCHAR(50),
  city VARCHAR(40)
);
CREATE TABLE orders (
  order_id INT PRIMARY KEY,
  customer_id INT,
  order_date DATE,
  status VARCHAR(20),
  total_amount DECIMAL(10,2)
);
INSERT INTO customers VALUES
(1,'Asha','Hyderabad'),
(2,'Ravi','Bengaluru'),
(3,'Meera','Hyderabad'),
(4,'Dev','Chennai');
INSERT INTO orders VALUES
(101,1,'2026-09-01','Delivered',500),
(102,1,'2026-09-04','Pending',300),
(103,2,'2026-09-05','Delivered',700),
(104,2,'2026-09-07','Late',200),
(105,4,'2026-09-08','Delivered',600);
```

Business questions:
1. List every order with customer name and city.
2. Show all customers, including those without orders.
3. Find customers with no orders.
4. Find customers with at least one delivered order using EXISTS.
5. Find orders above the overall average amount.
6. Calculate order count and order value by city.
7. Calculate delivered order count by customer.
8. Explain why the LEFT JOIN result includes customers with no orders.

Expected checks:
- Customers = 4; orders = 5.
- Customer Meera has no orders.
- Hyderabad order value = 800 across 2 orders.
- Bengaluru order value = 900 across 2 orders.
- Chennai order value = 600 across 1 order.
- Overall average order amount = 460.
- Orders above average: 500, 700 and 600 (3 rows).

Checker:
- [ ] Join keys are customer_id.
- [ ] Every query states its intended grain.
- [ ] LEFT JOIN retains customers with no orders.
- [ ] No-order query correctly tests NULL or NOT EXISTS.
- [ ] Average subquery returns 460.
- [ ] City totals reconcile to 2,300.
- [ ] No accidental row multiplication.
- [ ] Each query has a plain-language explanation.

Hints: First count rows in customers and orders separately. Then compare the join row count. Meera should appear with NULL order fields in the LEFT JOIN. For city revenue, ensure each order is counted once.

Extension: Add an order_items table and show how you would avoid double-counting order-level values when joining to line items.

## 14. Knowledge check
1. Which join preserves every row from the left table? A) INNER B) LEFT C) CROSS D) SELF. **Answer: B**.
2. How do you find unmatched right rows after a LEFT JOIN? A) WHERE right.id IS NULL B) WHERE right.id=0 C) GROUP BY NULL D) ORDER BY NULL. **Answer: A**.
3. What can a one-to-many join do? A) Always reduce rows B) Multiply rows C) Remove all NULLs D) Change primary keys. **Answer: B**.
4. What does EXISTS test? A) Whether a matching row exists B) Whether a table is empty only C) Whether a value is numeric D) Whether a chart exists. **Answer: A**.
5. Why can NOT IN be risky with NULLs? A) It sorts values B) NULL can affect the comparison result C) It changes data types D) It deletes rows. **Answer: B**.

## 15. Assessment and bridge
Complete Day 24 when you can select the correct join, explain row multiplication, use a subquery/EXISTS, and reconcile the customer and city summaries.

**Bridge to Day 25:** SQL produces business summaries. Next, use descriptive statistics to interpret variation and distributions rather than relying on averages alone.
