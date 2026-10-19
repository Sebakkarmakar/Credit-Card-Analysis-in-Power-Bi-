<img width="873" height="490" alt="customer_report" src="https://github.com/user-attachments/assets/0759e4e4-6476-4eca-a92f-4d8c03b24db5" /># 💳 Credit Card Analytics Dashboard | SQL + Power BI

An interactive weekly dashboard that turns raw credit card **transaction** and **customer** data from a SQL database into clear business insights.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 Table of Contents
- [Project Objective](#-project-objective)
- [Dashboard Preview](#-dashboard-preview)
- [Tools & Skills](#-tools--skills)
- [Project Workflow](#-project-workflow)
- [DAX Measures](#-dax-measures)
- [Key Insights](#-key-insights)
- [Recommendations](#-recommendations)
- [Repository Structure](#-repository-structure)
- [How to Use](#-how-to-use)
- [Author](#-author)

---

## 🎯 Project Objective

Build a comprehensive weekly credit card dashboard that gives stakeholders **near real-time visibility** into key performance metrics and trends, so they can monitor and analyze credit card operations effectively.

**Business questions answered**
- How much revenue, transaction amount and interest does the portfolio generate?
- Which card categories, customer segments and states drive revenue?
- How do revenue and spend change by quarter and week?
- How do customers spend (expense type, payment method)?
- What are the activation and delinquency rates?

---

## 📊 Dashboard Preview

### 1️⃣ Customer Report
<img width="873" height="490" alt="customer_report" src="https://github.com/user-attachments/assets/00d9fd9f-f8e0-40bd-a6b6-1af8e02e8dd8" />



**What it shows:** revenue by year, month and gender; revenue by marital status, income group, job, age group, top 5 states and education level; job-wise revenue, transaction amount and interest table.

### 2️⃣ Transaction Report
<img width="884" height="491" alt="transaction_report" src="https://github.com/user-attachments/assets/25de6b03-6531-41d8-895c-6878658c973c" />

**What it shows:** revenue and transaction amount by quarter; revenue by card category, expense type, payment method (swipe / chip / online), customer job and education level.

> **Interactivity:** slicers for **Card Category**, **Quarter**, **Week Start Date** and **Education Level**; every visual cross-filters.

---

## 🛠 Tools & Skills

| Area | Details |
|---|---|
| Database | SQL (table creation, CSV import) |
| BI Tool | Power BI Desktop |
| Language | DAX (calculated columns with `SWITCH`) |
| Skills | Data modelling, data cleaning, KPI design, data storytelling |

---

## 🔄 Project Workflow

1. **Prepare data**: clean and format the customer and transaction CSV files.
2. **Create tables in SQL**: define tables for customer details and transactions.
3. **Import CSV files into SQL**: load the data into the database.
4. **Connect Power BI to SQL**: import the tables and build relationships.
5. **Create DAX columns**: `AgeGroup` and `IncomeGroup` (see below).
6. **Design the dashboard**: two report pages with KPI cards, charts and slicers.
7. **Analyze and share insights**: summarize findings and recommendations.

---

## 🧮 DAX Measures

**Age Group**
```DAX
AgeGroup =
SWITCH(
    TRUE(),
    'public cust_detail'[customer_age] < 30, "20-30",
    'public cust_detail'[customer_age] >= 30 && 'public cust_detail'[customer_age] < 40, "30-40",
    'public cust_detail'[customer_age] >= 40 && 'public cust_detail'[customer_age] < 50, "40-50",
    'public cust_detail'[customer_age] >= 50 && 'public cust_detail'[customer_age] < 60, "50-60",
    'public cust_detail'[customer_age] >= 60, "60+",
    "unknown"
)
```

**Income Group**
```DAX
IncomeGroup =
SWITCH(
    TRUE(),
    'public cust_detail'[income] < 35000, "Low",
    'public cust_detail'[income] >= 35000 && 'public cust_detail'[income] < 70000, "Med",
    'public cust_detail'[income] >= 70000, "High",
    "unknown"
)
```

---

## 💡 Key Insights

### Headline KPIs
| Metric | Value |
|---|---|
| Total Revenue | **55M** |
| Total Transaction Amount | **45M** |
| Total Interest Earned | **7.84M** |
| Activation Rate | **57.5%** |
| Delinquent Rate | **6.06%** |

### Findings
- 👥 **Gender:** male customers contribute more revenue (**30M**) than female customers (**25M**).
- 💳 **Card category:** **Blue** cards generate about **83%** of revenue (46M). **Blue and Silver** together account for **93%** of all transactions.
- 📅 **Quarterly trend:** revenue is stable at 13.3M to 14.2M per quarter, peaking in **Q3** and lowest in **Q4**.
- 🗺 **Geography:** **TX, NY and CA** contribute about **68%** of revenue.
- 🎂 **Age:** the **40–50** age group is the largest revenue segment.
- 💼 **Job:** Businessmen (17M) and White-collar (10M) lead.
- 🛒 **Spending:** Bills (14M) and Entertainment (10M) are the top expense types.
- 🔄 **Payment method:** **Swipe** is about 64% of revenue (35M), Chip 17M, while **Online is only 3M**.
- 🎓 **Education:** Graduates (22M) and High School (11M) bring the most revenue.

---

## ✅ Recommendations

1. Upsell **Blue** card holders to **Gold / Platinum** with targeted offers.
2. Investigate the **Q4 revenue dip**.
3. Grow **online spending**, the least-used channel.
4. Monitor the **6.06% delinquency rate** closely.
5. Run campaigns to lift the **activation rate** above 57.5%.
6. Reduce dependence on the top 3 states and the 40–50 age group.

---

## 📁 Repository Structure

```
Credit-Card-Analysis-in-Power-BI/
│
├── data/                  # CSV files (customer and transaction data)
├── sql/                   # SQL scripts for table creation and import
├── powerbi/               # Power BI file (.pbix)
├── images/                # Dashboard screenshots
│   ├── customer_report.png
│   └── transaction_report.png
├── presentation/          # PowerPoint presentation
└── README.md
```

---

## 🚀 How to Use
1. Clone this repository:
2. Create the tables in your SQL database using the scripts in `/sql`.
3. Import the CSV files from `/data` into those tables.
4. Open the `.pbix` file in **Power BI Desktop**.
5. Update the data source connection (**Home → Transform data → Data source settings**) to point to your database.
6. Click **Refresh** and explore the dashboard.

---

## 🎥 Project Walkthrough

- Video explanation: [Add link here]
- Presentation: [Credit_Card_Dashboard_Presentation.pptx](https://github.com/user-attachments/files/33674955/Credit_Card_Dashboard_Presentation.pptx)


---

## 🙏 Acknowledgements

Thanks to **[Codebasics](https://codebasics.io/)** for the learning and inspiration behind this project.


## 👤 Author

**Sebak Karmakar**, Aspiring Data Analyst

- 💼 LinkedIn: [[Add My profile link](https://www.linkedin.com/in/sebak-karmakar-b80246256/)]

⭐ If you found this project useful, please give it a star!
