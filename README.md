# Superstore Sales Trend Analysis

## Table of Contents

- [Project Overview](#project-overview)
- [Business Objectives](business-objectives)
- [Data Source](data-source)
- [Tools](tools)

### Project Overview

This project aims to analyze sales data to uncover key business insights. The focus will be on identifying trends, seasonal patterns, and anomalies within the dataset. By evaluating performance across products, regions, subcategories, and customer segments, the analysis will inform strategic decision-making. It will highlight which areas to target for growth and which to deprioritize due to underperformance. Ultimately, the outcome will support data-driven decision-making and resource allocation.

### Business Objectives
1.	Which product subcategory recorded the highest profit, and which incurred the greatest loss?
2.	Which customer segment contributes the most to overall profit?
3.	Which month consistently records the highest sales volume?
4.	Which product category contributes the most to overall profit?
5.	Which product subcategory generates the highest and lowest revenue?
6.	Which product subcategory has the highest and lowest profit margin?
7.	What is the relationship between discount rates and quantity sold?
8.	How do discounts affect overall revenue generation?
9.	How do discounts influence profit generation across products?
10.	Which state records the highest sales and profit figures?
11.	Which city generates the most sales and profit?
12.	Which geographical region is the most profitable overall?


### Data Source

The dataset used for this project is the "Superstore Sales Analysis Dataset.xlsx" obtained from [kaggle](www.kaggle.com/datasets/vivek468/superstore-dataset-final)

### Tools
- Excel 
- Power Bi

### Data cleaning/preparation
1.	The column “Row ID” was removed
2.	The “Order Date” and “Ship Date” date format was changed from “MM–DD–YY” to “DD–MM–YY”, and the data type was set as date.
3.	Four (4) dimension tables were created
   - DimOrder
   - DimCustomer
   - DimLocation
   - DimProduct
4.	The cleaned dataset was imported into Power Bi, and a relationship was created between the dimension tables and the fact table
5.	A calendar date table was created and added to the star schema.

### Data Analysis

Seven (7) DAX measures were created to enhance analysis
- ```Average Sales = AVERAGE(FactTable[Sales])```
- ```Total Sales = SUM(FactTable[Sales])```
- ```Total Quantity = SUM(FactTable[Quantity])```
- ```Total Profit = SUM(FactTable[Profit])```
- ```Total Discount = SUM(FactTable[Discount])```
- ```Profit/Loss Flag = IF([Total Profit] < 0, "Loss", "Profit")```
- ```Profit Margin = DIVIDE([Total Profit], [Total Sales])```

### Visualization

#### Page 1: Sales trend analysis overview

#### Purpose:
To give stakeholders a quick overview of business performance at a glance.

#### Visuals:
1. KPI Cards:
- Total customers
- Total product
- Total orders
- Total revenue
- Total profit
2. Area chart:
- Profit trend over time
3. Donut cart:
- Total profit by segment
4. Clustered bar chart:
- Total profit per subcategory
5. Table:
- Year, month, total quantity, total sales, total profit, profit margin, profit/loss flag, total profit by day
6. Slicer:
- Category
- State
- Region

#### Page 2: Sales performance analysis
#### Purpose:
To evaluate how product category and subcategory contribute to profit and revenue

#### Visuals:
1. Ribbon chart:
- Sales seasonal pattern
2. Donut chart:
- Total quantity sold by category
3. Pie chart:
- Total profit by category
4. Funnel:
- Total quantity sold by subcategory
- Total revenue by subcategory
5. Clustered bar chart:
- Total profit by subcategory
- Profit margin by subcategory

#### Page 3: Discount impact analysis
#### Purpose:
To evaluate how discounts influence sales, revenue, and profit.
#### Visuals:
1. Line chart:
- Discount and sale activity timeline
2. Scatter chart:
- Average quantity by discount
- Average revenue by discount
- Average of profit by discount
3. Funnel:
- Average discount by subcategory

#### Page 4: Geospatial analysis
#### Purpose:
To show performance across states, cities, and regions.
#### Visuals:
1. Map visualization:
- Total revenue by state
- Total profit by state
2. Funnel:
- Top 10 cities by total revenue
- Top 10 cities by total profit
3. Donut chart:
- Total profit by region
4. Table:
- Region, state, city, total sales, total profit, profit margin, profit/loss flag

### Key Insights
#### 1.	Dataset Summary:
    
Between January 2014 and December 2017, the dataset recorded:

- 793 unique customers

- 1,818 products sold

- 5,009 total orders

- $2.3 million in total revenue

- $286,397 in total profit

#### 2.	Top and Bottom Performing Subcategories (Profit):

- Copiers were the most profitable subcategory, generating $55,617.82.

- Tables were the least profitable, incurring a loss of -$17,725.48.

#### 3.	Customer Segments Performance:

- The Consumer segment was the most profitable, contributing 47% of total profit.

- This outperformed the Corporate (32%) and Home Office (21%) segments.

#### 4.	Seasonality of Sales:

- November was the peak month for sales, with a total of $352,461.07 in revenue.

#### 5.	Top Product Category (Profit):

- The Technology category contributed the most to profit, generating $145,434.95, which is 50.79% of total profit.

- Copiers, Phones, and Accessories were the key contributors.

#### 6.	Top and Bottom Subcategories (Revenue):

- Phones generated the highest revenue at $330,007.05.

- Fasteners recorded the least revenue with $3,024.29.

#### 7.	Profit Margins by Subcategory:

- Labels had the highest profit margin at 44.42%.

- Tables had the lowest, with a negative margin of -8.56%, indicating a loss.

#### 8.	Discount vs Quantity Sold:

- A weak to moderate positive correlation exists between discount and quantity sold.  Higher discounts slightly increase sales volume.

#### 9.	Discount vs Revenue:

- There is a weak to moderate negative correlation between discount and revenue, indicating that increasing discounts tends to reduce total revenue.

#### 10.	Discount vs Profit:

- A strong negative relationship was observed between discount and profit. Higher discounts significantly reduce profit.

#### 11.	Top Performing States (Revenue):

- California generated the highest revenue, amounting to $472,903.64, followed by New York with a revenue of $302,004.92.92.

#### 12.	Top Performing States (Profit):

- New York recorded the highest profit at $71,022.39, closely followed by California with a profit of $70,105.49.49.

#### 13.	Top Performing City:

- New York City achieved the highest revenue at $256,368.16 and also recorded the largest profit of $62,035.98.8).

