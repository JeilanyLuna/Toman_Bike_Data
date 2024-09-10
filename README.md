# Toman Bike Data Analysis
## Table of Contents

- [Project Overview](#Project-overview)
- [Data Sources](#Data-Sources)
- [Tools](#Tools)
- [Data Cleaning and Preperation](#Data-Cleaning-and-Preperation)
- [Exploratory Data Analysis](#Exploratory-Data-Analysis)
- [Data Analysis](#Data-Analysis)
- [Results and Recommendation](#Results-and-Recommendation)


### Project Overview

In this project, I cleaned and analyzed data as well as vizualized my findings with PowerBI, to display key preformane metrics for Toman Bike sore such as hourly revenue analysis, profit and revenue trends, seasonal revenue, and rider demographics.

### Data Sources

The data sources are the following files. "bike_share_yr_0", "bike_share_yr_1", and "cost_table".

### Tools

- Excel
- SQL Server
- PowerBI

### Data Cleaning and Preperation
In prepping the data for analysis first I preformed:
1. Data loading and inspection.
2. Handling missinf and duplicated values.
3. Data cleaning and formatting

### Exploratory Data Aalysis
- Hourly Revenue Analysis
- Profit and Revenue Trends
- Seasonal Revenue
- Rider Demographics

### Data Analysis

```SQL
with cte as (
select * from bike_share_yr_0
union all
select * from bike_share_yr_1)


select 
dteday,
season,
a.yr,
weekday,
hr,
rider_type,
riders,
price,
COGS,
riders*price as revenue,
riders*price -COGS as profit
from cte a 
left join  cost_table b
on a.yr = b.yr
```

### Results and Recommendation

Conservative Increase: Considering the substantial increase last year, a more conservative increase might be prudent to avoid hitting a price cieling where demand starts to drop. An increase in the range of 10-15% could test the market’s response without risking a significant loss of customers. 
If the price in 2022 was $4.99, a 10% increase would make the new price about $5.49.
A 15% increase would set the price at approximately $5.74.
Recommended Stragety:
Market Analysis: Conduct further market research to understand customer satisfaction, potential competative changes, and the overall economic environment. This can guide whether leaning towards the lower or higher end of the suggested increase.
Segmented Pricing Strategy: Consider different pricing for casual versus registered users, as they may have different price sensetivities.
Monitor and Adjust: Implement the new prices, but be ready to adjust based on immediate customer feedback and sales data. Monitoring closely will allow you to fine-tune your pricing strategy without committing fully to a price that might turn out to be too high.


