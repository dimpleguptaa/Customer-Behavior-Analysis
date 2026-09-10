# Customer Behavior Analysis

An end-to-end data analytics project analyzing the shopping behavior of 3,900 customers using Python, PostgreSQL, and Power BI.

## Project Overview

This project explores customer transactional data to uncover patterns in spending behavior, product preferences, discount usage, and subscription trends, translating raw data into actionable business insights through structured analysis and interactive visualization.

## Project Structure

```
Customer-Behavior-Analysis/
├── Python_customerbehavior_code.ipynb          # Data cleaning & preparation
├── customerbehavior_sql.sql                    # SQL business queries (PostgreSQL)
├── PowerBI_Dashboard_Customerbehavior.pbix      # Interactive Power BI dashboard
├── Customer_Behavior_Analysis_Report.docx       # Full project report
├── Customer-Shopping-Behaviour-Analysis.pptx    # Presentation deck
└── README.md
```

> Note: rename the actual files in the repo to match these names exactly (currently the notebook has a space instead of an underscore, and the .pbix is missing the "r" in "Power") so the structure above and the commands below actually work if someone clones the repo.

## Tools & Technologies

| Tool | Purpose |
|---|---|
| Python (Pandas) | Data cleaning, feature engineering |
| SQLAlchemy + psycopg2 | Python → PostgreSQL connection |
| PostgreSQL / pgAdmin 4 | Database storage & SQL analysis |
| Power BI Desktop | Interactive dashboard & visualization |

## Dataset

- Source: **[add the dataset link here — e.g. the Kaggle page]**
- Rows: 3,900 | Columns: 18
- Key fields: Age, Gender, Item Purchased, Category, Purchase Amount (USD), Shipping Type, Discount Applied, Subscription Status, Review Rating, Previous Purchases

## Dashboard Preview

**[Add 1–2 screenshots of the Power BI dashboard here]** — most people reviewing this repo won't open a .pbix file, so this is the single highest-impact addition you can make.

```
![Dashboard overview](images/dashboard_overview.png)
```

## Workflow

### 1. Data Cleaning & Preparation (Python)

- Loaded CSV using pandas
- Identified and imputed 37 missing values in `review_rating` using category-level median
- Standardized all column names to snake_case for PostgreSQL compatibility
- Feature engineering:
  - `age_group` — bucketed customer ages into cohorts (Young Adult, Adult, Middle-aged, Senior)
  - `purchase_frequency_days` — converted text frequency to numeric days
- Dropped redundant column `promo_code_used` (100% identical to `discount_applied`)
- Loaded cleaned DataFrame into PostgreSQL using SQLAlchemy

### 2. SQL Analysis (PostgreSQL)

Ten business queries were written to answer key questions:

| # | Question |
|---|---|
| Q1 | Total revenue by gender |
| Q2 | Discount users who still spent above average |
| Q3 | Top 5 products by average review rating |
| Q4 | Average spend — Standard vs. Express shipping |
| Q5 | Subscriber vs. non-subscriber spend comparison |
| Q6 | Top 5 products by discount usage rate |
| Q7 | Customer segmentation — New, Returning, Loyal, based on number of previous purchases |
| Q8 | Top 3 products per category (window function) |
| Q9 | Repeat buyers and subscription likelihood |
| Q10 | Revenue contribution by age group |

### 3. Power BI Dashboard

An interactive dashboard built on top of the PostgreSQL database with:

- KPI cards — total customers (3.9K), avg. purchase ($59.76), avg. rating (3.75)
- Revenue and sales by product category
- Revenue and sales by age group
- Subscription status breakdown (Yes 27% / No 73%)
- Slicers for gender, category, shipping type, and subscription status

## Key Findings

- Male customers account for significantly higher total revenue (~$157K vs ~$75K for female)
- 839 customers used discounts but still spent above the average purchase amount
- Gloves, Sandals, and Boots are the top-rated products
- Express shipping customers spend slightly more on average ($60.48 vs $58.46 Standard)
- Non-subscribers outnumber subscribers 3:1, presenting a clear growth opportunity
- 80% of customers fall into the Loyal segment (>10 previous purchases)
- Young Adults generate the highest total revenue ($62,143)

## How to Run

1. Clone the repository
2. Download the dataset from the source above and place it in the project folder
3. Open `Python_customerbehavior_code.ipynb` in Jupyter and run all cells
4. Ensure PostgreSQL is running locally with a database named `customer_behavior`
5. Update database credentials in the notebook if needed (use environment variables rather than hardcoding them, if you haven't already)
6. Open `customerbehavior_sql.sql` in pgAdmin 4 and run queries
7. Open `PowerBI_Dashboard_Customerbehavior.pbix` in Power BI Desktop

## Author

Dimple
Data Analytics Project | Python · SQL · Power BI

