# 🛒 E-commerce Customer Retention & Cohort Analysis

An end-to-end **e-commerce customer analytics project** focused on understanding customer retention, repeat purchasing behaviour, customer value, and commercial performance using **Python, SQL, and Microsoft Excel**.

The project analyzes transaction-level e-commerce data and moves beyond basic sales reporting to answer business questions around **cohort retention, RFM segmentation, GMV, Average Order Value (AOV), repeat purchases, returns, cancellations, discount performance, and month-over-month growth**.

---

## 🎯 Business Objective

For an e-commerce business, acquiring customers is only the beginning. Long-term growth depends on whether customers return, how much value they generate, and which customer groups require retention or reactivation strategies.

This project was built to answer questions such as:

- How effectively are newly acquired customers retained?
- What percentage of purchasing customers return for another purchase?
- How does retention change across acquisition cohorts?
- Which customer segments generate the most value?
- Which customers may require reactivation?
- Which product categories contribute strongly to GMV?
- Which categories experience higher return and cancellation rates?
- How does performance vary across discount ranges?
- How does GMV change month over month?
- What actions could improve customer retention and commercial performance?

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|---|---|
| **Python** | Data cleaning, transformation, feature engineering, EDA, cohort analysis and RFM segmentation |
| **Pandas / NumPy** | Data manipulation and analytical calculations |
| **SQL / SQLite** | Business queries, aggregations, CTEs and window functions |
| **Microsoft Excel** | KPI reporting, cohort heatmap, RFM reporting and business presentation |
| **Google Colab** | Python and SQL analysis environment |
| **GitHub** | Project documentation and version control |

---

## 🔄 Project Workflow

```text
Raw E-commerce Transactions
        ↓
Data Quality Validation
        ↓
Data Cleaning & Transformation
        ↓
Feature Engineering
        ↓
Business KPI Analysis
        ↓
Customer Repeat-Purchase Analysis
        ↓
Cohort Retention Analysis
        ↓
RFM Customer Segmentation
        ↓
SQL Business Analysis
        ↓
Excel Reporting & Visualization
        ↓
Business Insights & Recommendations
```

---

## 🧹 1. Data Cleaning & Preparation

The raw transaction data was prepared for analysis using Python.

Key steps included:

- Removing duplicate records
- Checking missing values
- Standardizing date fields
- Validating quantity and pricing information
- Reviewing order-status values
- Creating analysis-ready customer and transaction fields
- Preparing cleaned data for SQL analysis

Additional analytical features were created for:

- GMV
- Discount analysis
- Order month
- Customer purchase history
- Cohort month
- Cohort index
- Recency
- Frequency
- Monetary value

---

## 📊 2. Business KPI Analysis

Core e-commerce KPIs were calculated to establish an overall view of business performance.

The analysis includes:

- **Total Orders**
- **Delivered Orders**
- **Total Customers**
- **Gross Merchandise Value (GMV)**
- **Average Order Value (AOV)**
- **Repeat Customer Rate**
- **Return Rate**
- **Cancellation Rate**

These metrics provide the foundation for the deeper customer and retention analysis.

---

## 🔁 3. Repeat Purchase Analysis

Customers were analyzed based on their completed purchasing activity.

A **repeat customer** was defined as a customer with more than one delivered order during the analysis period.

This analysis helps distinguish between:

- One-time customers
- Repeat customers

Understanding this split is important because order volume alone does not show whether the business is successfully converting acquired customers into recurring buyers.

---

## 📅 4. Cohort Retention Analysis

Customers were grouped according to the month of their **first purchase**.

Each cohort was then tracked across subsequent months:

```text
M0 = Acquisition month
M1 = One month after acquisition
M2 = Two months after acquisition
M3 = Three months after acquisition
...
```

The cohort matrix helps answer:

> After customers make their first purchase, what proportion returns in later months?

### Key Observation

Across mature cohorts, post-acquisition retention generally remains around the **mid-20% range**.

Rather than continuously collapsing after acquisition, retention stabilizes for a meaningful subset of customers.

At the same time, the analysis indicates an opportunity to convert a larger share of first-time buyers into repeat purchasers.

---

## 👥 5. RFM Customer Segmentation

