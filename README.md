# Telco Customer-Churn-Analysis
# Executive Summary: Customer Churn Analysis

## 1. Project Introduction

Customer churn is one of the major challenges faced by subscription-based businesses. It refers to customers discontinuing their services or ending their relationship with a company.

The objective of this project is to perform an in-depth Exploratory Data Analysis (EDA) of customer information to identify patterns, understand customer behaviour, and investigate the factors associated with customer churn.

Using Python and its data analysis and visualization libraries, I analyzed customer demographics, service subscriptions, contract types, tenure, billing information, and payment methods.

The analysis focuses on answering important business questions:

- What percentage of customers are leaving the company?
- Which customer groups are more likely to churn?
- Does customer tenure influence customer retention?
- Which contract types are associated with higher churn?
- How do different services relate to customer retention?
- Does the payment method have any relationship with customer churn?
- What strategies could help the company improve customer retention?

## 2. Dataset Overview

The analysis was performed using a Telco Customer Churn dataset.

| Dataset Information | Details |
|---|---:|
| Total customer records | 7,043 |
| Total columns | 21 |
| Numerical columns | 4 after preprocessing |
| Categorical columns | 17 after preprocessing |
| Duplicate customer records | 0 |
| Missing values after preprocessing | 0 |

The dataset contains information about the following categories:

**Customer Demographics**
- Gender
- SeniorCitizen
- Partner
- Dependents

**Customer Account Information**
- CustomerID
- Tenure
- Contract
- PaperlessBilling
- PaymentMethod

**Subscribed Services**
- PhoneService
- MultipleLines
- InternetService
- OnlineSecurity
- OnlineBackup
- DeviceProtection
- TechSupport
- StreamingTV
- StreamingMovies

**Billing Information**
- MonthlyCharges
- TotalCharges

**Target Variable**
- Churn

## 3. Data Cleaning and Preprocessing

Before performing Exploratory Data Analysis, I inspected and cleaned the dataset to improve data quality and ensure accurate analysis.

The following preprocessing steps were performed:

1. Imported the dataset using Pandas.
2. Examined the dataset structure using `df.info()`.
3. Checked numerical distributions using `df.describe()`.
4. Identified blank values in the TotalCharges column.
5. Replaced blank TotalCharges values with zero for customers with zero tenure.
6. Converted TotalCharges from object to float data type.
7. Checked missing values using `df.isnull().sum().sum()`.
8. Checked duplicate customer records using the customerID column.
9. Converted SeniorCitizen values from 0 and 1 into Yes and No categories for better readability.

**Data Quality Results**

- Total records processed: 7,043.
- Missing values after preprocessing: 0.
- Duplicate customer records: 0.
- TotalCharges successfully converted into numerical format.

These preprocessing steps prepared the dataset for further statistical analysis and visualization.

## 4. Exploratory Data Analysis and Key Findings

### 4.1 Overall Customer Churn Analysis

The first analysis examined the overall distribution of customers based on their churn status.

I used a bar chart and a pie chart to understand the number and percentage of customers who stayed with the company and those who discontinued their services.

**Key Findings**

| Customer Status | Customers | Percentage |
|---|---:|---:|
| Stayed | 5,174 | 73.46% |
| Churned | 1,869 | 26.54% |
| Total | 7,043 | 100% |

**Business Insight**

Approximately 26.54% of the total customers have churned, meaning that more than one out of every four customers discontinued the company's services.

This indicates a considerable customer retention challenge.

The company should investigate the factors responsible for customer attrition and develop strategies to retain existing customers.

### 4.2 Gender-Based Customer Analysis

I analyzed customer distribution by gender and compared churn behaviour between male and female customers using count plots.

**Analysis Performed**

- Compared the number of male and female customers.
- Examined churn distribution across both gender categories.
- Used grouped count plots to compare customers who stayed and customers who churned.

**Business Insight**

Gender-based analysis helps determine whether customer churn behaviour differs significantly between male and female customers.

However, the number of customers in each category should be considered when interpreting churn counts.

The notebook does not contain calculated gender-specific churn percentages, so a definitive difference in churn rates cannot be established from the current chart alone.

### 4.3 Senior Citizen Analysis

I analyzed customer distribution based on senior citizen status.

The original numerical values were converted into Yes and No categories to improve chart readability.

According to the dataset statistics, approximately 16.21% of customers belong to the senior citizen category, while 83.79% are non-senior citizens.

**Customer Distribution**

| Customer Category | Percentage |
|---|---:|
| Senior Citizens | 16.21% |
| Non-Senior Citizens | 83.79% |
| Total | 100% |

I created count plots and a percentage-based stacked bar chart to compare churn behaviour between the two groups.

**Business Insight**

The percentage-based stacked chart allows a fairer comparison of churn distribution within each customer category.

It is more informative than comparing only the number of churned customers because the two groups have different population sizes.

Senior citizen status should be considered alongside other factors such as tenure, contract type, and service subscriptions when developing customer retention strategies.

### 4.4 Customer Tenure Analysis

Customer tenure represents the number of months a customer has remained associated with the company.

I used a histogram with churn-based grouping to understand the relationship between customer tenure and churn behaviour.

**Key Findings**

- Customers with shorter tenure, particularly those with one or two months of service, show a higher concentration of churn.
- Customers with longer tenure are more frequently represented among those who stay.
- The analysis suggests that customer retention is particularly important during the early stages of the customer relationship.

The average customer tenure is approximately 32.37 months.

**Business Insight**

The first few months of a customer's relationship appear to be an important retention period.

