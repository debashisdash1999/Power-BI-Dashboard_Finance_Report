# 📊 Power BI Finance Report Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi\&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measure-blue)
![Power Query](https://img.shields.io/badge/Power%20Query-Data%20Transformation-success)
![Data Visualization](https://img.shields.io/badge/Data%20Visualization-Interactive-orange)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)

---

# 📌 Project Overview

The **Power BI Finance Report Dashboard** is an interactive business intelligence solution developed using **Microsoft Power BI Desktop** to analyze financial performance across multiple countries, products, customer segments, and time periods.

The objective of this project is to transform raw financial sales data into an executive-level dashboard that enables decision-makers to quickly evaluate business performance, identify profitable markets, monitor sales trends, and determine which products deserve future investment.

The dashboard provides an intuitive and interactive interface where business users can filter data by year and month, compare product performance, monitor profitability over time, and identify high-performing regions through geographical analysis.

This project demonstrates the complete Business Intelligence workflow, beginning with data preparation in **Power Query**, followed by data modeling, DAX calculations, relationship creation, visualization design, and dashboard formatting to deliver meaningful business insights.

---

# 🎯 Business Problem

Management requested an executive finance dashboard capable of answering several key business questions:

* Which month generated the highest profit?
* Which year performed the best financially?
* Which countries contribute the highest profits?
* Which products generate maximum sales?
* Which customer segments should receive additional business investment?
* How does profitability change over time?
* Can executives quickly filter the report for a particular year or month?

The goal was to create an easy-to-understand dashboard that converts raw transactional data into meaningful business intelligence.

---

# 📂 Dataset

**Dataset Name**

Financial Sample Dataset

**Source**

Microsoft Sample Financial Dataset

**File Format**

Excel Workbook (.xlsx)

**Primary Table**

Financials

The dataset contains sales transactions across different countries, products, customer segments, and dates.

### Main Attributes

| Category              | Columns                         |
| --------------------- | ------------------------------- |
| Product Information   | Product, Segment, Discount Band |
| Geography             | Country                         |
| Time                  | Date, Month, Month Number       |
| Sales Metrics         | Sales, Gross Sales, Profit      |
| Manufacturing Metrics | Manufacturing Price, Sale Price |
| Discounts             | Discounts                       |
| Cost Metrics          | COGS                            |
| Quantity              | Units Sold                      |

---

# 🎯 Project Objectives

The dashboard was designed to:

* Monitor financial performance over time.
* Compare profitability across countries.
* Evaluate product performance.
* Analyze customer segments.
* Create executive-level visualizations.
* Enable dynamic filtering using slicers.
* Present insights through an interactive dashboard.

---

# 🛠️ Technologies Used

| Technology                 | Purpose                        |
| -------------------------- | ------------------------------ |
| Microsoft Power BI Desktop | Dashboard Development          |
| Power Query Editor         | Data Cleaning & Transformation |
| DAX                        | Measures & Calculated Tables   |
| Data Modeling              | Relationship Creation          |
| Excel                      | Source Dataset                 |
| Interactive Visualizations | Business Analysis              |

---

# 🔄 Data Preparation (Power Query)

Before building the dashboard, the dataset was cleaned and transformed using **Power Query Editor**.

Several preprocessing steps were applied to improve data quality and make the report easier to understand.

## 1. Imported Dataset

* Connected to the Financial Sample Excel workbook.
* Loaded the Financials table into Power Query.

---

## 2. Changed Data Type

The **Units Sold** column originally contained decimal values.

Since products cannot realistically be sold in fractional quantities, the data type was changed to:

```
Whole Number
```

This improves both readability and reporting accuracy.

---

## 3. Standardized Text

The **Segment** column was converted to uppercase.

Example

Before

```
Government
```

After

```
GOVERNMENT
```

Benefits

* Improved chart readability
* Consistent labels
* Better visual appearance

---

## 4. Renamed Column

The original column

```
Month Name
```

was renamed to

```
Month
```

This simplifies the field list and improves dashboard usability.

---

## 5. Filtered Discontinued Product

The **Montana** product had been discontinued.

To ensure reports reflect only active products, all Montana records were removed from the dataset.

Remaining products include:

* Paseo
* VTT
* Velo
* Carretera
* Amarilla

This prevents discontinued products from influencing business decisions.

---

## 6. Applied Transformations

All transformation steps were recorded within Power Query's **Applied Steps**, allowing the ETL process to remain transparent, repeatable, and easy to maintain.

Applied Steps included:

* Source
* Navigation
* Changed Type
* Uppercase Text
* Renamed Columns
* Filtered Rows

---

## 7. Loaded Data

After completing the transformations:

```
Close & Apply
```

was used to load the cleaned dataset into Power BI Desktop.

---

# 🧹 Data Cleaning Summary

| Transformation       | Purpose                              |
| -------------------- | ------------------------------------ |
| Changed Data Type    | Converted Units Sold to Whole Number |
| Uppercase Formatting | Standardized Segment values          |
| Renamed Column       | Month Name → Month                   |
| Filtered Data        | Removed Montana product              |
| Loaded Data          | Imported clean dataset into Power BI |

---

# 📐 Data Modeling

A simple star-style model was created to support efficient reporting and time-based analysis.

## Fact Table

### Financials

Contains all transactional sales records including:

* Sales
* Profit
* Units Sold
* Discounts
* Gross Sales
* COGS
* Product
* Country
* Segment
* Date

---

## Dimension Table

### Calendar

A separate calendar table was created using DAX to support hierarchical date analysis.

This enables:

* Year-level reporting
* Month-level reporting
* Time intelligence
* Interactive date slicers

---

# 🧮 DAX Calculations

## Measure

```DAX
Total Units Sold =
SUM(financials[Units Sold])
```

This measure calculates the total quantity of units sold across all filtered records.

---

## Calculated Table

```DAX
Calendar =
CALENDAR(
    DATE(2013,1,1),
    DATE(2014,12,31)
)
```

The Calendar table generates a continuous date range covering the reporting period.

Benefits include:

* Date hierarchy
* Time-based filtering
* Better visualization support
* Future time intelligence calculations

---

# 🔗 Relationships

A relationship was established between:

```
Financials[Date]
        │
        ▼
Calendar[Date]
```

Relationship Type

```
One-to-Many
```

This relationship enables accurate filtering between the Calendar table and the Financials table while supporting date hierarchies and slicers.

---

# 📁 Project Workflow

```text
Excel Financial Dataset
          │
          ▼
Power Query
(Data Cleaning)
          │
          ▼
Data Modeling
(Calendar Table + Relationship)
          │
          ▼
DAX Calculations
          │
          ▼
Interactive Dashboard
          │
          ▼
# 📊 Dashboard Design
```
The Finance Dashboard was designed as an executive summary page that provides stakeholders with a quick overview of the organization's financial performance.

The report combines interactive visualizations, geographic analysis, trend analysis, and product performance metrics into a single dashboard. Users can dynamically filter the report by year and month, making it easy to compare performance across different time periods.

---

# 📌 Dashboard Components

The dashboard consists of the following major components:

| Visual                 | Purpose                    |
| ---------------------- | -------------------------- |
| Executive Title        | Dashboard Header           |
| Line Chart             | Profit Trend Over Time     |
| Map Visual             | Profit by Country          |
| Clustered Column Chart | Sales by Product & Segment |
| Date Slicer            | Interactive Time Filtering |

---

# 📈 Dashboard Visualizations

## 1️⃣ Executive Dashboard Title

The report begins with a clean executive header.

**Title**

```text
Executive Summary – Finance Report
```

The title provides a clear description of the dashboard's purpose and establishes an executive reporting style.

---

## 2️⃣ Profit by Month & Year (Line Chart)

### Objective

Analyze how profit changes over time and identify the most profitable month.

### Visualization Type

* Line Chart

### Fields Used

| Field          | Role   |
| -------------- | ------ |
| Date Hierarchy | X-Axis |
| Profit         | Y-Axis |

### Insights

The line chart reveals monthly profit trends over a two-year period.

Business users can quickly identify:

* Seasonal trends
* Growth patterns
* Profit fluctuations
* Highest-performing months

### Key Finding

**December 2014** generated the highest overall profit during the reporting period.

---

## 3️⃣ Profit by Country (Map Visualization)

### Objective

Identify the geographical regions contributing the highest profits.

### Visualization Type

* Bubble Map

### Fields Used

| Field   | Role        |
| ------- | ----------- |
| Country | Location    |
| Profit  | Bubble Size |

### Insights

Each country is represented by a bubble.

Larger bubbles indicate higher profits.

The map enables management to compare regional performance at a glance.

### Business Observation

European countries significantly outperform North American markets.

The highest-performing countries include:

* France
* Germany

This geographic visualization supports regional investment and expansion decisions.

---

## 4️⃣ Sales by Product & Customer Segment

### Objective

Compare product sales across different customer segments.

### Visualization Type

* Clustered Column Chart

### Fields Used

| Field   | Purpose |
| ------- | ------- |
| Product | X-Axis  |
| Sales   | Values  |
| Segment | Legend  |

### Business Value

This visualization enables stakeholders to identify:

* Top-selling products
* Best-performing customer segments
* Sales distribution
* Product popularity

### Major Finding

The **Paseo** product consistently generates the highest sales.

Customer segments contributing the strongest revenue include:

* Small Business
* Government

These insights help prioritize future investments and marketing strategies.

---

## 5️⃣ Interactive Date Slicer

### Objective

Allow users to filter the dashboard dynamically.

### Visualization Type

* Hierarchical Date Slicer

### Supports

* Year
* Month

Users can:

* Analyze a specific year
* Compare monthly performance
* Filter every visual simultaneously
* Focus on individual reporting periods

This significantly improves dashboard interactivity and user experience.

---

# 🎨 Dashboard Formatting

To enhance readability and create an executive-style report, several formatting improvements were applied.

## Executive Theme

The report uses the **Executive Theme** to provide a clean, professional appearance.

---

## Visual Titles

Each visualization includes:

* Descriptive title
* Increased font size
* Consistent formatting
* Improved readability

Examples:

* Profit by Month and Year
* Profit by Country
* Sales by Product and Segment

---

## Shadow Effects

Shadow effects were enabled for all primary visuals to create depth and improve visual distinction.

Applied to:

* Line Chart
* Map
* Clustered Column Chart

---

## Background Shapes

Rectangular shapes were added behind dashboard components to improve visual organization.

Benefits include:

* Cleaner layout
* Better spacing
* Improved visual hierarchy
* Professional appearance

---

## Dashboard Header

The dashboard title is placed over a blue rectangular banner with white text to create a modern executive reporting style.

---

# 📊 Dashboard Features

The completed dashboard provides several interactive capabilities.

### ✔ Interactive Filtering

Users can instantly filter all visuals using the date slicer.

---

### ✔ Cross-Filtering

Selecting data in one visual automatically updates the remaining visuals.

---

### ✔ Geographic Analysis

The map visual enables quick comparison of financial performance across countries.

---

### ✔ Trend Analysis

The line chart makes it easy to identify:

* Seasonal changes
* Monthly trends
* Profit peaks
* Revenue fluctuations

---

### ✔ Product Performance Analysis

The clustered column chart highlights:

* Best-selling products
* Customer segment performance
* Sales distribution
* Business opportunities

---

# 📌 Key Business Insights

After analyzing the financial data, several important insights were identified.

---

## 📈 Highest Profit Month

**December 2014** recorded the highest profit during the reporting period.

This indicates a strong year-end sales performance and possible seasonal demand.

---

## 🌍 Best Performing Region

Europe generated the highest overall profits.

Top-performing countries include:

* France
* Germany

These regions present strong opportunities for continued business investment.

---

## 🏆 Best Performing Product

The **Paseo** product consistently achieved the highest sales.

This suggests strong customer demand and makes it a priority product for future growth initiatives.

---

## 👥 Highest Performing Customer Segments

The most profitable customer segments were:

* Government
* Small Business

These segments should remain key targets for future marketing and sales strategies.

---

# 💼 Business Recommendations

Based on the dashboard analysis, the following recommendations can be made:

* Continue investing in the Paseo product line.
* Expand business operations in high-performing European markets.
* Focus marketing campaigns on Government and Small Business customers.
* Monitor monthly profit trends to better prepare for seasonal demand.
* Utilize interactive dashboard filtering for faster executive decision-making.

---

# 🚀 Business Value Delivered

This dashboard transforms raw financial data into actionable business intelligence by enabling stakeholders to:

* Monitor financial performance in real time.
* Identify profitable products and regions.
* Understand customer segment behavior.
* Make data-driven investment decisions.
* Improve strategic planning through interactive reporting.

# 🧠 Skills Demonstrated

This project demonstrates a complete end-to-end Business Intelligence workflow using Microsoft Power BI.

### Business Intelligence

* Executive Dashboard Development
* Interactive Data Visualization
* Business Performance Analysis
* KPI Reporting
* Financial Analytics
* Self-Service BI

### Data Preparation

* Power Query (ETL)
* Data Cleaning
* Data Transformation
* Data Type Conversion
* Text Standardization
* Data Filtering

### Data Modeling

* Star Schema Concepts
* Fact & Dimension Tables
* Relationship Creation
* Calendar Table
* Date Hierarchies

### DAX

* Measures
* Calculated Tables
* Aggregation Functions
* Time-Based Data Modeling

### Visualization Techniques

* Line Chart
* Map Visualization
* Clustered Column Chart
* Interactive Slicers
* Executive Dashboard Design

---

# 🖼 Dashboard Preview

> Add screenshots after uploading your project to GitHub.

## Executive Dashboard

```markdown
![Finance Dashboard](Images/Dashboard.png)
```

---

## Data Model

```markdown
![Data Model](Images/Data%20Model.png)
```

---

## Profit Trend

```markdown
![Profit Trend](Images/Profit%20by%20Month.png)
```

---

## Country Analysis

```markdown
![Country Analysis](Images/Country%20Analysis.png)
```

---

## Product Analysis

```markdown
![Product Analysis](Images/Product%20Analysis.png)
```

---

# 📊 Project Highlights

✔ Built an interactive executive finance dashboard.

✔ Performed data cleaning and preprocessing using Power Query.

✔ Created DAX measures and a calculated Calendar table.

✔ Established relationships for efficient data modeling.

✔ Developed interactive visualizations for financial analysis.

✔ Implemented dynamic date filtering using slicers.

✔ Designed a clean, executive-style report layout.

✔ Delivered actionable business insights from financial data.

---

# 🎯 Learning Outcomes

Throughout this project, I gained hands-on experience in:

* Building professional Power BI dashboards
* Transforming raw datasets using Power Query
* Writing DAX measures and calculated tables
* Creating data models with relationships
* Applying interactive filtering using slicers
* Designing business-focused reports
* Presenting insights through effective visual storytelling

---

# 🚀 Future Enhancements

Potential improvements for future versions of this dashboard include:

* Additional KPI cards for Sales, Profit, and Gross Margin
* Year-over-Year (YoY) Growth Analysis
* Month-over-Month (MoM) Trend Analysis
* Profit Margin Analysis
* Dynamic Tooltips
* Drill-through Pages
* Bookmarks and Navigation Buttons
* Row-Level Security (RLS)
* Conditional Formatting
* Forecasting and Trend Lines
* Power BI Service Deployment
* Automated Data Refresh
* Mobile-Optimized Dashboard

---

# 📌 Key Takeaways

This project demonstrates how Power BI can transform raw financial data into meaningful business insights through effective data preparation, modeling, visualization, and interactive reporting.

By integrating Power Query, DAX, data modeling, and visualization techniques, the dashboard enables stakeholders to monitor business performance, identify profitable regions and products, and make informed strategic decisions.

---

# 🛠 Software & Technologies

* Microsoft Power BI Desktop
* Microsoft Excel
* Power Query
* DAX (Data Analysis Expressions)

---

# 📖 References

* Microsoft Power BI Documentation
* Microsoft Financial Sample Dataset

---

# 🤝 Contributing

Contributions, suggestions, and improvements are welcome.

If you have ideas to enhance this project, feel free to fork the repository and submit a pull request.

---

# ⭐ Support

If you found this project helpful, consider giving it a ⭐ on GitHub.

Your support is greatly appreciated.

---

# 👨‍💻 Author

**Choudhury Debashis Dash**

**Snowflake Data Engineer | Power BI Developer | SQL | Data Analytics**

GitHub: **https://github.com/YourGitHubUsername**

LinkedIn: **https://linkedin.com/in/YourLinkedInUsername**

Email: **[your-email@example.com](mailto:your-email@example.com)**

---

# 📄 License

This project is licensed under the **MIT License**.

Feel free to use this project for learning and educational purposes.

---

## ⭐ If you enjoyed this project, don't forget to star the repository!

