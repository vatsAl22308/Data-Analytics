# data analytics

## **OBJECTIVE**

This project uses historical data and derived features to predict customer churn in the banking sector. The goal is to understand the key factors that influence customer retention and to help banks make informed decisions to reduce customer attrition.

Retaining customers is more cost-effective than acquiring new ones. Therefore, this predictive model can aid in identifying high-risk customers and enable proactive measures to improve their satisfaction and loyalty.

## **Dataset Description**

The dataset consists of both raw and engineered features, capturing various aspects of customer behavior, such as:

Demographic Variables: Age, Gender, Salary, Working Status

Credit and Financial Indicators: Credit Score, Balance, Loan History

Engagement Metrics: Number of Products, Frequency of Transactions, Tenure, Complaints, and Customer Service Logs

Target Variable: Churn (1 = Exited, 0 = Retained)

The data was collected from multiple sources:

Internal banking systems (Online banking, Credit card dept.)

Customer surveys and call center logs

Market intelligence reports

# **Tools and technique** 

Languages & Libraries

Python (Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn)

Techniques Applied

Exploratory Data Analysis (EDA): To understand the data distribution, identify trends, and detect outliers

Data Preprocessing: Handling missing values outlier treatment using Clamping (e.g., for age and credit score)

Feature Engineering: Creating relevant features like Avg_Transaction_Monthly, categorizing credit scores, and summarizing complaints

Model Building: Regression and Classification techniques to predict churn

Model Evaluation: Correlation analysis and comparison of churn rates across demographic groups

# **Data quality**


**Objective**

The objective of maintaining data quality in this project is to ensure that the input dataset used for predictive modeling is:

Accurate: Free from errors, anomalies, and inconsistencies

Complete: Contains minimal missing values that could compromise the model's output.

Consistent: Uniform across all features for better interpretability

Reliable: Trustworthy enough to make critical business decisions regarding customer churn

Relevant: Includes features that contribute meaningful insights to the model.

High-quality data enhances the model’s performance, reduces bias, and ensures that business insights derived from analysis are valid and actionable.

## **Data Cleaning Process**
To ensure data quality, the following steps were applied:

1. Missing Value Treatment
Continuous variables like Age, Salary, and Credit Score had missing values.

Applied mean or median imputation depending on the skewness of the variable.

2. Outlier Detection & Treatment
Extreme values were found in features like Age and Credit Score (e.g., age values > 100, credit scores > 6800).

Used Clamping (Winsorization) technique:

Age was clipped between 14 and 62 years

Credit Score was clipped between 380 and 923

3. Categorical Consistency
Categorical variables like Gender, Geography, and Product Ownership were checked for:

Typos

Improper casing

Missing categories

Used label normalization and standard encoding to ensure consistency

4. Handling Duplicates
Checked for and removed duplicate rows to ensure no data leakage or redundancy

5. Data Type Corrections
Ensured all features had correct data types (e.g., Age as integer, Churn as categorical)

## **Data Table** 
Major outliers were identifying in Age and credit score. Max value of the credit score is 
6800 which is not practical and To solve this we have use clamp transformation by calculating 
the minimum and maximum value and clipping them into original data and further same was 
done for the Age as seen in the table it is not possible to have 129 unique data and max age 
cannot be 440. For credit card min and max value was calculated as 379.625 and 922.625 for age 
it was 14 and 62

