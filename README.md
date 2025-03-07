# Green-Planet-Co. Sales-Performance-Analytics

# Project Background
Green Planet Co. is a large-scale plant company that sells a variety of products across multiple regions. To analyze sales performance, profitability, and year-over-year trends, we developed an interactive Power BI dashboard. The report provides deep insights into sales trends, gross profit margins, and product performance at different levels of granularity (country, product, and account level).

The key objectives of this analysis are:
- Understanding sales trends across different time periods YTD(Year to date) vs PYTD(Prior year to date).
- Identifying underperforming regions and products.
- Analyzing account profitability to optimize sales strategies.
- Enabling dynamic filtering and visualization to facilitate business decisions.

An interactive PowerBI dashboard can be viewed [here](https://github.com/PranitHande7/Green-Planet-Co.---Sales-Performance-Analytics/blob/main/PerformReport.pbix).

# Data Structure and Initial Checks
The dataset consists of three core tables:

- **Fact_Sales**: Contains sales invoices, including revenue, cost of goods sold (COGS), and quantity.
- **Account**: Holds customer-specific details.
- **Plant_Hierarchy**: Provides a structured view of the product categories, enabling drill-down analysis.

Additionally, a **Dim_Date** table was created using a DAX function to facilitate time-based calculations.

 ![image11](https://github.com/PranitHande7/Green-Planet-Co.-Sales-Performance-Analytics/blob/main/Data.png)

# Executive Summary
- **Sales Performance**: The company’s **YTD sales stand at $3.57M**, slightly **declining by $135.89K (-3.6%)** compared to the PYTD ($3.71M).
- **Gross Profit Margin**: **39.15%**, indicating a stable profitability percentage.
- **Bottom 10 Markets**: Canada, Colombia, and Croatia experienced the largest declines in sales compared to PYTD.
- **Product Performance**: Sales varied across product types, with notable declines in outdoor plant categories in March and April.
- **Account Profitability**: Segmentation analysis suggests a strong correlation between high-value accounts and high GP%.

# Overview of Findings

In this snapshot, the selected filter is Sales, meaning all metrics displayed are based on total revenue. The available filters allow switching between Gross Profit and Quantity to analyze performance from different perspectives.

Year-to-Date (YTD) Sales: $3.57M, reflecting total sales so far in 2024.
Prior Year-to-Date (PYTD) Sales: $3.71M, indicating a decline of $135.89K (-3.6%) compared to the same period last year.
Gross Profit Percentage (GP%): 39.15%, showing stable profitability despite the slight revenue dip.
This insight highlights a minor decline in sales performance compared to the previous year, suggesting a need to investigate underperforming regions and product categories. Switching the filter to Gross Profit or Quantity would provide further clarity on profitability trends and sales volume dynamics.

Below is the overview page from the PowerBI dashboard and more examples are included throughout the report. The entire dashboard can be viewed [here](https://github.com/PranitHande7/Green-Planet-Co.---Sales-Performance-Analytics/blob/main/PerformReport.pbix).

![Sales Performance Dashboard](https://github.com/PranitHande7/Green-Planet-Co.---Sales-Performance-Analytics/blob/main/PerformReport.png)

## **1. Year to Year Performance** 

### Bottom 10 YTD vs PYTD by Country
- The visualization highlights the 10 worst-performing countries based on Year-to-Date (YTD) sales compared to the Previous Year-to-Date (PYTD).The darker shades represent countries with larger sales declines, while the lighter shades indicate smaller drops.
- Canada (-73.71K) and Colombia (-61.12K) have experienced the highest YTD sales declines, signaling potential market challenges, demand shifts, or competitive pressure in these regions.
- Other significantly impacted markets include Croatia (-48.52K), Germany (-44.04K), and Hungary (-32.07K), suggesting a broader trend of reduced performance in these regions.
- Countries such as Vietnam, South Korea, Czech Republic, Greece, and Kenya also show notable declines between -27.60K and -23.89K.
  
 ![image1](https://github.com/PranitHande7/Green-Planet-Co.-Sales-Performance-Analytics/blob/main/bottom10.png)

## **2. Product & Regional Trends**

### 2.1 Sales YTD vs PYTD by Month - Country - Product
- This visual represents the month-over-month change in Year-to-Date (YTD) vs Previous Year-to-Date (PYTD) sales, showing where sales have increased or decreased.
- February saw a strong increase of +0.34M, making it the best-performing month in YTD vs PYTD comparison.
- January (-0.08M) showed a small dip, possibly due to seasonal demand fluctuations.
- March (-0.15M) and April (-0.24M) had significant drops, with April being the worst-performing month in terms of YTD vs PYTD sales difference.
- Total net change for the period is -0.14M, indicating an overall sales decline compared to the previous year.
  
 ![image5](https://github.com/PranitHande7/Green-Planet-Co.-Sales-Performance-Analytics/blob/main/YTDvsPYTD.png)

### 2.1.1 Drill-Down Insight: March Sales YTD vs PYTD by Country
- **We dive deep into the decline of sales in the month of March by country offering deeper insights into regions which contributed to the overall negative YTD vs PYTD sales.**
- Countries like Colombia, Canada, and Croatia show significant negative contributions, with sales dropping between -0.06M and -0.07M.
- Many other countries, including Greece, Germany, and Japan, also recorded losses, further driving the overall sales decline in March.
- A few regions, such as Poland (+0.05M), Thailand (+0.09M), and the United States (+0.04M), performed well and partially offset the decline.
- Despite pockets of growth in select countries, the majority of regions recorded negative variances, leading to an overall decline in March sales compared to PYTD.
- The cumulative total for March is still negative, emphasizing the need for further analysis into product performance, demand shifts, or operational challenges.
  
 ![image3](https://github.com/PranitHande7/Green-Planet-Co.-Sales-Performance-Analytics/blob/main/March.png)

### 2.1.2 Drill-Down Insight: Canada’s Sales YTD vs PYTD by Product Type
- **Major decline was seen in Canada, Colombia and Croatia. The following chart provides a deeper analysis of Canada’s YTD vs PYTD sales performance, categorized by product type. The breakdown helps pinpoint which product segments contributed most to the overall sales decline in the region.**
- Indoor products saw the largest drop (-145K), indicating a significant loss in sales compared to the previous year.
- Landscape products also declined (-118K), further adding to the overall downward trend.
- Outdoor products showed an increase of +128K, partially offsetting the losses from other categories.
- Overall, despite the gain in outdoor products, the total net change for Canada remains negative (-136K), confirming the need for intervention in the Indoor and Landscape categories.
  
 ![image6](https://github.com/PranitHande7/Green-Planet-Co.-Sales-Performance-Analytics/blob/main/canada.png)

### 2.1.3 Drill-Down Insight: Indoor Product Sales Decline in Canada
- **Indoor products indicated significant loss in canada, the following chart highlights which specific products contributed most to the overall decline in this category.**
- Several indoor plant products such as Acacia dealbata Maiden (-0.02M) and Acalypha hispida (-0.02M)  have shown negative YTD vs PYTD sales differences, with some losing as much as -0.02M to -0.01M in revenue.
- While the category as a whole showed a decline, some indoor plants saw YTD gains, to name a few are Aspidistra elatior (+0.02M), Aloe vera (+0.02M) and Begonia convolvulacea (+0.03M).
  
 ![image2](https://github.com/PranitHande7/Green-Planet-Co.-Sales-Performance-Analytics/blob/main/Indoor.png)

### 2.2 Sales YTD and PYTD by Month
- The chart provides a breakdown of sales performance (YTD) by product type across different months while comparing it to PYTD sales
- Strong Q1 performance can be observed. February had the highest sales ($1.15M), driven by strong Landscape category growth ($0.46M) making it the best-performing month so far whereas March remained stable ($1.19M) but had a slightly higher PYTD ($1.04M), indicating last year’s stronger performance.
- A sharp decline can be seen in April where sales dropped drastically to $0.39M, affecting all product categories. The steep PYTD decline suggests April is historically weak, requiring further analysis.
  
 ![image4](https://github.com/PranitHande7/Green-Planet-Co.-Sales-Performance-Analytics/blob/main/Stackedbar.png)

## **3. Account Profitability**
- The plot analyzes account profitability (GP%) against total sales (YTD value), helping identify high-value and high-margin accounts while identifying areas for improvement.
- Most accounts fall within low-to-moderate sales value (<$20K) but vary significantly in gross profit percentage (GP%).
- Accounts with high GP% (>40%) and high sales (>20K) are key profit drivers and should be prioritized.
- Some accounts generate high sales but have GP% below 40%, indicating potential pricing or cost issues. These accounts may benefit from margin improvement strategies.
  
 ![image7](https://github.com/PranitHande7/Green-Planet-Co.-Sales-Performance-Analytics/blob/main/segmen.png)

# Recommendations

Based on the uncovered insights, the following recommendations have been provided:

- Canada, Colombia, and Croatia experienced the highest YTD vs PYTD sales declines, signaling market-specific challenges.
- In Canada, the decline in indoor product sales suggests a shift in consumer preferences toward low-maintenance plants. Introduce marketing campaigns focused on air-purifying and easy-care indoor plants like Aloe Vera and Aspidistra Elatior.
- Regions such as Colombia & Croatia may be facing economic constraints or increased competition. A pricing analysis should be conducted to identify optimal price points and determine whether localized discounts or flexible payment terms could improve demand.
- Indoor and Landscape categories saw significant sales declines, especially in Canada. Introducing new product bundles that include soil, pots, and care instructions to encourage consumer adoption e.g. Indoor plant starter kits. Indoor plant sales typically slow down in spring and summer when outdoor gardening gains popularity. Offer discounts or promotions on indoor plants during these months to sustain demand.
- April saw a sharp decline in sales across all product types, significantly impacting overall performance. Reviewing supply chain and stock levels to ensure availability in Q2. Stock shortages could have disrupted sales in April, leading to missed revenue opportunities. If April historically experiences a drop in demand due to seasonal shifts, develop a pre-season marketing campaign to encourage early planting purchases.
- Several accounts generate high sales but operate at low GP% (<40%), impacting overall profitability. Conducting a cost-plus pricing review to ensure the company isn’t underpricing high-sales products. Small price adjustments on best-selling SKUs can significantly improve margins.
- If logistics costs are high for specific low-margin accounts, consider optimizing order fulfillment or introducing bulk-order incentives to lower per-unit shipping costs.
- Introduce volume-based discounts meaning transition from flat discounts to tiered pricing models where larger purchases receive better discounts, encouraging bulk buying while maintaining profit margins.
- Expand Sales from High-GP%, Low-Sales Accounts by leveraging these accounts for additional upselling opportunities, such as offering plant care kits, fertilizers, or decorative pots as add-ons. Likewise, offer incentives for repeat purchases or encourage wholesale buyers to expand their orders through personalized sales consultations.
- Sales performance varies significantly across regions, products, and customer segments, requiring real-time monitoring and adaptable strategies. Using historical data to forecast seasonal demand and optimize inventory purchases ahead of peak seasons and running location-based digital ads focusing on underperforming regions (e.g., targeted Facebook & Google Ads for Canada and Colombia).

---

# Glossary

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


