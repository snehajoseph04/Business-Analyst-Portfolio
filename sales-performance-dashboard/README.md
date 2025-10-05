## 🚀 Power BI Sales Performance Dashboard

This repository showcases a comprehensive **Sales Performance Analysis Dashboard** built using **Microsoft Power BI**. The project focuses on transforming raw transactional data into an interactive, visually appealing report that enables data-driven decision-making for sales management and strategic planning.

-----

### 📊 Skills and Tools Demonstrated

This project highlights end-to-end Business Intelligence (BI) skills:

| Category | Tools/Skills | Description |
| :--- | :--- | :--- |
| **Data Sourcing & ETL** | **Power Query (M Language)** | Data cleaning, type conversion, column splitting, and creation of a dedicated Calendar/Date Dimension table. |
| **Data Modeling** | **Star Schema** | Establishing robust relationships between fact and dimension tables (Sales Fact, Date Dim, Product Dim, Sales Rep Dim) for efficient filtering and calculation context. |
| **Analytical Language** | **DAX (Data Analysis Expressions)** | Creation of **Key Performance Indicators (KPIs)** and complex time-intelligence calculations. |
| **Visualization** | **Power BI Desktop** | Designing a user-friendly, interactive report with custom visuals, drill-through pages, and slicers. |

-----

### 🔑 Key Metrics and Insights

The dashboard delivers insights across three main pages (e.g., *Executive Summary, Product Deep Dive, Regional Performance*), tracking essential KPIs:

  * **Total Revenue** and **Total Target**: Monitoring overall business scale.
  * **Target Variance (%):** Calculated as `([Total Revenue] - [Total Target]) / [Total Target]`, used to gauge success against set goals.
  * **Year-over-Year (YoY) Growth:** Showing the percentage change in revenue compared to the previous period.
  * **Top N Analysis:** Dynamic ranking of Sales Representatives and Products by Revenue.
  * **Performance vs. Target Visualization:** Conditional formatting used to highlight areas lagging behind targets (Red/Green or Icons).

-----

### 🛠️ Technical Process Highlights

1.  **Data Transformation (Power Query):** The initial sales data (`Raw_Sales_Data.csv`) was loaded. Steps included:
      * Unpivoting/pivoting columns for flexibility.
      * Creating columns for **Month Name**, **Quarter**, and **Year** from the Date column.
      * Handling potential data quality issues (e.g., null values or incorrect data types).
2.  **DAX Implementation:**
      * **Calculated Measures:** All performance metrics (Revenue, Target, Variance) were implemented as **Measures** for optimal performance and correct context transition during filtering.
      * **Time Intelligence:** Used DAX functions like `CALCULATE`, `DATEADD`, and `TOTALYTD` to perform comparative analysis.
3.  **Report Design:** The dashboard was designed with a clear, concise visual hierarchy, utilizing tooltips and drill-through actions to enhance user exploration.

-----

### 📂 Repository Contents and Access

| File/Folder | Description |
| :--- | :--- |
| `report/Sales_Dashboard.pbix` | The main Power BI Desktop file. **(Requires Power BI Desktop to open)** |
| `visuals/Dashboard_Preview.png` | \*\*\*\* A high-resolution static screenshot of the final dashboard pages. |
| `data/Raw_Sales_Data.csv` | The source data file used to build the report. |
