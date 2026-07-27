# 📓 Coffee Vending Analytics — Project Journal & Steps

## Phase 1: Project Setup & Planning
* **Define Goals & Scope**: Set clear business goals for a coffee machine located in a hospital. Decided to analyze single-item sales and agreed on a step-by-step learning approach.
* **Create Git Repository**: Set up a Git environment on Linux Mint, created a `.gitignore` file to hide raw data and virtual environment files, and connected the project to GitHub.
* **Set Up Python Environment**: Created a Python virtual environment (`venv`) and installed key libraries (`pandas`, `jupyter`).
* **Define Business Questions**: Listed main business questions (total profit, top drinks, peak sales hours) to guide the analysis.

---

## Phase 2: Data Cleaning & Cost Calculations (`01_data_cleaning_and_cogs.ipynb`)
* **Load Data**: Imported raw 2025 sales data from an Excel file exported from Nayax.
* **Translate Schema**: Renamed Polish column names to English (`transaction_id`, `beverage_name`, `price`, `payment_method`, etc.) to make the project clear for international portfolios.
* **Remove Test Data**: Found and deleted 272 invalid or test transactions (where price was zero or missing).
* **Clean Drink Names**: Cleaned 26 messy text strings (with extra spaces, Nayax codes, and numbers) into 9 clear drink names (e.g., *Cappuccino*, *Coffee with Milk*, *Espresso*).
* **Add Time & Cost Features**:
  * Extracted time columns: `month`, `day_of_week`, `hour`, and `date`.
  * Added **COGS (Cost of Goods Sold)** based on the price of ingredients for each drink.
  * Added **Transaction Fees** (2% bank/card fee per payment).
  * Calculated **Gross Profit per Cup**: `price - cogs - transaction_fee`.
* **Save Clean Data**: Saved the cleaned table to `data/processed/clean_sales_2025.csv`.

---

## Phase 3: Data Analysis & Business Insights (`02_exploratory_analysis_and_kpis.ipynb`)
* **Calculate Annual Profit (P&L)**: Calculated total sales, sold volume, ingredient costs, bank fees, monthly fixed costs, and net profit.
* **Analyze Product Performance**: Grouped sales by drink type to find bestsellers and profit margins. Identified **Cappuccino** and **Coffee with Milk** as top sales and profit drivers.
* **Analyze Sales Patterns over Time**:
  * **Top Months**: August and September had the highest sales volume.
  * **Peak Hours**: Most drinks were sold between 10:00 AM and 2:00 PM, matching hospital visiting hours, appointment times, and staff lunch breaks.
* **Payment & Card Analysis**: Analyzed payment channels and card types. Identified **Contactless Bank Card (Karta bankowa CLS)** as the primary payment method and **VISA** as the leading card brand, highlighting strong customer preference for cashless convenience.
---

## Phase 4: Business Insights & Recommendations
* **Financial Assessment**: Verified positive net profit, identifying high fixed operating costs as the main reason for lower-than-expected total margins.
* **Operational Schedule**: Recommended machine restocking and maintenance outside the 09:00–15:00 window to maximize sales availability during peak hospital hours.
* **Pricing Strategy**: Identified opportunities to optimize profit margins by selectively increasing prices on core milk-based beverages while preserving entry-level drink pricing.

* **Tableau Integration Setup**: Prepared and verified `clean_sales_2025.csv` for BI dashboard creation. Planned executive dashboard layout including KPI scorecards, menu profitability, temporal rush-hour analysis, and payment distribution.