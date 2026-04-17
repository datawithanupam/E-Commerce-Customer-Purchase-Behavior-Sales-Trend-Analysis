# 🛒 E-Commerce Customer Purchase Behavior & Sales Trend Analysis
### Advanced SQL Analysis on Real Transactional Data | MySQL Workbench

![SQL](https://img.shields.io/badge/SQL-MySQL-blue)
![Dataset](https://img.shields.io/badge/Dataset-Olist%20E--Commerce-orange)
![Queries](https://img.shields.io/badge/Queries-12%20Business%20Questions-green)
![Concepts](https://img.shields.io/badge/Concepts-CTEs%20%7C%20Window%20Functions%20%7C%20LAG%20%7C%20LEAD%20%7C%20NTILE-purple)

---

## 📌 Project Overview

This project analyzes 99,000+ real e-commerce transactions from the
**Brazilian Olist E-Commerce Dataset** using advanced SQL techniques.
It answers 12 critical business questions across revenue trends,
customer behavior, product performance, delivery operations, and
seller efficiency — producing insights directly actionable by
marketing, operations, and product teams.

> This is not just data querying. Every query answers a question a
> business manager would actually ask on a Monday morning.

---

## 🎯 Business Questions Answered

| # | Business Question | SQL Concept Used |
|---|---|---|
| 1 | How has revenue trended month over month? | CTE + LAG() |
| 2 | What is our cumulative revenue growth? | SUM() OVER() Running Total |
| 3 | Which product categories drive the most revenue? | RANK() + CROSS JOIN |
| 4 | How do we segment customers by value? | NTILE() + CASE WHEN |
| 5 | Which days of the week see most orders? | RANK() OVER() + GROUP BY |
| 6 | What does next month's volume look like? | LAG() + LEAD() |
| 7 | How long are customers active? First vs latest purchase? | ROW_NUMBER() + NULLIF() |
| 8 | Is revenue growth consistent or volatile? | Rolling AVG — ROWS BETWEEN |
| 9 | Do high-value customers pay differently? | NTILE() + PARTITION BY |
| 10 | Which orders breached delivery SLA? | DATEDIFF() + CASE WHEN |
| 11 | Who are the top sellers across all metrics? | Multi-RANK() Composite Score |
| 12 | What is each customer's inter-purchase gap? | LAG() + DATEDIFF() |

---

## 🗃️ Dataset

**Brazilian E-Commerce Public Dataset by Olist**
- 📦 Source: [Kaggle — Olist Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- 📅 Period: September 2016 – September 2018
- 📊 Scale: ~100,000 orders, ~99,000 customers

| Table | Rows | Description |
|---|---|---|
| customers | 99,441 | Customer IDs, location |
| orders | 96,461 | Order status, timestamps |
| order_items | 112,650 | Products, prices, sellers |
| order_payments | 103,886 | Payment types, values |
| olist_products_dataset | 32,340 | Product categories |

> ⚠️ **Critical Data Note:** `customer_id` resets with every order.
> All customer-level analysis uses `customer_unique_id` to correctly
> identify real repeat buyers.

---

## 🧠 SQL Concepts Demonstrated

| Concept | Where Used |
|---|---|
| `WITH` (CTE) | All 12 queries |
| `LAG()` | Revenue MoM trend, purchase gap |
| `LEAD()` | Forward-looking order forecast |
| `ROW_NUMBER()` | Customer purchase ranking |
| `RANK()` | Category, seller, day rankings |
| `DENSE_RANK()` | Tie-safe ranking |
| `NTILE()` | Customer value segmentation |
| `SUM() OVER()` | Running totals |
| `AVG() OVER()` | Rolling 3-month smoothing |
| `ROWS BETWEEN` | Sliding window frame |
| `PARTITION BY` | Per-segment calculations |
| `DATEDIFF()` | Gap and lifespan analysis |
| `CASE WHEN` | Conditional classification |
| `NULLIF()` | Safe division (no divide-by-zero) |
| `CROSS JOIN` | Dynamic reference injection |

---


---

## 🔍 Key Insights & Business Decisions

### 1. Revenue & Growth
- Revenue shows consistent MoM growth through 2017 with a clear
  peak in Nov 2017 (Black Friday effect)
- Rolling 3-month average confirms underlying growth is real,
  not just seasonal spikes
- **Decision:** Scale inventory and ad spend in Q4; use rolling
  avg to set realistic monthly targets

### 2. Customer Behavior
- ~97% of customers purchase only once — repeat buyers are rare
  but extremely high-value
- Repeat customers have an average inter-purchase gap of
  60–120 days
- **Decision:** Any retention investment focused on the top 3%
  repeat buyers yields disproportionate ROI

### 3. Product Performance
- Top 3 categories contribute over 40% of total revenue
- Long-tail categories (bottom 50%) contribute under 15% combined
- **Decision:** Prioritize inventory depth in top categories;
  evaluate viability of low-revenue categories

### 4. Customer Segmentation
- High-value customers (top NTILE tier) spend 3–5x more per order
  than low-value customers
- High-value customers prefer credit card payments; low-value
  customers use more boleto (bank slip)
- **Decision:** Design payment-specific promotions — installment
  offers for high-value, upfront discounts for boleto users

### 5. Delivery Operations
- A significant % of orders arrive after the estimated delivery date
- Late deliveries correlate with lower review scores
- **Decision:** Tighten SLA commitments in high-delay zip codes;
  use on-time delivery as a seller performance KPI

### 6. Campaign Scheduling
- Monday and Tuesday see the highest order volumes
- Weekend orders are significantly lower
- **Decision:** Schedule email campaigns and flash sales for
  Sunday night / Monday morning for maximum conversion

### 7. Seller Performance
- Top sellers by revenue are not always top sellers by review score
- Composite ranking (revenue + volume + reviews) surfaces
  well-rounded sellers vs one-dimensional performers
- **Decision:** Use composite score for featured seller badges
  and preferential placement in search results

---

## 🛠️ Tools Used

- **MySQL 8.0** — Query execution
- **MySQL Workbench** — Schema design and import
- **Kaggle** — Dataset source

---

## 👤 Author

**Anupam Kumar**
📍 Bangalore, India
