# Green-Planet-Co. Sales-Performance-Analytics

## **1. Background and Overview**
Green Planet Co. is a large-scale plant company that sells a variety of products across multiple regions. To analyze sales performance, profitability, and year-over-year trends, we developed an interactive Power BI dashboard. The report provides deep insights into sales trends, gross profit margins, and product performance at different levels of granularity (country, product, and account level).

The key objectives of this analysis are:
- Understanding sales trends across different time periods (YTD vs. PYTD).
- Identifying underperforming regions and products.
- Analyzing account profitability to optimize sales strategies.
- Enabling dynamic filtering and visualization to facilitate business decisions.

## **2. Data Structure and Overview**
The dataset consists of three core tables:

- **Fact_Sales**: Contains sales invoices, including revenue, cost of goods sold (COGS), and quantity.
- **Account**: Holds customer-specific details.
- **Plant_Hierarchy**: Provides a structured view of the product categories, enabling drill-down analysis.

Additionally, a **Dim_Date** table was created using a DAX function to facilitate time-based calculations.

### **Files Required for Full Analysis:**
- **Data Source:** `Plant_DTS.xls` (Excel file with sales, account, and product hierarchy data)
- **Power BI Dashboard:** `image.png` (Snapshot of the dashboard)
- **Power BI File:** `PerformReport.pbix`

## **3. Executive Summary**
- **Sales Performance**: The company’s **YTD sales stand at $3.57M**, slightly **declining by $135.89K (-3.6%)** compared to the PYTD ($3.71M).
- **Gross Profit Margin**: **39.15%**, indicating a stable profitability percentage.
- **Bottom 10 Markets**: Canada, Colombia, and Croatia experienced the largest declines in sales compared to PYTD.
- **Product Performance**: Sales varied across product types, with notable declines in outdoor plant categories in March and April.
- **Account Profitability**: Segmentation analysis suggests a strong correlation between high-value accounts and high GP%.

## **4. Insights Deep Dive**
![Sales Performance Dashboard](https://github.com/PranitHande7/Green-Planet-Co.---Sales-Performance-Analytics/blob/main/performreport.png)

### **1. Year-Over-Year Performance (YTD vs PYTD)**
- The overall sales **declined by $135.89K** compared to the same period last year.
- Some regions, including **Canada (-73.71K) and Colombia (-61.12K),** saw major drops in sales.
- Sales peaked in **March (1.19M) but dropped significantly in April (0.39M),** requiring further investigation.

### **2. Product & Regional Trends**
- The **outdoor plant category** saw the largest decline in PYTD, leading to the overall revenue dip.
- Countries like **Croatia, Germany, and Hungary** showed declining trends, hinting at potential market challenges.

### **3. Account Profitability**
- **Higher GP%** is generally associated with higher-value accounts.
- Identifying low-GP% accounts and optimizing pricing strategies could improve profitability.

## **5. Recommendations**
🔹 **Target Underperforming Markets**  
   - Canada and Colombia need **targeted marketing efforts** or pricing adjustments to recover lost sales.  
   - Consider **customer segmentation** to offer personalized incentives.  

🔹 **Investigate Seasonal Trends**  
   - The decline in outdoor plant sales suggests **seasonal demand shifts**; aligning inventory accordingly could optimize revenue.  

🔹 **Account-Level Strategy**  
   - **Reassess pricing strategies** for low-GP% accounts to maximize profitability.  
   - Implement **customer retention programs** for high-value accounts.  

---

## **DAX Measures and Modeling Details**
For technical teams, the following are the key DAX measures that drive the report:

### **1. Creating a Date Table**
```DAX
Dim_Date = CALENDAR(Date(2022,01,01), Date(2024,12,31))
```
*Creates a continuous date range for time-based analysis.*

### **2. Past Period Comparisons**
```DAX
PYTD_Sales = CALCULATE([Sales], SAMEPERIODLASTYEAR(Dim_Date[Date]), Dim_Date[Inpast] = TRUE)
```
*Ensures past-year sales comparisons exclude future months with no data.*

### **3. Year-To-Date (YTD) Calculations**
```DAX
YTD_Sales = TOTALYTD([Sales], Fact_Sales[Date_Time])
```
*Calculates cumulative sales from the start of the year to the current date.*

### **4. YTD vs. PYTD Switch**
```DAX
YTD vs PYTD = [S_YTD] - [S_PYTD]
```
*Derives the performance difference between YTD and PYTD values.*

### **5. Gross Profit Calculation**
```DAX
GP = Sales - COGs
```
*Determines the profit generated after deducting costs.*

### **6. Dynamic Measure Switching (Sales, GP, Quantity)**
```DAX
S_YTD =
VAR selected_value = SELECTEDVALUE(Slc_Values[Values])
VAR result = SWITCH( selected_value,
    "Sales", [YTD_Sales],
    "Gross Profit", [YTD_GrossProfit],
    "Quantity", [YTD_Quantity],
    BLANK()
)
RETURN
result
```
*Allows users to switch between different performance metrics dynamically.*

---


