# **ROSSMANN SALES FORECAST**

## Sales Predictions for ROSSMANN Stores

Rossmann operates over 3,000 drug stores in 7 European countries. Currently, Rossmann store managers are tasked with predicting their daily sales for up to six weeks in advance. Store sales are influenced by many factors, including promotions, competition, school and state holidays, seasonality, and locality. With thousands of individual managers predicting sales based on their unique circumstances, the accuracy of results can be quite varied.




![]()

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

- [ ] **Step 05:** Data Preparation

- [ ] **Step 06:** Feature Selection

- [ ] **Step 07:** Machine Learning Modelling

- [ ] **Step 08:** Hyperparameter Fine Tunning

- [ ] **Step 09:** Convert Model Performance to Business Values

- [ ] **Step 10:**  Deploy Modelo to Production


## 4. TOP 5 DATA INSIGHTS

**Hypothesis 01:** Stores with larger assortments should sell more
 - *Reply:* **Falso**. The first graph describes the amount of sales by type of assortment, then we have the behavior of the variables over time. And finally a linearity investigation of the extra attribute referring to the assortment variable

<p float="left">
  <img src="/images/h1.png" width="315" />
  <img src="/images/h1_1.png" width="315" /> 
  <img src="/images/h1_2.png" width="315" />
</p>
 
**Hypothesis 02:** Stores with closer competitors should sell less.
 - *Reply:* **Falso**. The first graph shows the relationship between sales by stores versus the distance between competitors. Where the distance is grouped from 1000 to 1000 meters. Then we have the concentration of sales by stores versus the distance of competitors. And finally, the impact of the distance variable from competitors on the response variable (sales).

<p float="left">
  <img src="/images/h2.png" width="750" />
</p>

**Hypothesis 03:** Stores with longer competitors should sell more.
 - *Reply:* **Falso.** Stores with longer competitors sell less, that is, the more recent they are, the more they sell.
 
 <p float="left">
  <img src="/images/h3.png" width="750" />
</p>

**Hypothesis 04:** Stores with longer active promotions should sell more.
 - *Reply* **Falso.** Stores with longer active promotions (extended) sell less after a certain period of promotion. That is, it is profitable for a given time, then we have a fall.

![]()

**Hypothesis 05:** Stores with more consecutive promotions should sell more
 - *Reply:* **Falso**

![]()


***
Made By **Camila D'Angelo**

[Portfólio](https://github.com/camila-dangelo-tempesta?tab=repositories)

[LinkeldIn](https://www.linkedin.com/in/camiladangelotempesta/)
