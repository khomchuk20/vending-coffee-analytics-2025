# 📓 Coffee Vending Analytics — Data Journal & Progress Log

## 📍 Phase 1: Planning & Business Requirements
* **Objective**: Defined project scope to evaluate sales performance, unit economics, and customer purchasing patterns for a self-service coffee machine located in a hospital.
* **Constraints Identified**: Single-item transactions only (no cart analysis required).
* **Architecture Setup**: Configured local environment (Linux Mint, Python, Jupyter, Git) and initialized GitHub repository with `.gitignore`.

---

## 📍 Phase 2: Data Cleaning & COGS Modeling (`01_data_cleaning_and_cogs.ipynb`)
* **Data Ingestion**: Loaded raw 2025 sales logs exported from the Nayax platform (`.xlsx`).
* **Header & Anomaly Handling**: Identified and stripped 272 invalid/test transactions (zero/negative values or empty strings).
* **Column Normalization**: Renamed Polish schema to English standardized names (`transaction_id`, `transaction_time`, `beverage_name`, `price`, `payment_method`, `card_brand`).
* **Text Normalization**: Cleaned 26 raw/dirty product strings (containing control characters, Nayax codes, and irregular casing) down to 9 clean canonical beverages (e.g., *Cappuccino*, *Coffee with Milk*, *Espresso*, *Matcha*).
* **Feature Engineering**:
  * Extracted time dimensions: `month`, `day_of_week`, `hour`, `date`.
  * Added **COGS (Cost of Goods Sold)** mapping based on ingredient costs per drink.
  * Calculated **Transaction Fees** (2% payment gateway rate).
  * Derived **Gross Profit per Cup**: `price - cogs - transaction_fee`.
* **Data Export**: Saved sanitized dataset to `data/processed/clean_sales_2025.csv`.

---

## 📍 Phase 3: Exploratory Analysis & Unit Economics (`02_exploratory_analysis_and_kpis.ipynb`)
* **Annual P&L Summary**: Built top-level financial KPIs (Gross Revenue, Total Volume, Total COGS, Total Fees, Fixed OpEx, Net Profit, and Net Profit Margin %).
* **Menu Performance**: Calculated volume share, revenue contribution, and profit margins per beverage. Identified **Cappuccino** and **Coffee with Milk** as top drivers of volume and profit.
* **Temporal Insights**:
  * **Peak Months**: August and September generated peak sales volume.
  * **Peak Hours**: 10:00 AM – 2:00 PM showed heaviest traffic, perfectly correlating with hospital visiting hours, outpatient appointments, and staff breaks.