RFM analysis was used to understand differences in customer behaviour and value.

### R — Recency

How recently did the customer make a purchase?

### F — Frequency

How frequently did the customer purchase?

### M — Monetary

How much monetary value did the customer generate?

Customers were grouped into actionable segments such as:

- **Champions**
- **Loyal Customers**
- **Potential Loyalists**
- **At Risk**
- **Hibernating**

This allows the business to move from a single retention strategy toward differentiated customer treatment.

### Example Actions

**Champions**

Protect high-value relationships through loyalty benefits, personalization and relevant early-access opportunities.

**Loyal Customers**

Encourage continued engagement using personalized recommendations and loyalty initiatives.

**Potential Loyalists**

Focus on increasing purchase frequency and developing these customers into stronger repeat buyers.

**At Risk**

Test targeted win-back campaigns based on previous purchasing behaviour.

**Hibernating Customers**

Use selective reactivation campaigns rather than relying on blanket discounts.

---

## 💰 6. Customer Value Analysis

Customer count alone does not determine the commercial importance of an RFM segment.

Therefore, the project also evaluates:

- Number of customers by segment
- Average monetary value
- Total monetary value
- Contribution to customer value

This provides a more commercially relevant view of segmentation by connecting customer behaviour with monetary contribution.

---

## 🗃️ 7. SQL Business Analysis

The cleaned transaction data was loaded into **SQLite** for business analysis.

SQL was used to answer questions including:

1. How does GMV change month over month?
2. Which product categories generate the highest GMV?
3. Which categories have the highest Average Order Value?
4. Who are the highest-value customers?
5. How many customers make repeat purchases?
6. What is the repeat customer rate?
7. What is the distribution of one-time vs repeat customers?
8. Which categories experience higher return rates?
9. Which categories experience higher cancellation rates?
10. Which cities contribute the most GMV?
11. Which products generate the highest GMV within each category?
12. How does the active purchasing customer base change over time?
13. What percentage of GMV does each category contribute?
14. How does performance vary across discount ranges?
15. How does GMV grow or decline month over month?

---

## 🧠 SQL Concepts Used

The analysis demonstrates:

```sql
GROUP BY
CASE WHEN
COUNT(DISTINCT ...)
CTEs
DENSE_RANK()
LAG()
PARTITION BY
Window Functions
Conditional Aggregation
```

For example, product performance was ranked **within individual categories** using `DENSE_RANK()` and `PARTITION BY`.

Month-over-month GMV analysis used `LAG()` to compare current performance with the previous month.

---

## 🛍️ 8. Category Performance

Product categories were evaluated using metrics such as:

- Order volume
- Customer count
- GMV
- Return rate
- Cancellation rate

An important observation from the return analysis is that category-level return rates are relatively close.

This means category-level information alone may not be sufficient to identify the underlying causes of returns.

A more granular analysis using **SKU, brand, price range and return reason** could provide more actionable insights.

---

## 🏷️ 9. Discount Analysis

Orders were grouped into discount ranges to compare:

- Order volume
- Customer activity
- GMV

The analysis shows that the discount range associated with the highest transaction volume is not necessarily the same range associated with the highest monetary value.

This highlights an important commercial principle:

> **More orders do not automatically mean more value.**

Promotional decisions should therefore consider GMV, customer value and repeat purchasing rather than evaluating discounts using transaction volume alone.

The results represent observed associations and should not be interpreted as evidence that discounts directly caused changes in purchasing behaviour.

---

## 📈 10. Month-over-Month Performance

Monthly GMV was analyzed using SQL window functions.

`LAG()` was used to retrieve previous-month GMV and calculate month-over-month growth.

The analysis shows fluctuations across the year rather than a consistently increasing or decreasing pattern.

This suggests that GMV changes should be evaluated alongside:

- Customer activity
- Category mix
- Promotional activity
- Order behaviour
- Retention patterns

rather than interpreting monthly GMV in isolation.

---

## 📗 11. Excel Analysis & Reporting

Microsoft Excel was used as the final business-reporting layer.

The workbook includes:

- Executive KPI Summary
- Cohort Retention Heatmap
- RFM Customer Segmentation
- Customer Value Contribution
- Category Analysis
- Return Analysis
- Cancellation Analysis
- Discount Analysis
- Monthly GMV Trend
- Business Insights & Recommended Actions

This provides a stakeholder-friendly layer on top of the Python and SQL analysis.

---

## 💡 Key Business Insights

### 1. Retention

Post-acquisition retention among mature cohorts generally remains around the mid-20% range.

A meaningful subset of customers continues purchasing after acquisition, while an opportunity remains to increase conversion from first purchase to repeat purchase.

### 2. Customer Segmentation

RFM analysis identifies materially different customer groups based on recency, frequency and monetary value.

Retention strategies should therefore be differentiated rather than applying the same treatment to every customer.

### 3. Customer Value

Customer count alone does not represent segment importance.

Combining RFM behaviour with monetary contribution provides a stronger basis for prioritizing retention and reactivation initiatives.

### 4. Returns

Category return rates are relatively close.

Deeper SKU-, brand- and return-reason-level analysis would be required before attributing return issues to specific product categories.

### 5. Discounts

The discount range generating the greatest transaction volume is not necessarily the range generating the highest GMV.

Promotional performance should therefore be evaluated using multiple commercial metrics.

### 6. Monthly Performance

GMV fluctuates month over month.

Customer activity, product mix and promotional context should be considered before drawing conclusions about the causes of these movements.

---

## 🎯 Business Recommendations

### Strengthen the Second-Purchase Journey

Develop targeted post-purchase journeys for first-time customers and test campaign timing against observed repurchase behaviour.

### Protect High-Value Customers

Use differentiated retention strategies for Champions and Loyal Customers through personalization, loyalty benefits and relevant offers.

### Reactivate At-Risk Customers

Use historical purchase behaviour to design targeted win-back campaigns rather than sending generic promotions.

### Optimize Promotional Strategy

Evaluate discounts using:

- GMV
- Order volume
- Repeat purchasing
- Customer value

instead of optimizing for transactions alone.

### Investigate Returns at a Granular Level

Extend the analysis to:

- SKU
- Brand
- Price range
- Return reason

to identify more actionable drivers of returns.

### Monitor Cohort Retention

Track acquisition cohorts regularly to determine whether customer quality and retention performance improve over time.

---

## 📂 Repository Files

```text
Ecommerce_Customer_Retention_Analysis.ipynb
    → Complete Python and SQL analysis

Ecommerce_Retention_Analysis.xlsx
    → Excel reporting, retention analysis and business presentation

ecommerce_transactions.csv
    → Raw transaction dataset

ecommerce_cleaned.csv
    → Cleaned analysis-ready dataset

cohort_retention.csv
    → Cohort retention output

rfm_segments.csv
    → RFM customer segmentation output

kpi_summary.csv
    → Business KPI summary
```

---

## 🚀 Skills Demonstrated

**Data Analysis**
- Exploratory Data Analysis
- Data Cleaning
- Feature Engineering
- KPI Analysis

**Customer Analytics**
- Cohort Analysis
- Customer Retention
- Repeat Purchase Analysis
- RFM Segmentation
- Customer Value Analysis

**E-commerce Analytics**
- GMV
- AOV
- Returns
- Cancellations
- Discount Analysis
- Category Performance

**SQL**
- CTEs
- Window Functions
- DENSE_RANK
- LAG
- Conditional Aggregation
- Business Query Development

**Business Analytics**
- Problem Framing
- KPI Interpretation
- Customer Segmentation
- Insight Generation
- Recommendation Development

---

## 📌 Project Takeaway

The key takeaway from this project is that **e-commerce performance cannot be understood through GMV alone**.

Retention, repeat purchasing, customer value, returns, cancellations, discount behaviour and customer segmentation provide additional context required for better business decisions.

By combining **Python for analytical processing, SQL for business querying, and Excel for stakeholder reporting**, this project demonstrates an end-to-end approach to translating transaction data into actionable customer and commercial insights.

---

## 👩‍💻 Author

**Disha Pramanick**

Data Analyst | SQL | Python | Excel | Power BI | Tableau

Portfolio:  
https://dishapramanick2018-eng.github.io/
