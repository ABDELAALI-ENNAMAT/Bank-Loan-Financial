<!-- HEADER -->
<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,50:16213e,100:0f3460&height=250&section=header&text=🏦%20Bank%20Loan%20Financial%20Analysis&fontSize=38&fontColor=e94560&animation=fadeIn&fontAlignY=38&desc=Turning%20Raw%20Financial%20Data%20into%20Actionable%20Intelligence&descAlignY=58&descSize=16&descColor=a8dadc" width="100%"/>

<br/>

[![Power BI Live Dashboard](https://img.shields.io/badge/🔴%20LIVE%20DASHBOARD-Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://app.powerbi.com/reportEmbed?reportId=98676d40-1b49-4418-a2d8-0032bb5508c5&autoAuth=true&ctid=2e589d81-ea7a-4dc7-8fb2-84ba95cc947f)
[![PostgreSQL](https://img.shields.io/badge/SQL-PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Power BI](https://img.shields.io/badge/BI-Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![License](https://img.shields.io/badge/License-MIT-e94560?style=for-the-badge)](LICENSE)
[![Made with ❤️](https://img.shields.io/badge/Made%20with-❤️-e94560?style=for-the-badge)](https://github.com/ABDELAALI-ENNAMAT)

<br/>

> **"Without data, you're just another person with an opinion."** — *W. Edwards Deming*

</div>

---

## 🌟 Project at a Glance

<div align="center">

| 🗄️ Dataset | 🛠️ Tools | 📊 Dashboards | 📁 Deliverables |
|:---:|:---:|:---:|:---:|
| `FinancialData.csv` (~7.6 MB) | PostgreSQL + Power BI | 3 Interactive Pages | SQL Report + `.pbix` |
| Real-World Bank Loan Records | pgAdmin Query Engine | Summary · Overview · Details | Fully Reproducible |

</div>

---

## 📸 Dashboard Showcase

> 🔴 **[Click here to access the LIVE interactive dashboard →](https://app.powerbi.com/reportEmbed?reportId=98676d40-1b49-4418-a2d8-0032bb5508c5&autoAuth=true&ctid=2e589d81-ea7a-4dc7-8fb2-84ba95cc947f)**

### 📋 Summary View — The Big Picture
![Summary Dashboard](Screenshot%20Dashboard/Summary.PNG)
> *High-level KPIs: Total Applications, Funded Amounts, Repayments, Interest Rates, DTI Ratios — all at a glance.*

---

### 🔍 Overview View — Trends & Patterns
![Overview Dashboard](Screenshot%20Dashboard/Overview.PNG)
> *Temporal trends, geographic distributions, loan grades, employment lengths — understand the macro landscape.*

---

### 📂 Details View — Granular Record-Level Insights
![Details Dashboard](Screenshot%20Dashboard/Details.PNG)
> *Drill down to individual loan records. Filter by status, purpose, grade, and more for deep forensic analysis.*

---

## 🎯 Project Objectives

This project was built to simulate a **real-world financial analyst's workflow** — from raw data extraction using SQL to executive-level visualization in Power BI.

```
📦 Raw Data  ──►  🔍 SQL Analysis  ──►  🧹 Data Modeling  ──►  📊 Power BI Dashboard  ──►  💡 Insights
```

### The 4 Analytical Pillars:

| # | Focus Area | Business Question Answered |
|---|---|---|
| 🎯 1 | **Loan Performance Analysis** | Which borrower profiles repay most reliably? |
| 📈 2 | **Trend Identification** | How do interest rates vary by grade & term? |
| ⚠️ 3 | **Risk Assessment** | What DTI ratios correlate with loan defaults? |
| 🕒 4 | **Temporal Patterns** | When do borrowers tend to default or repay? |

---

## 🛠️ Tech Stack & Tools

<div align="center">

| Layer | Technology | Purpose |
|:---:|:---:|:---|
| 🗄️ **Database** | PostgreSQL (pgAdmin) | Data storage, complex SQL queries, aggregations |
| 📊 **Visualization** | Microsoft Power BI | Interactive dashboards, DAX measures, drill-throughs |
| 📁 **Data Format** | CSV (7.6 MB) | Source data for 38,000+ loan records |
| 📝 **Documentation** | Microsoft Word (.docx) | SQL query documentation & business context |

</div>

---

## 📁 Repository Structure

```
📦 Bank-Loan-Financial
 ┣ 📂 Dataset
 ┃ ┗ 📄 FinancialData.csv          ← 🗃️ Core dataset (~7.6 MB, 38K+ records)
 ┣ 📂 Report
 ┃ ┗ 📄 BANK LOAN REPORT QUERY DOCUMENT.docx  ← 📝 Full SQL query documentation
 ┣ 📂 Screenshot Dashboard
 ┃ ┣ 🖼️ Summary.PNG                ← Dashboard page 1
 ┃ ┣ 🖼️ Overview.PNG               ← Dashboard page 2
 ┃ ┗ 🖼️ Details.PNG                ← Dashboard page 3
 ┗ 📄 README.md                    ← You are here 👋
```

---

## 🔍 Key Insights Uncovered

### 💰 Financial KPIs Tracked
- **Total Loan Applications** — Volume trends Month-over-Month (MoM)
- **Total Funded Amount** — Capital deployed across loan categories
- **Total Amount Received** — Repayment health and collection rates
- **Average Interest Rate** — Trends across loan grades A–G
- **Average DTI (Debt-to-Income)** — Risk signal per borrower segment

### 📊 Analytical Findings

> 🟢 **Good Loans vs. 🔴 Bad Loans** — Segmentation by loan status (Fully Paid, Current, Charged Off) reveals repayment health at the portfolio level.

> 🏠 **Home Ownership Impact** — Borrowers who own their home vs. rent vs. mortgage show distinct repayment profiles.

> 💼 **Employment Length Matters** — Borrowers with 10+ years of employment consistently outperform in repayment reliability.

> 🎯 **Loan Purpose Distribution** — Debt consolidation dominates, followed by credit card refinancing and home improvement.

> 📅 **Seasonal Patterns** — Q4 shows a spike in loan applications correlated with holiday spending cycles.

---

## 🧩 SQL Analysis Highlights

All SQL queries are documented in [`Report/BANK LOAN REPORT QUERY DOCUMENT.docx`](Report/BANK%20LOAN%20REPORT%20QUERY%20DOCUMENT.docx).

Queries covered include:

```sql
-- Example: Total Applications by Month
SELECT 
    EXTRACT(MONTH FROM issue_date) AS Month,
    COUNT(id) AS Total_Applications,
    SUM(loan_amount) AS Total_Funded,
    SUM(total_payment) AS Total_Received
FROM financial_data
GROUP BY Month
ORDER BY Month;
```

```sql
-- Example: Good Loan vs Bad Loan KPIs
SELECT
    loan_status,
    COUNT(id) AS Total_Applications,
    SUM(loan_amount) AS Total_Funded_Amount,
    SUM(total_payment) AS Total_Amount_Received
FROM financial_data
GROUP BY loan_status;
```

> 📄 All queries, including complex JOINs, window functions, and aggregation logic, are fully documented in the report.

---

## 📊 Dashboard Deep Dive

### 🗂️ Page 1 — Summary
The **Summary** dashboard answers: *"How healthy is our loan portfolio?"*
- KPI cards: Total Applications, Total Funded, Total Received, Avg Interest, Avg DTI
- **Good Loan %** vs **Bad Loan %** donut chart
- Loan Status breakdown table

### 🌐 Page 2 — Overview
The **Overview** dashboard answers: *"Where, when, and how are loans being issued?"*
- Monthly application trend (line chart)
- State-level distribution (filled map)
- Loan term distribution (donut)
- Employment length analysis (bar chart)
- Loan purpose breakdown (horizontal bar)
- Home ownership breakdown (treemap)

### 🔬 Page 3 — Details
The **Details** dashboard answers: *"What does each individual loan look like?"*
- Fully filterable record-level grid
- Columns: Loan ID, Purpose, Grade, Sub-Grade, Ownership, State, Funded, Received, Interest Rate, Installment, DTI

---

## 🚀 How to Reproduce This Project

### Step 1 — Set Up PostgreSQL
```bash
# Install PostgreSQL and pgAdmin
# Create a new database: bank_loan_db
# Import FinancialData.csv using pgAdmin's Import/Export tool
```

### Step 2 — Run SQL Queries
```bash
# Open pgAdmin
# Connect to bank_loan_db
# Execute the queries from Report/BANK LOAN REPORT QUERY DOCUMENT.docx
```

### Step 3 — Load into Power BI
```bash
# Open Power BI Desktop
# Connect to PostgreSQL data source
# Load tables and build the data model
# Apply DAX measures for KPIs
# Design the 3-page dashboard
```

### Step 4 — Explore the Live Dashboard
> 🔴 **[→ Launch Live Dashboard](https://app.powerbi.com/reportEmbed?reportId=98676d40-1b49-4418-a2d8-0032bb5508c5&autoAuth=true&ctid=2e589d81-ea7a-4dc7-8fb2-84ba95cc947f)**

---

## 📈 Dataset Overview

| Field | Description |
|---|---|
| `id` | Unique loan identifier |
| `loan_amount` | Requested loan amount ($) |
| `funded_amount` | Approved funded amount ($) |
| `total_payment` | Total repayment received ($) |
| `interest_rate` | Annual interest rate (%) |
| `dti` | Debt-to-income ratio |
| `loan_status` | Fully Paid / Current / Charged Off |
| `grade` | Credit grade assigned (A–G) |
| `sub_grade` | Subgrade within each grade |
| `home_ownership` | Own / Rent / Mortgage |
| `emp_length` | Employment length (years) |
| `purpose` | Loan purpose category |
| `issue_date` | Date the loan was issued |
| `addr_state` | Borrower's state of residence |

---

## 👤 Author

<div align="center">

### Abdelaali Ennamat

**Data Analyst | Business Intelligence Enthusiast | Financial Analytics**

[![GitHub](https://img.shields.io/badge/GitHub-ABDELAALI--ENNAMAT-181717?style=for-the-badge&logo=github)](https://github.com/ABDELAALI-ENNAMAT)

*Passionate about transforming complex financial datasets into clear, compelling, and actionable insights.*

</div>

---

## 📜 License

This project is licensed under the **MIT License** — feel free to use, adapt, and build upon it with attribution.

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f3460,50:16213e,100:1a1a2e&height=120&section=footer&fontSize=20&fontColor=e94560" width="100%"/>

**⭐ If this project gave you value, a star means the world! ⭐**

*Built with 🔥 passion, 🧠 data thinking, and ☕ too much coffee.*

</div>