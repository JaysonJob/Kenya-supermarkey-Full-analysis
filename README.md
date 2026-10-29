# Kenya-supermarkey-Full-analysis
## Dataset Overview
This project uses a realistic retail dataset generated to simulate a supermarket's daily transactions.The raw data is publicly available on Kaggle: [Supermarket Dataset](https://www.kaggle.com/datasets/datascikhan/supermarket). 

The original dataset contains over **120,000 rows** and **250+ columns**,including customer IDs,transaction dates,product details,store information,payment methods and promotions.For this analysis,I filtered the data down to the 12 most important columns to make the queries and models faster and easier to understand.

## Tech Stack
- Python (Pandas,Scikit-learn) for data cleaning and machine learning.
- PostgreSQL for storing data and running queries.
- Power BI for making the dashboard.
- Jupyter Notebook for running the code.

## Setup / Installation

### 1. What you need
- PostgreSQL installed on your computer.
- Power BI Desktop (offline).
- Jupyter Notebook or Google Colab.
- Python 3 with pandas and scikit-learn installed.

### 2. Steps to run this project
1. **Database:** Open pgAdmin and create a new database called `capstone_project`.
2. **Import Data:** Run the `data collection.sql` file to create the tables.Then import the `kenya_retail.csv` file into the database.
3. **Clean Data:** Run the `data cleaning.sql` file to fix the data types and missing values.
4. **Run Queries:** Run the `analysis and answering busines questions.sql` file to get the business answers.
5. **Power BI:** Double-click the `Power bi.pbix` file to open the dashboard offline.I aswell have the power BI pdf

## Workflow & Analysis

### 1. Data Collection (Python)
*File: `importing the data and modifying.ipynb`*
**Goal:** Load the huge raw dataset and keep only the 12 columns we actually need out of 250+.This makes the data smaller and faster to work with.

### 2. Data Cleaning (SQL)
*File: `data cleaning.sql`*
**Goal:** Fix the data so it is ready for analysis.
**What it does:**It fixes negative numbers,makes sure the total amount is calculated correctly and changes "Mobile Wallet" to "M-Pesa" and standardising texts.

### 3. SQL Business Analytics and views
*File: `analysis and answering busines questions.sql`*

**Query 1: Which payment method brings in the most money?**
* **Question:** Should the manager focus on M-Pesa or cards?
* **Answer:** The query groups by payment method.The answer is that Credit and Debit cards actually bring in more money (over 55%) than M-Pesa (15%).

**Query 2: What are the top product categories?**
* **Question:** What should the store always keep in stock?
* **Answer:** The query sums revenue by category.Groceries,Meat and Fruits are the top sellers.

**Query 3: Did promotions work?**
* **Question:** Do discounts make people spend more?
* **Answer:** The query compares average spending with and without promotions.It shows that promotions slightly increase the average basket size.

**Query 4: Do people spend more on holidays?**
* **Question:** Should we hire more staff on public holidays?
* **Answer:** The query groups by `is_holiday`.It shows that while fewer people shop,the average spend per person is higher on holidays.

**Query 5: Which store is the best?**
* **Question:** Which store is our top performer in terms of revenue generated?
* **Answer:** Using a ranking window function,the query lists the top 10 stores by revenue.

**Query 6: Who are our best customers?**
* **Question:** Who should we give VIP treatment to?
* **Answer:** The query calculates Recency,Frequency and Monetary value (RFM) to find the top 10 customers who spend the most money.

**Query 7: Which customers are leaving?**
* **Question:** Who needs a win-back discount?
* **Answer:** The query finds how many days since a customer last bought something.Customers with the highest days are at risk of leaving.

**Query 8: What do customers buy more than once?**
* **Question:** What items have loyal buyers?
* **Answer:** The query joins the table to itself to find customers who bought the exact same product on different days.

### 4. Predictive Modeling (Python)
*File: `predictive model.ipynb`*
**Goal:** Predict which customers will stop buying (churn).
**How it works:** I grouped the data by customer and defined churn as "not buying since Jan 2024".I trained a Random Forest model and compared it to a simple baseline.The model helps us find customers who are about to leave so we can send them discounts.

### 5. Executive Dashboard (Power BI)
*File: `Power bi.pbix` / `Power bi.pdf`*
**Goal:** Give the manager a quick summary of the whole business in plain text.
**What it says:** The report explains that the store made 11.27M from 120,000 sales with an average basket of 93.88.It highlights that Credit and Debit cards actually bring in more money than M-Pesa.It also mentions that Groceries and Meat are the top sellers and sales started dropping towards the end of the year.Finally,it warns that new customers are most likely to stop buying.

### 7. Insights & Strategic Recommendations (Power BI Text Page)
**Goal:** Turn the data into real actions the business can take to make more money.

**Insights found from the data:**
- **Payments:** While M-Pesa is popular but Credit and Debit Cards make up over 55% of the revenue.
- **Products:** Grocery,Meat and Fruits are the biggest money makers.
- **Trends:** Sales drop heavily towards October and November.
- **Churn:** Customers who only buy once are the most likely to leave.

**Recommendations for the Manager:**
1. **Card-First Marketing:** Since cards bring in the most money,the store should offer cashback or loyalty points for card users.
2. **Stock Up on Winners:** Always keep Groceries and Meat fully stocked to prevent customers from going to competitors.
3. **Fix the End-of-Year Drop:** Launch a special holiday campaign in October and November to boost sales and clear out old stock (like Laundry items).
4. **Increase Basket Size:** An average spend of 93.88 is low.Put snacks and bakery items near the checkout so people buy more.
5. **Stop Customer Churn:** Use the churn model to find new customers who haven't returned in 30 days and send them a 10% discount SMS to their M-Pesa.


## Connect With Me
If you have any questions or feedback about this project feel free to reach out

- **Email:** [jaysonjobkibet@gmail.com](mailto:jaysonjobkibet@gmail.com)
- **LinkedIn:** [Jayson Kibet](https://www.linkedin.com/in/jayson-kibet-/)