The company should focus on improving the onboarding experience, providing effective customer support, and identifying early signs of dissatisfaction.

Early engagement programs and targeted retention offers could help reduce customer attrition.

### 4.5 Contract-Based Customer Churn Analysis

Contract type is an important factor in understanding customer retention.

I compared three contract categories:

- Month-to-month
- One year
- Two year

Using count plots, I examined how customer churn is distributed across different contract types.

**Key Findings**

- Month-to-month contract customers show substantially higher churn counts.
- Customers with one-year contracts demonstrate better retention patterns.
- Two-year contract customers show comparatively stronger retention.

**Business Insight**

Customers with month-to-month contracts may have greater flexibility to discontinue their subscriptions.

Long-term contracts are associated with stronger customer retention in this dataset.

The company could encourage customers to choose longer contracts by offering loyalty benefits, attractive discounts, and additional service benefits.

For a more accurate comparison, the churn rate should be calculated separately for each contract category rather than comparing only churn counts.

### 4.6 Service-Based Customer Analysis

I analyzed nine service-related variables to understand customer subscriptions and their relationship with churn.

The following services were examined:

| Service | Analysis Focus |
|---|---|
| PhoneService | Phone service subscription |
| MultipleLines | Multiple phone line subscriptions |
| InternetService | Type of internet connection |
| OnlineSecurity | Online security subscription |
| OnlineBackup | Online backup subscription |
| DeviceProtection | Device protection subscription |
| TechSupport | Technical support subscription |
| StreamingTV | Television streaming subscription |
| StreamingMovies | Movie streaming subscription |

I created two sets of visualizations:

1. Count plots to understand customer distribution across service categories.
2. Churn-based grouped count plots to compare customers who stayed and customers who churned.

**Key Findings**

- PhoneService and InternetService represent important parts of the customer service distribution.
- DSL and Fiber optic are important internet service categories.
- Customers without additional services such as OnlineSecurity and TechSupport show notable churn patterns.
- OnlineBackup, DeviceProtection, StreamingTV, and StreamingMovies provide further opportunities to investigate differences in customer behaviour.

**Business Insight**

The company should investigate whether customers without additional support and security services experience lower satisfaction or perceive less value from their subscriptions.

Offering relevant additional services, improving service quality, and communicating the benefits of available subscriptions could support customer retention.

These findings indicate associations, not proof that subscribing to a particular service directly prevents churn.

### 4.7 Payment Method Analysis

Payment method is another important factor examined in this project.

I compared customer churn across four payment methods:

- Electronic Check
- Mailed Check
- Bank Transfer (Automatic)
- Credit Card (Automatic)

A grouped count plot was used to compare churned and retained customers across these categories.

**Key Findings**

- Electronic Check shows a notably high number of churned customers.
- Automatic payment methods show comparatively different churn distributions.
- Payment behaviour is an important area for further customer retention investigation.

**Business Insight**

Customers using Electronic Check appear to represent an important group for further investigation.

The company should understand whether payment convenience, billing experience, payment reliability, or other customer characteristics are associated with this pattern.

Encouraging convenient automatic payment options and improving billing communication could be useful strategies to test.

## 5. Overall Business Insights

Based on the exploratory analysis, the following factors deserve particular attention:

| Factor | Observation | Business Importance |
|---|---|---|
| Overall Churn | 26.54% customers churned | High |
| Customer Tenure | Short-tenure customers show greater churn concentration | High |
| Contract Type | Month-to-month customers show higher churn counts | High |
| Payment Method | Electronic Check shows notable churn counts | High |
| Additional Services | Security and support subscriptions show useful churn patterns | Medium |
| Senior Citizen | Demographic differences need further investigation | Medium |
| Gender | Churn differences need percentage-based comparison | Medium |

## 6. Business Recommendations

Based on the findings, I recommend the following actions:

**1. Improve Early Customer Retention**

Develop a customer onboarding strategy for newly registered customers, particularly during the first few months.

**2. Encourage Long-Term Contracts**

Introduce attractive offers, loyalty rewards, and discounts to encourage customers to select one-year and two-year contracts.

**3. Improve Customer Support**

Promote TechSupport and OnlineSecurity services and investigate whether customers without these services face more service-related difficulties.

**4. Improve Payment Experience**

Investigate the high churn counts associated with Electronic Check users and encourage convenient payment options.

**5. Develop Customer Segmentation**

Group customers based on tenure, contract type, service subscriptions, and demographic characteristics to develop more targeted retention strategies.

**6. Monitor Customer Churn Regularly**

Create a customer churn monitoring dashboard to track churn rates, customer retention, and changes in customer behaviour over time.

## 7. Project Conclusion

This project demonstrates how Exploratory Data Analysis can transform raw customer information into meaningful business insights.

By analyzing 7,043 customer records across 21 columns, I investigated customer demographics, service subscriptions, tenure, contract types, and payment methods.

The analysis identified an overall customer churn rate of 26.54%, highlighting the importance of improving customer retention.

The findings particularly emphasize short customer tenure, month-to-month contracts, and Electronic Check payment patterns as important areas for further investigation.

Through data cleaning, statistical analysis, and visualizations, this project demonstrates my practical understanding of data analysis and my ability to communicate analytical findings through business-oriented insights.

**The ultimate objective is to help businesses understand customer behaviour, identify potential retention challenges, and make better data-driven decisions.**

## 8. Tools and Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

**Project Type:** Exploratory Data Analysis (EDA)

**Domain:** Telecommunications

**Primary Business Objective:** Customer Retention and Churn Analysis
