# 🛒 E-Commerce Sales, Profitability & Operational Intelligence Dashboard

An end-to-end business intelligence and data analytics project demonstrating **AI-driven synthetic data engineering**, **forensic spreadsheet auditing in Microsoft Excel**, **DAX KPI calculations**, and a **3-page interactive executive dashboard in Microsoft Power BI**.

---

## 📌 Project Overview
* **Domain:** E-Commerce / Retail Operations
* **Tools Used:** Microsoft Excel, Microsoft Power BI, Power Query, DAX, Generative AI
* **Dataset Scope:** 3,500 Validated Orders (22 Attributes)
* **UI Theme:** Midnight Dark Canvas with Clean High-Contrast Visual Cards

---

## 🏗️ Analytics Workflow

1. **Synthetic Data Engineering (Generative AI):** Generated a 22-attribute e-commerce dataset containing 3,505 initial transactions, with realistic operational anomalies (duplicates, unassigned marketing channels, returns, cancellations).
2. **Forensic Audit & Cleaning (Microsoft Excel):** Dropped 5 exact duplicate order pairs (10 redundant rows) to preserve 3,500 unique records. Reconciled mathematical boundaries ($\text{Selling Price} = \text{List Price} \times (1 - \text{Discount})$) and validated 1,176 blanks as authentic non-delivered order states.
3. **Data Modeling & DAX Calculation Engine (Power BI + AI):** Created a centralized `_Measures` table housing 10 core business KPIs, verified against Excel baseline figures.
4. **Interactive Dashboard Design:** Built a 3-page reporting system with global synchronized slicers (`Order Date`, `Category`, `Region`).
5. **Business Insights & Strategy:** Extracted 10 actionable recommendations covering profit retention, marketing channels, and logistics turnaround.

---

## 🖥️ Dashboard Previews

### Page 1: Executive Overview
![Executive Overview](Screenshot%202026-08-31%20101749.png)
*Tracks top-level enterprise metrics: Total Revenue ($6.91\text{M}$), Gross Profit ($828.98\text{K}$), Profit Margin ($11.99\%$), Total Orders ($3.5\text{K}$), and regional distributions.*

---

### Page 2: Customer & Product Analysis
![Customer & Product Analysis](Screenshot%202026-08-31%20101810.png)
*Granular breakdown of bestselling products (Air Fryer, Coffee Maker), customer segments, category ratings, and return rates by category.*

---

### Page 3: Marketing & Operations
![Marketing & Operations](Screenshot%202026-08-31%20101834.png)
*Attribution channel revenue, pre-fulfillment cancellation rates, payment method split, and regional logistics costs vs. delivery days.*

---

## 📊 Audited Benchmark KPIs & DAX Formulas

| KPI / Metric | DAX Formula Applied | Audited Value | Business Interpretation |
| :--- | :--- | :--- | :--- |
| **Total Orders** | `DISTINCTCOUNT(Orders[Order_ID])` | **3,500** | Total processed unique transactions |
| **Total Quantity** | `SUM(Orders[Quantity])` | **4,916 units** | Net physical items ordered |
| **Total Net Revenue** | `SUM(Orders[Total_Amount])` | **₹69,11,402.28** ($6.91\text{M}$) | Realized cumulative sales |
| **Total Gross Profit** | `SUM(Orders[Profit])` | **₹8,28,982.28** ($828.98\text{K}$) | Bottom-line profitability post product cost |
| **Average Order Value (AOV)** | `DIVIDE([Total Revenue], [Total Orders], 0)` | **₹1,974.69** | Mean cart size realized per order |
| **Profit Margin %** | `DIVIDE([Total Gross Profit], [Total Revenue], 0)` | **11.99%** | Overall operational enterprise margin |
| **Average Customer Rating** | `AVERAGE(Orders[Rating])` | **4.37 / 5.00** ⭐ | Customer review score benchmark |
| **Return Rate %** | `DIVIDE(CALCULATE(DISTINCTCOUNT(Orders[Order_ID]), Orders[Order_Status]="Returned"), [Total Orders], 0)` | **15.80%** | Delivered merchandise returned post-sale |
| **Cancellation Rate %** | `DIVIDE(CALCULATE(DISTINCTCOUNT(Orders[Order_ID]), Orders[Order_Status]="Cancelled"), [Total Orders], 0)` | **17.80%** | Orders cancelled prior to fulfillment |
| **Avg Delivery Days** | `CALCULATE(AVERAGE(Orders[Delivery_Days]), Orders[Order_Status]="Delivered")` | **4.02 days** | Mean turnaround time for delivered items |

---

## 💡 Strategic Business Insights

* **Revenue Pillar:** `Home & Kitchen` contributes the largest revenue share ($2.7\text{M}$), making it the primary anchor category for bundling campaigns.
* **The Return Paradox:** `Beauty` ($18.03\%$) and `Electronics` ($17.88\%$) show high return rates despite customer ratings $>4.33$, pointing to packaging or transit issues rather than product defects.
* **Pre-Fulfillment Leakage:** `Sports` ($20.00\%$) and `Fashion` ($18.72\%$) experience high pre-dispatch cancellations, requiring sizing guides and checkout delivery estimates.
* **Marketing Channel Efficiency:** `Affiliate Marketing` ($1.21\text{M}$) and `Google Ads` ($1.19\text{M}$) yield the highest sales pipelines, confirming strong return on ad spend (ROAS).
* **Payment Reliability:** Payment share is evenly distributed ($\approx 19\text{--}20\%$ across UPI, Cards, Net Banking, and COD), ensuring zero single-gateway point of failure.
* **Logistics SLA:** Delivery turnaround is uniform at $\approx 4\text{ days}$ nationwide, with the Central region achieving the lowest shipping cost burden.

---

## 📂 Repository Structure

```text
├── E-Commerce Sales, Profitability & Customer Analysis.pbix  # Interactive Power BI Model
├── E-commerce_Sales_Analysis.xlsx                            # Cleaned & Audited Excel Dataset
├── README.md                                                 # Project Documentation
├── Screenshot 2026-08-31 101749.png                          # Page 1 Screenshot
├── Screenshot 2026-08-31 101810.png                          # Page 2 Screenshot
├── Screenshot 2026-08-31 101834.png                          # Page 3 Screenshot
└──raw_data.xlsx                                             # Original Transactional Data
