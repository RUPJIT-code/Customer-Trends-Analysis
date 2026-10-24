# Customer Shopping Behavior Analysis

An end-to-end data analytics project that studies the shopping behavior of 3,900 retail customers using **Python, PostgreSQL (SQL) and Power BI**, and turns the results into simple business recommendations.

## Project Goal

Understand who the customers are, what they buy and what drives their spending, then suggest clear actions to grow the business.

## Tools Used

| Stage | Tool |
|---|---|
| Data cleaning and feature engineering | Python (pandas), Jupyter Notebook |
| Data storage | PostgreSQL (SQLAlchemy, psycopg2) |
| Analysis | SQL |
| Visualization | Power BI Desktop |

## Dataset

- File: `data/customer_shopping_behavior.csv`
- 3,900 rows (one per customer) and 18 columns
- Includes age, gender, location, item, category, purchase amount, season, review rating, subscription status, shipping type, discount, previous purchases, payment method and purchase frequency

## Project Workflow

1. **Clean and prepare data (Python):** checked data quality, filled 37 missing review ratings with the category median, renamed columns to snake_case, created `age_group` and `purchase_frequency_days`, and dropped `promo_code_used` because it was identical to `discount_applied`.
2. **Store data (PostgreSQL):** loaded the cleaned data into a `customer` table.
3. **Analyze (SQL):** answered 10 business questions.
4. **Visualize (Power BI):** built an interactive dashboard with filters and KPI cards.
5. **Report:** summarized findings and recommendations in a report and presentation.

## Business Questions Answered (SQL)

1. Revenue from male vs. female customers
2. Discount users who still spent above the average
3. Top 5 products by review rating
4. Average purchase for Standard vs. Express shipping
5. Do subscribers spend more than non-subscribers?
6. Top 5 products with the highest discount rate
7. New, Returning and Loyal customer segments
8. Top 3 most purchased products in each category
9. Are repeat buyers more likely to subscribe?
10. Revenue by age group

## Key Findings

- Total revenue is **$233,081**, average purchase **$59.76**, average rating **3.75 / 5**.
- **Clothing and Accessories** bring about 76% of revenue. Outerwear is the smallest category (8%).
- Men bring 68% of revenue only because there are more male customers. Average spend is almost the same for men ($59.54) and women ($60.25).
- **Subscribers do not spend more** ($59.49 vs. $59.87), and only 27% of customers subscribe.
- **43% of purchases use a discount**, but discounted purchases are not bigger ($59.28 vs. $60.13).
- **80% of customers are Loyal** and only 2% are New.

## Business Recommendations

1. Improve the subscription program with real benefits and free trials for repeat buyers.
2. Reduce unnecessary discounts, starting with Hats, Sneakers and Coats.
3. Bring in more new customers with first-purchase offers.
4. Attract more women customers, who spend as much as men but are only 32% of customers.
5. Boost Outerwear sales by bundling it with Clothing.
6. Promote top-rated products (Gloves, Sandals, Boots) and check the quality of Shirts, Jeans and Blouses.
7. Focus marketing on young adults (18-31) and top states (Montana, Illinois, California).

## Limitations

- The data has no dates, so trends over time cannot be measured.
- There is no cost or margin data, so recommendations are based on revenue, not profit.
- Many differences between groups are small (1-3%) and should be tested for statistical significance.

## Repository Structure

```
customer-shopping-behavior-analysis/
├── data/
│   └── customer_shopping_behavior.csv
├── notebooks/
│   └── Customer_Shopping_Behavior_Analysis.ipynb
├── sql/
│   └── customer_behavior_sql_queries.sql
├── dashboard/
│   ├── customer_behavior_dashboard.pbix
│   ├── customer_behavior_dashboard_powerbi.pdf
│   └── dashboard_preview.png
├── reports/
│   ├── Customer_Shopping_Behavior_Report.pdf
│   └── Customer_Shopping_Behavior_Presentation.pptx
├── README.md
└── .gitignore
```

## How to Run

1. Install the libraries: `pip install pandas sqlalchemy psycopg2-binary jupyter`
2. Create a PostgreSQL database named `customer_behavior`.
3. Set your database password as an environment variable named `PG_PASSWORD`.
4. Open the notebook in `notebooks/` and run all cells to clean the data and load it into PostgreSQL.
5. Run the queries in `sql/customer_behavior_sql_queries.sql` in pgAdmin or any SQL client.
6. Open `dashboard/customer_behavior_dashboard.pbix` in Power BI Desktop.

## Author

**Rupjit Das** | [LinkedIn](https://www.linkedin.com/in/rupjit) | [GitHub](https://github.com/RUPJIT-code)
