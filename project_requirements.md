# ☕ Coffee Vending Business Analytics (2025)

## 📌 Executive Summary
This project evaluates the financial performance, operational efficiency, and pricing structure of a self-service coffee vending machine operating in Poland during 2025. The analysis is performed for the business owner to optimize margins, identify peak demand periods, and refine the product offerings.

---

## 🎯 Business Questions (Stakeholder Requirements)

### 1. Financial Performance & Profitability
* What is the **real Net Profit Margin** for 2025 after considering all fixed costs (rent, utilities, ZUS) and variable costs (COGS, Nayax processing fees)?
* What is the monthly breakdown of Gross Revenue vs. Net Profit?

### 2. Pricing & Margin Optimization
* How margins (in PLN and %) vary across individual beverages?
* Is the price difference between products aligned with their unit cost differences (e.g., Espresso vs. Latte)?
* Which beverages generate the highest absolute gross profit vs. high margin percentage but low sales volume?

### 3. Time-Series & Demand Analysis
* What are the peak sales hours during the day and peak days of the week?
* When should maintenance and refilling occur to avoid downtime during high-demand hours?
* Are there seasonal sales trends across the months of 2025?

### 4. Operational & Payment Insights
* What is the distribution of payment methods (Card vs. BLIK vs. Mobile/Prepaid)?
* Which beverage categories represent the largest share of total sales volume?

---

## 📐 Key Performance Indicators (KPIs) & Metrics

| Metric | Formula / Description | Purpose |
| :--- | :--- | :--- |
| **Gross Revenue** | $\sum \text{Transaction Amounts}$ | Track total top-line sales |
| **COGS (Cost of Goods Sold)** | $\sum (\text{Ingredient Unit Cost} \times \text{Recipe Usage})$ | Measure direct cost of ingredients per cup |
| **OpEx (Operating Expenses)** | $\text{Fixed Costs (Rent, ZUS)} + \text{Variable Fees (Nayax Telemetry \& Processing)}$ | Calculate total overhead and fees |
| **Net Profit** | $\text{Gross Revenue} - (\text{COGS} + \text{OpEx})$ | Evaluate bottom-line profitability |
| **Net Margin %** | $(\text{Net Profit} / \text{Gross Revenue}) \times 100\%$ | Measure overall business efficiency |
| **Gross Profit per Cup** | $\text{Retail Price} - \text{Unit COGS} - \text{Transaction Fee}$ | Assess profitability of individual drinks |
| **Sales Volume** | $\text{Count of Transactions}$ | Track unit demand per product / time block |

---

## ⚠️ Analytical Assumptions & Constraints
* **Single-Item Transactions:** Each Nayax transaction corresponds to exactly one beverage purchase (no multi-item cart capabilities). Therefore, Average Order Value (AOV) is equivalent to product price and is excluded as a separate KPI.