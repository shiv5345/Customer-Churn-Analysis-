# Customer Churn Analysis
## Comprehensive Summary:
Customer Churn Analysis
This report, authored by Shiv Chetan Kumawat, presents a thorough exploratory data analysis (EDA) of a telecommunications customer dataset. The primary goal is to understand the factors driving customer churn (i.e., customers leaving the service).

### 1. Project Overview & Setup
Objective: To analyze customer data and identify key patterns and characteristics associated with churn.

Tools Used: The analysis is conducted in Python using popular data science libraries:

pandas and numpy for data manipulation.

seaborn and matplotlib.pyplot for data visualization.

Dataset: The dataset (Customer_Churn.csv) contains 7,043 customer records and 21 attributes, including demographic information, service subscriptions, account details, and the target variable Churn (Yes/No).

### 2. Data Cleaning and Preparation
The analyst performed crucial data cleaning steps to ensure data quality:

Initial Inspection: The df.info() function revealed the dataset had no null values but identified an issue with the TotalCharges column, which was incorrectly stored as a string (object) type instead of a numerical type.

Fixing TotalCharges: The analyst found blank spaces (" ") in the TotalCharges column for customers with zero tenure. These blanks were replaced with '0' and the column was successfully converted to a float data type.

Data Integrity: Checks confirmed there are no missing values (df.isnull().sum().sum() = 0) and no duplicate customer IDs (df['customerID'].duplicated().sum() = 0).

Data Transformation: The SeniorCitizen column, which was encoded as integers (0 or 1), was converted to categorical strings ('No' or 'Yes') for easier interpretation and visualization.

### 3. Exploratory Data Analysis (EDA) - Key Findings
The EDA is extensive and uses count plots, pie charts, and histograms to compare the behavior of customers who churned ("Yes") versus those who stayed ("No").

#### A. Overall Churn Rate:

The overall customer churn rate is 26.54%.

5,174 customers did not churn.

1,869 customers did churn.

#### B. Demographic Factors:

Gender: Churn is almost evenly distributed between males and females, indicating that gender is not a significant predictor of churn.

Senior Citizen: While there are far fewer senior citizens, they have a significantly higher churn rate (58.3%) compared to non-seniors (23.6%). This makes SeniorCitizen a very important demographic factor.

#### C. Service Tenure and Contract:

Tenure: The tenure histogram shows a very clear pattern: customers with very low tenure (0-5 months) are highly likely to churn. Conversely, customers who have stayed with the company for a longer period are far less likely to leave.

Contract Type: This is one of the strongest indicators of churn.

Month-to-Month: Customers with monthly contracts have a very high churn rate.

One-Year & Two-Year Contracts: Customers with longer-term contracts have dramatically lower churn rates. This suggests that commitment is a powerful retention tool.

#### D. Service Subscriptions:
The analysis includes count plots for all service offerings (Phone, Internet, Security, Backup, etc.). Key takeaways include:

Internet Service Type: Customers with Fiber optic service have a much higher churn count than those with DSL, potentially due to pricing, competition, or service issues.

Additional Services: Customers without additional services like Online Security, Tech Support, Online Backup, and Device Protection (shown as "No" in the plots) are more likely to churn than those who have them. This suggests that these value-added services help in customer retention.

Multiple Lines: The presence or absence of multiple lines does not show a dramatic difference in churn behavior.

#### E. Payment Method:

The Electronic check payment method is associated with a significantly higher rate of churn compared to automatic payment methods (Credit card, Bank transfer). This could be due to the manual effort required or a reminder of the bill, making customers more likely to cancel.

### 4. Conclusion and Inferred Business Insights
The analysis successfully identifies several high-impact factors that contribute to customer churn:

High-Risk Customers: New customers (low tenure) and those on month-to-month contracts are the most vulnerable to churning.

Key Demographic: Senior citizens are a high-risk demographic that may require targeted retention strategies.

Value of Bundled Services: Offering and promoting add-on services like Online Security and Tech Support can significantly improve customer retention.

Payment Method: Encouraging customers to adopt automatic payment methods could reduce churn.

Internet Service: The high churn among Fiber optic users warrants investigation into service quality, pricing, and competitive positioning.

### Recommendation:
        The company should focus its retention efforts on new customers and those without long-term contracts. Strategies could include targeted offers to convert month-to-month users to annual contracts, creating engagement campaigns for the first 6 months, promoting the value of add-on services, and making automatic payments more attractive.

