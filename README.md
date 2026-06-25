# 📊 Power BI Finance Report Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi\&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-blue)
![Power Query](https://img.shields.io/badge/Power%20Query-ETL-success)

## 📌 Project Overview

This project is an interactive **Finance Dashboard** built using **Microsoft Power BI Desktop** to analyze financial performance across different countries, products, customer segments, and time periods.

The dashboard transforms raw financial data into meaningful business insights using **Power Query**, **DAX**, **data modeling**, and interactive visualizations.

---

## 🎯 Business Objectives

The dashboard answers the following business questions:

* Which month generated the highest profit?
* Which country contributes the highest profit?
* Which product performs the best?
* Which customer segment generates the highest sales?
* How does profit change over time?

---

## 🛠 Tools & Technologies

* Microsoft Power BI Desktop
* Power Query
* DAX (Data Analysis Expressions)
* Microsoft Excel

---

## 🔄 Data Preparation

The dataset was cleaned and transformed using **Power Query** by:

* Converting **Units Sold** to Whole Number
* Formatting **Segment** values to uppercase
* Renaming **Month Name** to **Month**
* Removing the discontinued **Montana** product
* Loading the cleaned data into Power BI

---

## 📐 Data Modeling

A separate **Calendar** table was created using DAX and linked to the Financials table to enable date-based analysis and slicers.

### DAX Measure

```DAX
Total Units Sold =
SUM(financials[Units Sold])
```

### Calendar Table

```DAX
Calendar =
CALENDAR(
    DATE(2013,1,1),
    DATE(2014,12,31)
)
```

---

## 📊 Dashboard Visualizations

* 📈 **Line Chart** – Profit by Month & Year
* 🥧 **Pie Chart** – Profit Distribution by Country
* 📊 **Clustered Column Chart** – Sales by Product & Segment
* 🎛 **Date Slicer** – Filter dashboard by Year and Month

---

## 📈 Key Insights

* **December 2014** recorded the highest profit.
* **France** and **Germany** contributed the highest share of profit.
* **Paseo** was the top-performing product.
* **Government** and **Small Business** were the most profitable customer segments.

---

## 🚀 Skills Demonstrated

* Power BI Dashboard Development
* Power Query (ETL)
* Data Cleaning & Transformation
* Data Modeling
* DAX Measures
* Interactive Visualizations
* Financial Data Analysis
* Business Intelligence Reporting

---

## 📂 Project Structure

```text
Power BI Dashboard_Finance_Report/
│
├── Finance Report.pbix
├── Financial Sample.xlsx
├── README.md
└── Images/
    └── Dashboard.png
```

---

## 🖼 Dashboard Preview

<img width="886" height="499" alt="image" src="https://github.com/user-attachments/assets/0f6a47ba-a99f-4701-bf0c-f8addb8546b5" />

---

## 🔮 Future Improvements

* KPI Cards
* Drill-through Reports
* Dynamic Tooltips
* Year-over-Year Analysis
* Power BI Service Deployment
