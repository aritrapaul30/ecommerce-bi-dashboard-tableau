# 🛒 E-Commerce BI Dashboard: Growth, Satisfaction & Risk Analysis


---

## 📌 Project Overview

This project delivers an **interactive, three-dashboard Business Intelligence suite** built in Tableau to answer a core managerial question:

> *How do product mix, customer demographics, and purchasing behaviours influence revenue performance and customer satisfaction — and how can a retailer grow without eroding brand trust?*

The analysis moves beyond aggregate averages to surface hidden risks: high-revenue products with low ratings, frustrated senior customers, and seasonal revenue concentration — all translated into **actionable strategic recommendations**.

---

## 🎯 Research Questions

1. **Revenue Performance** — Which product categories and cities generate the most revenue? Are there payment method or seasonal trends driving totals?
2. **Demographics** — How do age groups and genders vary in Average Order Value (AOV) and return frequency?
3. **Satisfaction & Risk** — Which products combine high revenue with low ratings, and what interventions are needed before growth is impacted?

---

## 🗂️ Dataset

| Attribute | Detail |
|---|---|
| **Source** | [Kaggle — Online Retail & E-Commerce Dataset](https://www.kaggle.com/datasets/ertugrulesol/online-retail-data/data) |
| **Type** | Synthetic POS transactional data |
| **Size** | 10,000 rows × 13 columns |
| **Coverage** | Orders, customer demographics, product categories, review scores |

### 📋 Key Variables

| Variable | Description |
|---|---|
| `customer_id` | Unique customer identifier |
| `order_date` | Purchase date |
| `product_name` | Product sold |
| `category_name` | Product category (Electronics, Fashion, etc.) |
| `quantity` | Units purchased per transaction |
| `price` | Unit price at time of transaction |
| `payment_method` | Bank Transfer / Credit Card / Cash on Delivery |
| `city` | Customer's city |
| `review_score` | Customer satisfaction rating (1.0–5.0) |
| `gender` | Customer gender |
| `age` | Customer age at time of transaction |

---

## 📊 Dashboard Architecture

The dashboards follow a structured decision-making flow:

📋 Overview → 💰 Revenue → ⭐ Customer Satisfaction

### 🔵 Dashboard 1: Overview
Establishes the business health baseline:
- **Headline KPIs**: Total Revenue (~$737K), Customers (1,000), AOV (~$737), Avg Rating (~4.0 ⭐)
- **Monthly Growth Chart**: Identifies seasonal peaks (August & December dominate)
- **Revenue Tree Map**: Category contribution — Electronics, Fashion, Sports & Outdoors, Books, Home & Living
- **Top Cities**: Geographic revenue concentration across 981 cities
- **Customer Segmentation**: Gender × Age band rings

### 🟢 Dashboard 2: Revenue
Drills into controllable revenue levers:
- **Monthly/Quarterly Trend Toggle**: Tactical vs. strategic granularity
- **Category Performance Panel**: Revenue amount + contribution share + micro-trend direction
- **Payment Influence Donut**: Bank Transfer vs. Credit Card vs. Cash on Delivery revenue split
- **Top N Products Bar Chart**: Dynamic parameter — switch between Top 10 / Top 20 instantly

### 🔴 Dashboard 3: Customer Satisfaction & Risk
Converts ratings into business risk signals:
- **Satisfaction Heatmap** (Category × Age Band): Pinpoints which segments are most dissatisfied
- **Risk–Revenue Scatter Plot**: Positions every product on a revenue vs. rating trade-off matrix
- **Worst Products View**: Isolates items pulling ratings down for operational intervention
- **Demographic Sentiment Bubbles**: Age group vs. category satisfaction
- **Top Customers Table**: High-value customer retention lens

---

## 🛠️ Data Engineering & Calculated Fields

All calculated fields were built directly in Tableau:

```text
Revenue         = quantity × price
Customers       = COUNTD(customer_id)
Avg Rating      = AVG(review_score)
AOV             ≈ Total Revenue / Order Count
Top N Parameter = Dynamic integer filter for cities and products

