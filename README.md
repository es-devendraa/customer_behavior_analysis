# customer_behavior_analysis
Data analysis on customer shopping pattern using python, sql, powerbi.


# Customer Shopping Behavior Analysis

An end-to-end data analytics project exploring customer purchasing
patterns, product preferences, discounts, shipping choices, and
subscription behavior. The project uses **Python for data preparation,
PostgreSQL for SQL analysis, and Power BI for interactive
visualization** to turn transaction-level data into business
recommendations.

## Table of Contents

-   [Project Overview](#project-overview)
-   [Business Problem](#business-problem)
-   [Objectives](#objectives)
-   [Dataset](#dataset)
-   [Tools and Technologies](#tools-and-technologies)
-   [Project Workflow](#project-workflow)
-   [Business Questions Explored](#business-questions-explored)
-   [Key Business Recommendations](#key-business-recommendations)
-   [Dashboard](#dashboard)
-   [Repository Structure](#repository-structure)
-   [How to Run the Project](#how-to-run-the-project)
-   [Skills Demonstrated](#skills-demonstrated)
-   [Future Improvements](#future-improvements)

## Project Overview

Retail businesses need to understand what influences customers'
purchasing decisions and what encourages repeat purchases. This project
examines customer shopping data to identify patterns across customer
segments, product categories, discounts, reviews, seasons, shipping
types, and subscription status.

The analysis follows a practical analytics workflow: clean and prepare
the data in Python, load it into PostgreSQL for business-focused SQL
queries, and present the analysis in a Power BI dashboard.

## Business Problem

The business wants to better understand its customers to improve sales,
customer satisfaction, and long-term loyalty. Management is interested
in how purchasing behavior differs across demographics, products, and
shopping preferences---and how factors such as discounts, reviews,
seasons, and payment preferences relate to customer decisions and repeat
purchases.

**Main business question:**\
How can the company use customer shopping data to identify trends,
improve customer engagement, and optimize marketing and product
strategies?

## Objectives

-   Prepare a reliable dataset for analysis by checking data types,
    missing values, and consistency.
-   Explore customer demographics and purchasing patterns.
-   Use SQL to investigate revenue, spending, discounts, shipping,
    subscriptions, and product performance.
-   Segment customers based on purchase history.
-   Build an interactive Power BI dashboard to communicate patterns and
    trends.
-   Translate analytical questions into practical business
    recommendations.

## Dataset

The project dataset contains **3,900 purchase records and 18 columns**.

  -----------------------------------------------------------------------
  Data area                           Example fields
  ----------------------------------- -----------------------------------
  Customer profile                    Age, gender, location, subscription
                                      status

  Purchase details                    Item purchased, category, purchase
                                      amount, season, size, color

  Shopping behavior                   Discount applied, previous
                                      purchases, purchase frequency

  Customer feedback and fulfillment   Review rating, shipping type
  -----------------------------------------------------------------------

The initial data review identified **37 missing values in the
`review_rating` column**. These were handled by imputing the median
review rating within each product category, as documented in the project
report.

> **Note:** Add the dataset source and license here if you plan to
> redistribute the data. Do not commit private or restricted data to a
> public repository.

## Tools and Technologies

-   **Python** --- data cleaning, exploratory data analysis, feature
    engineering, and database loading
-   **Pandas** --- data manipulation and preparation
-   **PostgreSQL** --- structured storage and SQL-based business
    analysis
-   **SQL** --- aggregations, comparisons, product analysis, and
    customer segmentation
-   **Power BI** --- interactive dashboard and visual reporting
-   **Jupyter Notebook** --- exploratory analysis and documentation (if
    used in your repository)

## Project Workflow

### 1. Data preparation and exploratory analysis --- Python

-   Loaded the dataset with Pandas.
-   Inspected its structure and summary statistics using methods such as
    `info()` and `describe()`.
-   Checked for missing values and imputed missing review ratings using
    the median rating for each product category.
-   Standardized column names to `snake_case`.
-   Created an `age_group` feature by grouping customer ages.
-   Created a `purchase_frequency_days` feature from the purchase data.
-   Checked whether `discount_applied` and `promo_code_used` represented
    redundant information and dropped `promo_code_used` as described in
    the report.
-   Connected Python to PostgreSQL and loaded the cleaned DataFrame for
    SQL analysis.

### 2. Business analysis --- PostgreSQL / SQL

SQL queries were used to investigate business questions, including
revenue comparisons, discount behavior, product ratings, shipping types,
subscription behavior, customer segments, and purchase patterns.

### 3. Dashboard and communication --- Power BI

An interactive Power BI dashboard was created to present the analysis
visually and help stakeholders explore customer shopping behavior.

## Business Questions Explored

The SQL analysis covers the following questions:

1.  **Revenue by gender:** How does total revenue compare between male
    and female customers?
2.  **High-spending discount users:** Which customers used discounts but
    still spent more than the average purchase amount?
3.  **Top-rated products:** Which five products have the highest average
    review ratings?
4.  **Shipping comparison:** How do average purchase amounts compare
    between Standard and Express shipping?
5.  **Subscribers vs. non-subscribers:** How do average spend and total
    revenue differ by subscription status?
6.  **Discount-dependent products:** Which five products have the
    highest percentage of discounted purchases?
7.  **Customer segmentation:** How can customers be classified as New,
    Returning, or Loyal based on purchase history?
8.  **Best-selling products by category:** What are the top three
    most-purchased products in each category?
9.  **Repeat buyers and subscriptions:** Are customers with more than
    five purchases more likely to subscribe?
10. **Revenue by age group:** How much total revenue does each customer
    age group contribute?

These are the questions investigated by the project; consult the SQL
outputs and report for the actual results and values.

## Key Business Recommendations

Based on the project's analysis themes and recommendations:

-   **Encourage subscriptions:** Promote relevant exclusive benefits to
    help increase subscription adoption.
-   **Build customer loyalty:** Consider rewards for repeat buyers and
    campaigns that encourage customers to progress into the Loyal
    segment.
-   **Review discount strategy:** Evaluate whether discounts are
    supporting purchases while keeping profitability and margins in
    view.
-   **Promote strong products:** Use highly rated and frequently
    purchased products in relevant marketing campaigns.
-   **Target marketing thoughtfully:** Use age-group revenue patterns
    and shipping preferences to inform campaign targeting, then validate
    performance with further analysis.

These are strategic recommendations, not claims of proven causal
effects. Validate campaign impact with suitable performance metrics or
controlled tests before making major changes.

## Dashboard

The project includes a Power BI dashboard file:
`customer_behavior_dashboard.pbix`.

**To view it:** Open the `.pbix` file in Microsoft Power BI Desktop.

If you add a dashboard screenshot to the repository, you can display it
here. For example, save an image as `images/dashboard-overview.png` and
uncomment the line below:

```{=html}
<!-- ![Customer Shopping Behavior Dashboard](images/dashboard-overview.png) -->
```
## Repository Structure

A clear repository structure could look like this. Update the names
below to match the files you actually publish.

``` text
customer-shopping-behavior-analysis/
├── data/
│   └── README.md                 # Dataset source and access instructions
├── notebooks/
│   └── customer_behavior_analysis.ipynb
├── python/
│   └── data_cleaning.py
├── sql/
│   └── customer_behavior_analysis.sql
├── powerbi/
│   └── customer_behavior_dashboard.pbix
├── reports/
│   ├── business_problem.pdf
│   └── customer_shopping_behavior_analysis.pdf
├── images/
│   └── dashboard-overview.png    # Optional dashboard screenshot
├── requirements.txt
└── README.md
```

You do not need to use every folder. Keep only the files and folders
that exist in your actual repository, and avoid committing credentials
or restricted data.

## How to Run the Project

The following is a general setup guide. Adjust file names, database
names, and paths to match your implementation.

### Prerequisites

-   Python 3.x
-   PostgreSQL
-   A Python environment such as `venv` or Conda
-   Microsoft Power BI Desktop to open the dashboard

### 1. Clone the repository

``` bash
git clone <your-repository-url>
cd customer-shopping-behavior-analysis
```

Replace `<your-repository-url>` with the URL of your GitHub repository.

### 2. Set up Python

Create and activate a virtual environment if desired:

``` bash
python -m venv .venv
```

On Windows:

``` bash
.venv\Scripts\activate
```

Install the packages required by your scripts. For example, if they are
used in your project:

``` bash
pip install pandas sqlalchemy psycopg2-binary jupyter
```

If you create a `requirements.txt`, install from it instead:

``` bash
pip install -r requirements.txt
```

### 3. Prepare the database

-   Start PostgreSQL and create a database for the project.
-   Configure the database connection using environment variables or a
    local configuration file that is **not committed to GitHub**.
-   Run your Python cleaning/loading script or notebook to prepare the
    data and load it into PostgreSQL.
-   Execute the SQL scripts against the database.

Do not put database passwords, API keys, or other secrets directly in
source code or this README.

### 4. Open the dashboard

Open `powerbi/customer_behavior_dashboard.pbix` in Power BI Desktop. If
the report uses a local database connection, update its data-source
settings to match your own PostgreSQL setup and refresh the data.

## Skills Demonstrated

-   Data cleaning and preprocessing
-   Exploratory data analysis with Python and Pandas
-   Feature engineering
-   Relational database integration
-   SQL aggregations and business analysis
-   Customer segmentation
-   KPI and trend communication through Power BI
-   Translating analytical questions into business recommendations

## Future Improvements

-   Add a documented data dictionary and data-source reference.
-   Include the SQL scripts and Python notebook/script with reproducible
    instructions.
-   Add screenshots of the dashboard and a concise summary of the
    measured findings.
-   Investigate purchase patterns by season, payment preference, and
    other available variables where the dataset supports it.
-   Evaluate recommendations using measurable KPIs, such as subscription
    conversion, repeat-purchase rate, average order value, and
    discount-related profitability.
-   Add validation checks and document assumptions used in feature
    engineering and segmentation.

------------------------------------------------------------------------

## Author

Devendra Patel
- GitHub:
[es-devendraa](https://github.com/es-devendraa)\
- LinkedIn: [your-linkedin-profile](https://www.linkedin.com/in/es-devendra/)