![image](https://github.com/user-attachments/assets/74f3875f-88e0-4333-94e4-a601643af515)

The tables give us certain important insight of the data. Such as gender of the customer 
and this help us to understand who the main customer for us are and can help us to have 
marketing relevant to that here we have almost equal proportion. Mode for the Geography is 
France which means we need focus more in that region to acquire more customers. Mode % of 
12 
the data gives us information about how many of our customer has credit card and this data can 
be used for reaching out to them who doesn’t have and approach them to sell it

![image](https://github.com/user-attachments/assets/b54e8e1f-0484-4b35-a061-0c5afae702c9)

# Descriptive Analysis
## **Objective of Descriptive Analysis**
The objective of Descriptive Analysis in this project is to:

Summarize and understand the dataset by identifying key patterns, trends, and relationships among variables.

Provide insights into customer behaviors, demographics, and financial characteristics to better understand the factors influencing churn.

Identify data anomalies, such as missing values and outliers, that could impact model performance.

Segment customers based on attributes like age, gender, credit score, and product usage to uncover high-risk groups.

Support feature selection by evaluating the importance and distribution of each variable in relation to the target variable (Churn).

## **Correlation of variables**

![image](https://github.com/user-attachments/assets/0243f0b9-c915-474c-9621-e4ab580a0a47)


# **Demographic Analysis**

Significant difference can be seen by analysing the gender it shows that the female 
customers are more likely to be exit more. Possible reason can be low credit score of the females 
generally females have low credit score which leads to higher rate of interest. Further analysis 
shows that the younger people has the lowest risk of leaving the bank. It is believe that as 
customers get older they start planning for the safer income and young people has higher appetite 
for this risk and older people refrain to takes risk and moves towards other financial institution 
who gives higher interest rate

![image](https://github.com/user-attachments/assets/95695511-7778-459c-8fff-cd77a5e67997)


## **Diagnostic Analysis**

The primary objective of Diagnostic Analysis in this project is to:

Identify the root causes behind customer churn by examining relationships between key features and the churn outcome.

Uncover patterns and triggers that contribute to customer exits, such as low credit scores, high product ownership, or specific demographic traits.

Validate assumptions formed during descriptive analysis with deeper insights into “why” certain behaviors occur.

Compare subgroups (e.g., churned vs. retained customers) to reveal the most influential variables affecting churn.

Guide business decision-making by highlighting areas of concern, such as service dissatisfaction, risky credit behavior, or ineffective product bundling.

Support predictive modeling by narrowing down the most relevant variables for feature selection and engineering.


## **Demographic Analysis:**    

Significant difference can be seen by analysing the gender it shows that the female 
customers are more likely to be exit more. Possible reason can be low credit score of the females 
generally females have low credit score which leads to higher rate of interest. Further analysis 
shows that the younger people has the lowest risk of leaving the bank. It is believe that as 
customer get older they start planning for the safer income and young people has higher appetite 
for this risk and older people refrain to takes risk and moves towards other financial institution 
who gives higher interest rate 

![image](https://github.com/user-attachments/assets/c6c90a31-692e-4b59-ad86-88fc22271511)


![image](https://github.com/user-attachments/assets/75859668-9044-4ec9-9c75-7b4ac9c9d238)


### **Credit Analysis**

Although there is no such major difference in credit score among various age group 
however we try to compare the previous analysis with this the same age group whose churn rate 
was higher has the low credit score maybe the assumption we made on above analysis of getting 
settle paying out loans and having a transition to a safer option have some effect in credit score 
and both the parameters have connection with each other.

![image](https://github.com/user-attachments/assets/f018961b-f594-4c90-a5b5-7c4c39a5f932)


## **Product Analysis** 

Majorly 4 products are provided by the bank and a customer who has 2 products has the 
lowest churn rate and customers with the 4 products have the highest churn rate. Further-more 
analysis was done for each product, and what’s the average age credit score, active or inactive? It 
can be interpreted that the customers with 2 products are younger most of  them are active and have 
higher credit score might be very useful for marketing and it is very easy to tell that 
customer with more products got too many products which they can handle and ultimately forced 
to leave the bank

![image](https://github.com/user-attachments/assets/cbac5a61-a271-4fbd-b0be-6c4aec8aeca1)

## **Financial Analysis** 
The final analysis kind of help us to sum up the analysis by supporting the previous 
analysis the below figure shows that the older age people has the more balance which proves that 
the people are playing more safe game and accumulating the money for the retirement and prefer 
to got the institution that pays them higher rate of interest

![image](https://github.com/user-attachments/assets/ed55ab59-f4bd-4c05-a106-933e23d21b92)

## **Recommendation **
Focus more on the middle age group: As clearly explain above the analysis supports that the 
bank should focus more on age group by introducing the products which meets their need and to 
provide attractive rate of interest which will make them stick to banking institution. Focus more 
on providing attractive retirement option for old age people such as providing services with 
lower banking charges helping customer and to prepare them for retirement. 
Focusing more on gender: Introducing some products which is related to the females and 
20 
reaching them effectively my introducing relevant marketing and providing some free services 
for initial phase.














