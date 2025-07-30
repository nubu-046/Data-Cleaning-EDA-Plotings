# Sales Transaction Data Analysis

This project involves exploratory data analysis (EDA) of a retail sales transaction dataset. It covers the process of data cleaning, preprocessing, and uncovering patterns using visualizations.

## Dataset Overview

- The dataset contains retail transaction records.
- Key columns include Transaction ID, Customer ID, Category, Item, Price Per Unit, Quantity, Total Spent, Payment Method, Location, Transaction Date, and Discount Applied.

## Data Cleaning

- Identified missing values in several numeric and categorical columns.
- Missing values in price, quantity, and total spent were filled or dropped as needed to maintain consistency.
- Discount Applied column was filled with default 'False' where missing.
- Transaction Date was converted to a consistent datetime format using day-month-year pattern.

## Exploratory Data Analysis

### Monthly Revenue Trend

- Grouped the transactions by month and visualized total revenue over time.
- Identified monthly fluctuations and seasonality in sales.

### Revenue Distribution by Category

- Compared how much revenue each product category generated.
- Displayed as a pie chart to show relative contribution of each category.

### Top Items by Revenue

- Identified top 10 items generating the most revenue.
- Visualized using a horizontal bar plot.

### Payment Method Distribution

- Analyzed which payment methods were used most frequently.
- Useful for understanding customer preferences.

### Impact of Discount on Spending

- Compared total amount spent between transactions with and without discounts.
- Helped evaluate effectiveness of discount strategies.

### Revenue by Location

- Compared total revenue generated from different locations.
- Highlighted best-performing and underperforming regions.

### Quantity Sold per Category

- Summarized the total quantity sold for each product category.
- Gave insights into product demand.

## Tools Used

- Python for data analysis
- Pandas for data manipulation
- Matplotlib and Seaborn for visualization

## Key Findings

- Some product categories and items generate significantly more revenue than others.
- Discounts have a limited but noticeable impact on customer spending.
- Certain locations contribute heavily to overall sales.
- Monthly sales trends reveal periodic patterns that can inform business strategy.

## Future Improvements

- Build interactive dashboards for live insights.
- Use machine learning to predict future sales.
- Segment customers based on purchasing behavior for targeted marketing.
