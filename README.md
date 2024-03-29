# **ROSSMANN SALES FORECAST**

## Sales Predictions for ROSSMANN Stores

Rossmann operates over 3,000 drug stores in 7 European countries. Currently, Rossmann store managers are tasked with predicting their daily sales for up to six weeks in advance. Store sales are influenced by many factors, including promotions, competition, school and state holidays, seasonality, and locality. With thousands of individual managers predicting sales based on their unique circumstances, the accuracy of results can be quite varied.


<div align="center">
<p float="left">
  <img src="/images/rossman_1.jpg" width="1000" height="350"/>
</p>
</div>

***
## 1. BUSINESS PROBLEMS

Definition of the Budget for the Renovation of the Stores.

 ### 1.1 **Context:**
 
 * CFO asked for a Sales Forecast of the Next 6 weeks from each Store

### 1.2 **Causes:**

 * Current Sales Prediction showed a lot of Divergence;
 * The Sales Prediction process is based on Past Experiences;
 * All Sales Forecasting is done Manually by Rossmann's 1,115 Stores;
 * Sales visualization is Computer Limited.

### 1.3 **Solution:**

 * Use Machine Learning to Forecast All Store Sales;
 * Visualization of Sales Predictions can be done by Smartphone;

***
## 2. BUSINESS ASSUMPTIONS

The motivation for forecasting sales for the next six weeks is to be able to forecast future revenue. This offers several advantages to the CFO and management team members when it comes to planning how the company's net income will be spent:

Maintenance and renovation of existing stores
Expand company stores to gain market share
Inventory management and inventory planning
Distribution of dividends to shareholders
Evaluating forecasts with operations teams

 ### 2.1 **Assumptions:** 

- Sales have some degree of seasonality and/or periodicity that can be captured by machine learning algorithms
- Sales are impacted by store type and assortment
- Sales are impacted by promotions and extended promotions
- Sales are affected by distance from competitors

***
## 3. SOLUTION PLANNING

- [x] **Step 01:** **Data Description**:  My goal is to use statistics metrics to identify data outside the scope of business.
  - Data Dimension
  - Data types
  - Check NA
  - Fillout NA
  - Change Types
  - Descriptive Statistivas
    * Numerical Attributes
    * Categorical Attributes

- [x] **Step 02:** **Feature Engineering**: Derive new attributes based on the original variables to better describe the phenomenon that will be modeled.
  - Hypoteses Mindmap
  - Missing values
  - Outlier manipulation
  - Binning
  - One-hot encoding
  - Grouping

- [x] **Step 03:** **Data Filtering**: Filter rows and select columns that do not contain information for modeling or that do not match the scope of the business
  - Line filtering
  - Selection of columns

- [x] **Step 04:** Exploratory Data Analysis:Explore the data to find insights and better understand the impact of variables on model learning. - Line filtering
  - Univariate Analysis
  - Bivariate Analysis
  - Multivariate analysis

- [x] **Step 05:** Data Preparation
  - Rescaling
    - Min-Max Scaler
    - Robust Scaler
  - Encoding
    - One Hot Encoding
    - Label Encoding
    - Ordinal Encoding
  - Response Variable Transformation
    - Logarithm Transformation
  - Nature Transformation
    - Sine and Cosine Transformation

- [x] **Step 06:** Feature Selection
  - Embedded Methods
    - Random Forest
  - Wrapper Methods
    - Boruta

- [x] **Step 07:** Machine Learning Modelling
  - Machine Learning model training

- [x] **Step 08:** Hyperparameter Fine Tunning
  - Random Search

- [x] **Step 09:** Convert Model Performance to Business Values

- [ ] **Step 10:**  Deploy Modelo to Production

***
## 4. TOP 5 DATA INSIGHTS

**Hypothesis 01:** Stores with larger assortments should sell more
 - *Reply:* **Falso**. The first graph describes the amount of sales by type of assortment, then we have the behavior of the variables over time. And finally a linearity investigation of the extra attribute referring to the assortment variable

<div align="center">
<p float="left">
    <img src="/images/h1.png" width="600" height="500"/>
  <img src="/images/h1_1.png" width="600" height="500"/>
  <img src="/images/h1_2.png" width="600" height="500"/>
</p>
</div>

**Hypothesis 02:** Stores with closer competitors should sell less.
 - *Reply:* **Falso**. The first graph shows the relationship between sales by stores versus the distance between competitors. Where the distance is grouped from 1000 to 1000 meters. Then we have the concentration of sales by stores versus the distance of competitors. And finally, the impact of the distance variable from competitors on the response variable (sales).

