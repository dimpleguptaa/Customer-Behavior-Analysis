# Customer-Behavior-Analysis
An end-to-end data analytics project analyzing the shopping behaviour of 3,900 customers using Python, PostgreSQL, and Power BI.

📌 Project Overview
This project explores customer transactional data to uncover patterns in spending behaviour, product preferences, discount usage, and subscription trends. The goal is to translate raw data into actionable business insights through structured analysis and interactive visualisation.

🗂️ Project Structure
customer-shopping-behaviour/
│
├── Python_customerbehavior_code.ipynb   # Data cleaning & preparation
├── customerbehavior_sql.sql             # SQL business queries (PostgreSQL)
├── PowerBI_Dashboard_Customerbehavior.pbix  # Interactive Power BI dashboard
├── Customer_Behavior_Analysis_Report.docx   # Full project report
└── README.md

🛠️ Tools & Technologies
ToolPurposePython (Pandas)Data cleaning, feature engineeringSQLAlchemy + psycopg2Python → PostgreSQL connectionPostgreSQL / pgAdmin 4Database storage & SQL analysisPower BI DesktopInteractive dashboard & visualisation

📊 Dataset

Source: Customer Shopping Behaviour dataset (CSV)
Rows: 3,900  |  Columns: 18
Key fields: Age, Gender, Item Purchased, Category, Purchase Amount (USD),
Shipping Type, Discount Applied, Subscription Status, Review Rating, Previous Purchases


⚙️ Workflow
1. Data Cleaning & Preparation (Python)

Loaded CSV using pandas
Identified and imputed 37 missing values in Review Rating using category-level median
Standardised all column names to snake_case for PostgreSQL compatibility
Feature Engineering:

age_group — bucketed customer ages into cohorts (Young Adult, Adult, Middle-aged, Senior)

purchase_frequency_days — converted text frequency to numeric days

Dropped redundant column promo_code_used (100% identical to discount_applied)

Loaded cleaned DataFrame into PostgreSQL using SQLAlchemy

2. SQL Analysis (PostgreSQL)
Ten business queries were written to answer key questions:
#QuestionQ1Total revenue by gender
Q2Discount users who still spent above average
Q3Top 5 products by average review rating
Q4Average spend — Standard vs. Express shipping
Q5Subscriber vs. non-subscriber spend comparison
Q6Top 5 products by discount usage rate
Q7Customer segmentation — New, Returning, Loyal
Q8Top 3 products per category (window function)
Q9Repeat buyers and subscription likelihood
Q10Revenue contribution by age group

3. Power BI Dashboard
An interactive dashboard built on top of the PostgreSQL database with:

KPI cards — total customers (3.9K), avg. purchase ($59.76), avg. rating (3.75)
Revenue and sales by product category
Revenue and sales by age group
Subscription status breakdown (Yes 27% / No 73%)
Slicers for gender, category, shipping type, and subscription status


💡 Key Findings

Male customers account for significantly higher total revenue (~$157K vs ~$75K for female)
839 customers used discounts but still spent above the average purchase amount
Gloves, Sandals, and Boots are the top-rated products
Express shipping customers spend slightly more on average ($60.48 vs $58.46 Standard)
Non-subscribers outnumber subscribers 3:1, presenting a clear growth opportunity
80% of customers fall into the Loyal segment (>10 previous purchases)
Young Adults generate the highest total revenue ($62,143)


📁 How to Run

Clone the repository
Open Python_customerbehavior_code.ipynb in Jupyter and run all cells
Ensure PostgreSQL is running locally with a database named customer_behavior
Update credentials in the notebook if needed
Open customerbehavior_sql.sql in pgAdmin 4 and run queries
Open PowerBI_Dashboard_Customerbehavior.pbix in Power BI Desktop


👩‍💻 Author
Dimple
Data Analytics Project | Python · SQL · Power BI
