# Predictive-Analysis
This project explores machine learning algorithms and data analysis to forecast supermarket sales and sales optimization.

## Table of Contents

- [Introduction](#introduction)
- [Data Source](#data-source)
- [Features Information](#features-information)
- [Tools](#tools)
- [Data Preprocessing](#data-preprocessing)
- [Predictive Modeling Techniques](#predictive-modeling-techniques)
- [Model Evaluation](#model-evaluation)
- [Results and Interpretation](#results-and-interpretation)
- [Conclusion](#conclusion)
- [Recommendations](#recommendations)
- [Limitations and Future Work](#limitations-and-future-work)
- [Challenges and Limitations](#challenges-and-limitations)


## Introduction

This project aims to explore the historical sales dataset from the Kaggle dataset named "Supermarket Sales," which offers a historical record of sales across three branches. This dataset will be used to develop a predictive model capable of forecasting each branch's total sales. The [dataset](https://www.kaggle.com/datasets/aungpyaeap/supermarket-sales/download?datasetVersionNumber=3) contains three months of recorded data from three distinct branches (A, B, and C). With 1000 rows and 17 columns, it covers attributes like date, time, branch, customer type, product line, quantity, unit price, tax, total, payment, and rating. The dataset is available in CSV and Excel formats and can be obtained via the provided link. 

## Data Source

The data for this project is sourced from Kaggle, a renowned platform hosting data science and machine learning competitions. This dataset encompasses sales transaction details from a supermarket's three branches over three months. Collected via the supermarket's point of sale system, it comprises variables like date, time, customer type, product line, unit price, quantity, tax, total, payment method, branch, and city.

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

  
' ' '

    #Display information about the dataset such as data type and missing values
    sales_data.info()

  
 ' ' '
 
This is the output:

' ' '

      <class 'pandas.core.frame.DataFrame'>
      RangeIndex: 1000 entries, 0 to 999
      Data columns (total 17 columns):
      #   Column          Non-Null Count  Dtype  
      ---  ------          --------------  -----  
      0   Invoice ID      1000 non-null   object 
      1   Branch          1000 non-null   object 
      2   City            1000 non-null   object 
      3   Customer type   1000 non-null   object 
      4   Gender          1000 non-null   object 
      5   Product line    1000 non-null   object 
      6   Unit price      1000 non-null   float64
      7   Quantity        1000 non-null   int64  
      8   Tax 5%          1000 non-null   float64
      9   Total           1000 non-null   float64
      10  Date            1000 non-null   object 
      11  Time            1000 non-null   object 
      12  Payment         1000 non-null   object 
      13  cogs            1000 non-null   float64
      14  gross margin percentage  1000 non-null   float64
      15  gross income    1000 non-null   float64
      16  Rating          1000 non-null   float64
      dtypes: float64(7), int64(1), object(9)
      memory usage: 132.9+ KB 
' ' '


This output reveals the dataset comprises 1000 rows and 17 columns, with no missing values detected. However, certain columns hold object data types, indicating they represent categorical variables.

## Predictive Modeling Techniques

Three different predictive models were developed to forecast the total sales of each branch:

1. Random Forest Regressor (Model 1)
2. Neural Network Regressor (Model 2)
3. Linear Regressor (Model 3)

' ' '
      
      models = {
      "RandomForestRegressor": RandomForestRegressor(n_estimators=100, random_state=42),
      "MLPRegressor": MLPRegressor(random_state=42, max_iter=500), # just in case, i will increase the max_iter to 500 to handle any convergence warning
      "LinearRegression": LinearRegression()
      }
' ' '

## Model Evaluation

The following evaluation metrics were used to assess the performance of the predictive models:

* Mean Absolute Error (MAE)
* Mean Squared Error (MSE)
* R-squared (R²)


 ' ' '
      
      mae = mean_absolute_error(y_test, predictions)
      mse = mean_squared_error(y_test, predictions)
      r2 = r2_score(y_test, predictions)
  
      print(f'{model_name} Evaluation:')
      print(f'Mean Absolute Error (MAE): {mae}')
      print(f'Mean Squared Error (MSE): {mse}')
      print(f'R-squared (R2): {r2}')
  ' ' '
  
This is the result of the model evaluation

' ' '

      RandomForestRegressor Evaluation:
      Mean Absolute Error (MAE): 0.7944168090452193
      Mean Squared Error (MSE): 3.3236542063460033
      R-squared (R2): 0.9999484283103733


      MLPRegressor Evaluation:
      Mean Absolute Error (MAE): 22.89302709215442
      Mean Squared Error (MSE): 753.008068680598
      R-squared (R2): 0.9883159029208719


      LinearRegression Evaluation:
      Mean Absolute Error (MAE): 6.909938841104191e-14
      Mean Squared Error (MSE): 7.628705150753281e-27
      R-squared (R2): 1.0

      
 ' ' '
 

A scatter plot visualization was used to illustrate the alignment between actual and predicted values, providing a nuanced interpretation of the models' effectiveness.

![Random forest regression actual vs  predicted](https://github.com/Ade-Ogunbiyi/Supermarket-Sales-Predictive-Analysis/assets/159503652/d2723858-0d67-4f3c-9dd1-4ebab085177a)

![Neural Network actual vs  predicted](https://github.com/Ade-Ogunbiyi/Supermarket-Sales-Predictive-Analysis/assets/159503652/b45ecbb3-005f-4ddc-9702-f5bdf8fec47b)

![Linear regression actual vs  predicted](https://github.com/Ade-Ogunbiyi/Supermarket-Sales-Predictive-Analysis/assets/159503652/c58ea867-fc4f-43d5-bdea-c0cb49e0147e)


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
