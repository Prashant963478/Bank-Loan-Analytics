# 🏦 Bank Loan Analytics Dashboard — Power BI

A comprehensive **Power BI dashboard** built to analyze bank lending performance, monitor loan portfolio health, and support data-driven decision-making using real-world financial loan data.

---

## 📊 Project Overview

This project involves building an end-to-end **Bank Loan Report** with two interactive dashboard pages — **Summary** and **Overview** — designed to track key lending KPIs, identify risk, and explore borrower trends across a dataset of 38,576 loan records worth **~$435 million**.

---

## 📸 Screenshots

### Dashboard 1 — Summary
![Summary Dashboard](screenshots/summary_dashboard.png)

### Dashboard 2 — Overview
![Overview Dashboard](screenshots/overview_dashboard.png)

---

## 🗂️ Dataset Details

| Field | Description |
|---|---|
| **Records** | 38,576 loan applications |
| **Columns** | 23 (borrower info, loan terms, repayment data) |
| **Key Fields** | Loan Amount, Interest Rate, DTI, Grade, Loan Status, Purpose, Employment Length, Annual Income |

---

## 📁 Project Structure

```
Bank-Loan-Analytics-Dashboard/
│
├── Financial_loan_data.xlsx            # Raw dataset
├── Bank_Loan_Analytics_Dashboard.pbix  # Power BI dashboard file
├── Bank_Loan_Description.pdf           # Column descriptions & business context
└── README.md
```

---

## 📌 Dashboard Pages

### Page 1 — Summary
Tracks high-level KPIs and loan health at a glance:

- ✅ Total Loan Applications
- ✅ Total Funded Amount (~$435.7M)
- ✅ Total Amount Received (~$473M)
- ✅ Average Interest Rate
- ✅ Average Debt-to-Income (DTI) Ratio
- ✅ **Good Loan vs Bad Loan classification**
  - Good Loans (Fully Paid + Current): **86.1%**
  - Bad Loans (Charged Off): **13.9%**

### Page 2 — Overview
Visual breakdown of lending trends and borrower segments:

- 📈 Monthly loan application trends
- 🗺️ State-wise loan distribution (US map)
- 🎯 Loan purpose breakdown (Debt Consolidation = 47%)
- 🏠 Home ownership analysis
- 📋 Grade & Sub-grade risk segmentation
- 👔 Employment length impact on loans
- ⏱️ Term-based analysis (36 vs 60 months)

---

## ⚙️ Tools & Technologies

| Tool | Usage |
|---|---|
| **Power BI Desktop** | Dashboard design & visualization |
| **DAX** | KPI measures, Good/Bad loan classification, MoM calculations |
| **Power Query** | Data cleaning & transformation |
| **Microsoft Excel** | Source data (.xlsx) |

---

## 🔑 Key DAX Measures

```dax
-- Good Loan %
Good Loan % = 
DIVIDE(
    CALCULATE(COUNT(loan_data[ID]), loan_data[LOAN_STATUS] IN {"Fully Paid", "Current"}),
    COUNT(loan_data[ID])
)

-- Bad Loan %
Bad Loan % = 
DIVIDE(
    CALCULATE(COUNT(loan_data[ID]), loan_data[LOAN_STATUS] = "Charged Off"),
    COUNT(loan_data[ID])
)

-- Month-over-Month Loan Applications
MoM Applications = 
DIVIDE([Current Month Apps] - [Previous Month Apps], [Previous Month Apps])
```

---

## 💡 Key Insights

- **Debt Consolidation** is the most common loan purpose at 47% of all applications
- **86.1%** of loans are classified as Good Loans, indicating a relatively healthy portfolio
- Borrowers with **Grade A** have the lowest default risk; Grade G has the highest
- **60-month term** loans tend to have higher interest rates and default rates
- States like **CA, NY, TX, FL** account for the highest loan volumes

---

## 🚀 How to Use

1. Download and open `Bank_Loan_Analytics_Dashboard.pbix` in **Power BI Desktop**
2. If needed, re-link the data source to `Financial_loan_data.xlsx`
3. Use slicers to filter by **Loan Grade, Purpose, State, Term, or Home Ownership**
4. Navigate between **Summary** and **Overview** pages using the page buttons

---

## 👤 Author

**Prashant**  
B.Tech Computer Science | GLA University, Mathura (2026)  
📧 [your email]  
🔗 [LinkedIn Profile]  

---

## 📄 License

This project is for educational and portfolio purposes only.