#### 14.	Top Performing Region:

- The Western region of the U.S. was the most profitable, generating $103,613.63 in revenue, which is 36.18% of the total.

### Recommendations

1.	The Technology category, while having the lowest number of products sold, accounts for over 50% of total profit (50.79%). This suggests a strong revenue potential for each unit sold. Therefore, investing resources to boost sales volume in this category through marketing efforts, improved availability, or promotional campaigns could lead to significant growth in overall revenue.

2.	Copiers, phones, and accessories should be prioritized for investment, with a particular emphasis on Copiers as the most promising subcategory. Although Copiers have the lowest sales volume, they generate the highest profit among all subcategories. Additionally, Copiers hold the highest profit margin within the Technology category, ranking fourth overall across all product categories with a profit margin of 37.20%. Expanding marketing efforts and optimizing distribution for Copiers can significantly enhance both revenue and profit performance.

3.	Review the pricing, discounting, sourcing, and marketing of tables, bookcases, and supplies, as they are underperforming and are the leading cause of losses. Consider phasing them out or improving their profitability.

4.	Promote cross-selling strategies that pair low-margin products with high-margin ones, such as bundling tables with profitable accessories or copiers.

5.	Avoid blanket discounting across all products:
- Limit discounts on high-margin products (such as labels and Technology items) to preserve profit.
- Target discounts should be applied only to high-volume, low-margin items where they encourage increased sales without excessively eroding profit.

6.	Allocate a larger share of the marketing budget to the Consumer customer segment, which is the most profitable. Implement tailored campaigns, including loyalty programs and exclusive offers, to retain existing customers and drive further growth within this segment.

7.	Increase inventory levels and enhance marketing efforts in October and early November, as November is the peak sales season. To fully capitalize on this period, consider launching exclusive promotional campaigns in the fourth quarter to take advantage of the natural surge in customer demand.

8.	Boost market presence in top states like California and New York by analyzing success factors in New York City, such as distribution, customer engagement, and localized marketing. Replicate these strategies in other promising urban markets to maximize growth.