<div align="center">
<p float="left">
    <img src="/images/h2.png" width="600" height="500"/>
</p>
</div>

**Hypothesis 03:** Stores with longer competitors should sell more.
 - *Reply:* **Falso.** Stores with longer competitors sell less, that is, the more recent they are, the more they sell.
The first graph shows the relationship between sales by stores versus competition time. Then we have the concentration of sales by stores versus the competition time. And finally, the impact of the competition time variable on the response variable (sales).

<div align="center">
<p float="left">
    <img src="/images/h3.png" width="600" height="500"/>
 </p>
</div>

**Hypothesis 04:** Stores with longer active promotions should sell more.
 - *Reply* **Falso.** Stores with longer active promotions (extended) sell less after a certain period of promotion. That is, it is profitable for a given time, then we have a fall.
 
<div align="center">
<p float="left">
    <img src="/images/h4.png" width="600" height="500"/>
</p>
</div>

**Hypothesis 05:** Stores with more consecutive promotions should sell more
 - *Reply:* **Falso**. The first chart shows the stores that only had the regular period. Then we have the stores that had both promotion periods (regular and extended).

<div align="center">
<p float="left">
    <img src="/images/h5.png" width="500" height="400"/>
    <img src="/images/h5_1.png" width="500" height="400"/>
</p>
</div>

***
## 5. Machine Learning Model Applied

Tests were made using different algorithms:

|                                            | MAE CV	                    | MAPE CV	          | RMSE CV       |
|--------------------------------------------|----------------------------|-------------------|---------------|
| Average Model                              | 681.70                     | 0.10              | 1013.08       | 
| Linear Regression                          | 868.96                     | 0.13              | 1238.55       | 
| Linear Regression Regularized              | 1354.80                    | 0.46              | 1835.14       |
| Random Forest Regressor                    | 1867.09                    | 0.29              | 2671.05       | 
| XGBoost Regressor                          | 1891.70                    | 0.29              | 2744.45       | 



The chosen algorithm was the **XGBoost Regressor**. In addition, I made a performance calibration on it.

***
## 6. Machine Learning Modelo Performance

The summary below shows the metrics comparison after running a cross validation score with stratified K-Fold with 5 splits in the full data set.

|                                            | MAE CV	                    | MAPE CV	               | RMSE CV                    |
|--------------------------------------------|----------------------------|------------------------|----------------------------|
| XGBoost Regressor                          |  785\.83 \(\+/\- 125\.56\) | 0\.11 \(\+/\- 0\.01\)  | 1140\.62 \(\+/\- 183\.62\) | 
| XGBoost Regressor                          | 1421\.42 \(\+/\- 145\.86\) | 0\.2  \(\+/\- 0\.01\)  | 2056\.45 \(\+/\- 199\.67\) | 
| XGBoost Regressor                          | 1819\.29 \(\+/\- 205\.8\)  | 0\.26 \(\+/\- 0\.01\)  | 2067\.47 \(\+/\- 287\.5\)  |
| XGBoost Regressor                          |  844\.47 \(\+/\- 143\.03\) | 0\.12 \(\+/\- 0\.01\)  | 1216\.9 \(\+/\- 206\.0\)   | 
| XGBoost Regressor                          |  815\.46 \(\+/\- 135\.59\) | 0\.12 \(\+/\- 0\.01\)  | 1175\.52 \(\+/\- 196\.88\) | 



***
## 7. Business Results

Let's recap the pricing model. Below we have the sales forecast for the next 6 weeks, the best and the worst. Thus, translating it to business numbers.

| Scenario	                           | Values                     | 
|--------------------------------------|----------------------------|
| predictions                          |  $ 283,814,336.00          | 
| worst_scenario                       |  $ 283,127,073.91          | 
| best_scenario                        |  $ 284,501,608.23          | 

This means that  in the **worst business scenario** the portfolio would generate a profit of **\$284.127.073.91** and in the **best scenario \$284.501.608.23**.


***
## 8. Conclusions

***
## 9. Lessons Learned

***
## 10. Next Steps to Improve

***
Made By **Camila D'Angelo**

- 🔭 I’m currently working on [DS Comuity](https://www.comunidadedatascience.com/) and [Data Science Academy](https://www.datascienceacademy.com.br/bundle/formacao-cientista-de-dados)
- 🌱 I’m currently learning Data Science
- 📫 How to reach me:  [LinkeldIn](https://www.linkedin.com/in/camiladangelotempesta/)
***
