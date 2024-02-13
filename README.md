# Predictive-Analysis
This project explores machine learning algorithms and data analysis to forecast supermarket sales and sales optimization.

## Table of Contents

-[Introduction](introduction)


## Introduction

This project aims to explore the historical sales dataset from the Kaggle dataset named "Supermarket Sales," which offers a historical record of sales across three branches. This dataset will be used to develop a predictive model capable of forecasting each branch's total sales. The [dataset](https://www.kaggle.com/datasets/aungpyaeap/supermarket-sales/download?datasetVersionNumber=3) contains three months of recorded data from three distinct branches (A, B, and C). With 1000 rows and 17 columns, it covers attributes like date, time, branch, customer type, product line, quantity, unit price, tax, total, payment, and rating. The dataset is available in CSV and Excel formats and can be obtained via the provided link. 

## Features Information

The dataset includes the following features:

* Invoice ID: A unique identifier for the transaction
* Store Branch: Designated code for the specific supermarket location (A, B, or C)
* City: Geographic location of the supermarket outlets
* Customer Category: Classification of customers based on their membership status ("Members" or "Normal")
* Customer Gender: The reported gender of the customer
* Product Category: Classification of items into groups such as Electronic Accessories, Fashion Accessories, Food and Beverages, Health and Beauty, Home and Lifestyle, Sports and Travel
* Item Unit Price: The cost per individual item in US dollars
* Purchase Quantity: The total count of items bought by the customer
* Sales Tax: A fixed 5% tax rate applied to the customer's purchase
* Total Price: The final amount payable, inclusive of sales tax
* Purchase Date: The specific day when the transaction occurred (January 2019 to March 2019)
* Purchase Time: The time of day when the purchase was made (between 10 am and 9 pm)
* Payment Method: The type of payment utilized by the customer (Cash, Credit Card, or E-wallet)
* Product COGS: The cost incurred to sell the goods
* Margin Percentage: The percentage representing the gross margin
* Gross Earnings: The total income before deductions, excluding sales tax
* Customer Satisfaction Rating: The customer's rating of their shopping experience (on a scale from 1 to 10)

## Tools
- Excel - Utilized for initial data investigation to gain a comprehensive overview of the dataset.
- Jupyterlab (Python) -  Python serves as the primary programming language for data analysis and machine learning. JupyterLab offers an interactive development environment for creating and sharing documents integrating live code, equations, visualizations, and text.
- Python Libraries - Pandas and numpy furnish essential data structures and operations for numerical and tabular data manipulation. Matplotlib provides data visualization capabilities, crafting diverse plots and charts. sklearn, meanwhile, assists in data modeling.
- Chatgpt - Leveraged for clarifying concepts, generating explanations, and gaining additional insights into the data.
  
## Data Preprocessing

To prepare the dataset for analysis, the following preprocessing steps were taken:

* Removal of missing values
* Correction of incorrect data types
* Removal of duplicate data
* Handling of outliers using the Interquartile Range (IQR) method
* Standardization of selected features to a common scale
* Encoding of categorical variables using one-hot encoding

## Predictive Modeling Techniques

Three different predictive models were developed to forecast the total sales of each branch:

1. Random Forest Regressor (Model 1)
2. Neural Network Regressor (Model 2)
3. Linear Regressor (Model 3)

## Model Evaluation

The following evaluation metrics were used to assess the performance of the predictive models:

* Mean Absolute Error (MAE)
* Mean Squared Error (MSE)
* R-squared (R²)

A scatter plot visualization was used to illustrate the alignment between actual and predicted values, providing a nuanced interpretation of the models' effectiveness.

## Results and Interpretation

Based on the evaluation metrics, the Random Forest Regressor (Model 1) emerged as the best-performing model with an MAE of 0.794, an MSE of 3.324, and an R² of 0.9999. The model's predictions are relatively close to the actual values, indicating that it can accurately forecast the total sales of each branch.

## Conclusion

The Supermarket Sales Predictive Analysis project demonstrates the potential of predictive analytics in providing valuable insights for informed decision-making. By accurately forecasting each branch's total sales, stakeholders can proactively manage inventory levels, inform targeted marketing strategies, and ultimately drive customer engagement and boost sales.

## Recommendations

To ensure sustained accuracy, stakeholders are recommended to commit to continuous improvement by regularly updating the predictive model with fresh data and exploring advanced techniques. Feedback loops should also be incorporated to ensure that the model remains at the forefront of evolving retail dynamics.

## Limitations and Future Work

While the selected model performs admirably, certain considerations warrant attention. The Neural Network (Model 2) introduces computational intensity, potentially posing challenges in resource-constrained environments. To mitigate this, future efforts should focus on exploring computational optimization strategies to streamline Neural Network computations. Furthermore, acknowledging the models' assumption that the future mirrors the past, there is scope for improvement in adapting to unforeseen shifts. Dynamic model updating mechanisms should be investigated to ensure adaptability to evolving sales patterns. On the data front, regular quality checks are imperative to uphold model effectiveness, and proactive measures to mitigate biases in data collection are essential for ensuring fair and unbiased predictions.

## Challenges and Limitations

Navigating challenges and limitations in the project primarily involves tackling data quality issues, exploring the dataset, and selecting suitable models. Notable hurdles include handling missing values and outliers effectively, encoding categorical variables for numerical analysis, addressing imbalanced classes potentially affecting model performance, resolving multicollinearity issues, and dealing with non-linear relationships demanding complex models or feature engineering.
To mitigate these obstacles, several strategies are proposed, including employing data cleaning and preprocessing techniques like handling missing values, outliers, and encoding categorical variables, conducting data exploration and visualization such as correlation analysis, employing feature selection methods, and experimenting with diverse machine learning models and algorithms, including linear regression, logistic regression, decision trees, and random forests.
