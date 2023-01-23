# Fraud_Detection
Fraud Detection Case Study

**Brief instructions about navigation**
Online Banking Fraud/Counterfeit Detection
Goal:
Predict fraudulent/counterfeit cases in credit card transactions.


Approach:
Search and retrieve relevant data from Kaggle.
Select relevant techniques to clean the data (missing values, outliers, wrong data types etc.)
Choose the correct feature selection technique for a classification problem.
Perform feature normalization on the data set.
Use credit card transactions and the information on its account-holder as attributes (i.e., When does a customer buy, what does he buy, how often he pays on time, etc.)
Label past transactions as fraud or fair transactions. This forms the class attribute.
Build a model for the class of the transactions.
Use this model to detect fraud by observing credit card transactions on an account.
Solution
Data Description
The data used was adopted from Credit Card Transactions Fraud Detection Dataset in Kaggle. The data is a simulated credit card transaction dataset containing legitimate and fraud transactions from the duration 1st Jan 2019 - 31st Dec 2020. It covers credit cards of 1000 customers doing transactions with a pool of 800 merchants. This dataset was obtained from the United States.

The dataset is split into a training data and test data in order to quantitfy the accuracy of the model.

NOTE: In the approach given in the question it is indicated that we should label past transactions as fraud or fair transactions forming the target variable but we were able to get data with the fraud target variable. Therefore this is not a step that is addressed in this assignment. We used a supervised learning approach in this assignment

Only certain columns and from the kaggle dataset were incorporated into the dataset that was used and they are:

"Transaction Number" - Unique identifier for the Transactions
"Customer ID" - Unique identifier for the customers
"Time stamp" - Indicates time of the transaction
"Category" - This is the category of what was purchased
"Amount Transacted" - This is the amount of the transaction
"First Name" - First name of the customer
"Last" - Last name of the customer
"Gender" - Gender of customer
"Street" - Street name where the customer is registered
"City" - City name where the customer is registered
"Is fraud" - This is the target variable
New custom columns which were added are:

"Credit Limit" - Limit of credit that each customer is worth
"Number of Transactions" - Number of attempted transactions
"Amounts received per day" - Amounts received per day
"Card Type" - The card level type
"Authentication" - Whether the authenication passed or failed
NOTE: The values in the amount transacted column to were changed in order to better train the model. This is explained below:

287 entries were extracted from the kaggle dataset. However custom features were added as mentioned. The 287 entries include both fraudulent and legitimate transactions. To make the columns more meaningful the following logic was used:

The dataset was adjusted to only contains 1 or 2 legitimate transactions every day in order to make the 'number of transactions' column a useful predictor for fraud. The majority of the fraudulent transactions in the dataset had more than two transactions every day.
Each person received a particular card type with a set credit limit, and in some fraud cases, it was included situations where the limit is exceeded in order to make the credit limit and card type useful predictors for fraud. For a particular card type, there are different credit limits, for example the signature card has a credit limit of both 400,000 and 500,000, the gold card has a credit limit of 600,000, 700,000 and 750,000 and the platinum card has a credit limit of 900,000 and 1,000,000.
An authentication field was included that returns success after a successful transaction, and fail whenever a transaction is unsuccessful. To make this column a useful predictor, fail cases were created for the fraudulent transactions.
