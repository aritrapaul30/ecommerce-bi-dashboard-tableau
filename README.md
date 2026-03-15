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
- **Headline KPIs**: Total Revenue (~737K$), Customers (1,000), AOV (~737$), Avg Rating (~4.0 ⭐)
- **Monthly Growth Chart**: Identifies seasonal peaks (August & December dominate)
- **Revenue Tree Map**: Category contribution - Electronics, Fashion, Sports & Outdoors, Books, Home & Living
- **Top Cities**: Geographic revenue concentration across 981 cities
- **Customer Segmentation**: Gender × Age band rings

### 🟢 Dashboard 2: Revenue
Drills into controllable revenue levers:
- **Monthly/Quarterly Trend Toggle**: Tactical vs. strategic granularity
- **Category Performance Panel**: Revenue amount + contribution share + micro-trend direction
- **Payment Influence Donut**: Bank Transfer vs. Credit Card vs. Cash on Delivery revenue split
- **Top N Products Bar Chart**: Dynamic parameter - switch between Top 10 / Top 20 instantly

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

| Field | Formula | Description |
|---|---|---|
| `Revenue` | `quantity × price` | Total sales value per transaction |
| `Customers` | `COUNTD(customer_id)` | Count of unique customers |
| `Avg Rating` | `AVG(review_score)` | Overall customer satisfaction indicator |
| `AOV` | `Total Revenue / Order Count` | Estimated average basket value |
| `Top N Parameter` | Dynamic integer filter | Adjustable filter for top cities and products |
---

## 🔍 Key Findings

- 📅 **Seasonal Risk**: Revenue is concentrated in **August and December** - operational failures in these two months destroy yearly performance
- 🗺️ **Geographic Fragmentation**: 981 cities served with no dominant hub - scattered delivery network is driving inconsistent review scores
- 👴 **Senior Customer Frustration**: Customers aged 55+ are the **highest spenders** but show the **lowest satisfaction** in Fashion and Books categories
- 💳 **Payment Complexity**: Three equally split payment methods (Bank Transfer, Credit Card, Cash on Delivery) signals no optimised checkout - Friction hurts seniors most
- ⚠️ **Risk–Revenue Trade-off**: Electronics generates the highest revenue but carries **below-average satisfaction** - scaling it further amplifies brand risk

---

## 💡 Strategic Recommendations

| Priority | Action |
|---|---|
| 🔴 High | Fix high-revenue + low-rating products immediately (protect revenue engine) |
| 🟠 Medium | Streamline payment experience — prioritise one dominant, frictionless method |
| 🟡 Medium | Segment-aware experience strategy for 55+ customers in Fashion & Books |
| 🟢 Low | Expand strong mid-tier categories with upward revenue trends |
| 🟢 Low | Use Risk–Revenue matrix before launching any scaling campaigns |

---

## ⚠️ Limitations

- No unique `order_id` — AOV is an estimate, not exact basket-level calculation
- No product cost / margin data — revenue ≠ profitability
- No promotion or discount flags — cannot isolate organic vs. promotional demand
- No delivery/logistics data — cannot confirm if low ratings are product or shipping issues
- No review text — ratings identified, but root causes unknown
- Synthetic dataset (10,000 rows) — patterns may not generalise to real-world complexity

---

## 🧰 Tools & Skills

![Tableau](https://img.shields.io/badge/Tableau-E97627?style=flat&logo=tableau&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)

| Skill | Application |
|---|---|
| Tableau Desktop | Dashboard design, calculated fields, parameters |
| Data Storytelling | Three-layer narrative: Overview → Revenue → Risk |
| BI Dashboard Design | Interactive navigation, Top N filters, time controls |
| Business Analytics | KPI framing, segmentation, risk–revenue matrix |
| Statistical Thinking | Univariate → Bivariate → Multivariate analytical layers |

---

## 🚀 How to Open the Dashboard

1. Download and install **[Tableau Public](https://public.tableau.com/en-us/s/download)** (free)
2. Clone or download this repository
3. Open `E-commerce Dashboard.twbx` in Tableau
4. Use the **navigation bar** to move between dashboards
5. Use **Top N sliders** and **time controls** to explore interactively

> 💡 **Note**: Dashboard is designed for **3840×2160 (4K)** resolution. On smaller screens, layout may shift - refer to the PDF report for intended visual output.
