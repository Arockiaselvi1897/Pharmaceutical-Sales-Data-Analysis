# Healthcare-Sales-Analysis

## **Project Overview**

This project presents an end-to-end **Healthcare Sales Analysis** using **Power BI**, starting from data cleaning, transformation, data modeling, DAX calculations, and interactive visualizations. The goal is to uncover actionable insights on sales trends, customer segments, product performance, and regional distribution.


## **Dataset Used**

pharma-data.csv - Contains Distributor, Customer, Product Details, Sales, Pricing, Channel, Geography, and Team Information.


## **Data Cleaning & Transformation (Power Query Editor)**

### Steps Performed

1. Imported dataset into Power BI.
2. Transformed the table in **Power Query Editor**.
3. Corrected data types:

   * Latitude, Longitude, Quantity → Number
   * Price, Sales → Fixed Decimal Number
   * Year → Whole Number
4. Converted **Sales Team** column to UPPERCASE.
5. Verified duplicates, missing values using filters and column quality.
6. Rounded Latitude & Longitude to 2 decimals.
7. Renamed:

   * *Price → Unit Price*
   * *Sales → Sales Amount*
8. Added new calculated columns:

   * **Sales Category** (Above/Below Average)
   * **Customer Segment** (Premium / Regular / New)
9. Added Index column → Renamed to **Sales Reference ID** → Converted to Text.
10. Created **Location** by merging City & Country.
11. Grouped & aggregated tables:

* Total Purchase Amount by Distributor & Customer
* Total Sales by Product Name
* Total Number of Sales by Location
* Total Sales Amount by Month & Year

12. Applied all transformations and loaded data into Power BI.


## **DAX Calculations**

### **Calculated Columns**

* **Channel Type**
  `Channel Type = 'Pharma Sales Data'[Channel] & " " & 'Pharma Sales Data'[Sub-channel]`

* **Sales Team Details**
  *(Summarize sales performance by team, manager, rep)*

### **Measures**

* Total Number of Sales
  `Total Number of Sales = COUNTROWS('Pharma Sales Data')`

* Average Sales Amount
  `Average Sales Amount = AVERAGE('Sales Details by Country'[Sales Amount])`

* Total Sales Amount
  `Total Sales Amount = SUM('Sales Details by Country'[Sales Amount])`

### **Calculated Tables**

* **Sales Details by Country**
  Using `SUMMARIZECOLUMNS()` for Distributor, Customer, City, Country, Sales Amount, Reference ID.


## **Data Modeling**

* Cleaned and optimized relationships.
* Ensured proper data types and summarization settings.
* Used star-schema-style modeling for efficient reporting.


## **Visualizations Created**

### **1. Sales by Year & Channel (Clustered Column Chart)**

Shows yearly comparison between **Hospital** and **Pharmacy** sales.

### **2. Sales by Country (Map Visual)**

Identifies regional sales distribution using bubble size.

### **3. Sales by Month & Year (Area Chart)**

Highlights overall monthly trends over multiple years.

### **4️. Sales by Sub-Channel (Donut Chart)**

Breakdown of sales by sub-channel segments.

### **5️. Sales by Sales Team & Product Class (100% Stacked Bar Chart)**

Compares how teams perform across product categories.

### **6️. Sales by Managers (Funnel Chart)**

Shows top contributing managers.

### **7️. KPI Cards**

* Total Sales Amount
* Total Number of Sales

### **8️. Slicers**

* Country
* Distributor
* Product Class
  All visuals update dynamically for interactive analysis.


## **Key Insights**

* Identified high-performing product classes and regions.
* Segmented customers into Premium, Regular, and New.
* Highlighted team and manager contributions.
* Monthly & yearly trends revealed seasonal patterns.
* Aggregated distributor-level customer purchases for deeper analysis.

## **Tools Used**

* **Power BI Desktop**
* **Power Query Editor**
* **DAX (Data Analysis Expressions)**
* **Excel** (for initial verification)
