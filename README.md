# RETAIL INVENTORY ANALYSIS AND DEMAND FORECASTING

## Abstract  
Retail businesses rely on efficient inventory management to balance supply and demand, reduce losses, and optimize sales.

This study examines a retail store inventory dataset containing sales data, inventory levels, demand forecasts, external factors such as weather and seasonal trends. Through comprehensive data preprocessing, we address missing values, remove outliers using the IQR method, and analyze demand distribution. Exploratory data analysis (EDA) reveals key insights into sales trends, product demand fluctuations, and pricing effects.

Additionally, machine learning models are employed for demand forecasting, aiming to enhance inventory decision-making. The findings from this study provide actionable insights for businesses to improve stock management, minimize wastage, and maximize revenue.

---

## 1. Introduction  
Effective inventory management is a cornerstone of successful retail operations. Businesses must balance supply and demand to prevent stockouts, overstocking, and financial losses. Traditional inventory strategies often rely on static rules or past sales trends, which may not effectively capture dynamic market conditions.

This study focuses on analyzing a retail inventory dataset that includes historical sales, stock levels, pricing, discounts, competitor pricing, and external influences such as weather and seasonality. The objective is to identify patterns that influence demand and develop predictive models to optimize inventory management.

---

## 2. Problem Statement  
Retailers often face challenges in maintaining the right stock levels due to unpredictable demand fluctuations. Overstocking leads to increased holding costs and potential product wastage, while stockouts result in lost sales and dissatisfied customers.

This study aims to bridge this gap by applying predictive modeling to improve demand forecasting. The goal is to provide businesses with actionable insights to optimize stock levels, minimize losses, and enhance retail efficiency.

---

## 3. Methodology  
Libraries used include `missingno`, `lightgbm`, `pandas`, `numpy`, `seaborn`, `matplotlib`, `sklearn`, and `boruta`.

### 3a. Data Initial Preprocessing  
Initial features include:
- Numerical: `Inventory Level`, `Units Sold`, `Units Ordered`, `Price`, `Discount`, `Holiday/Promotion`, `Competitor Pricing`
- Categorical: `Store ID`, `Product ID`, `Category`, `Region`, `Weather Condition`, `Seasonality`

Observations:
- No null values
- Right-skewed distributions for `Units Sold` and `Demand Forecast`

### 3b. Exploratory Data Analysis (EDA)
- Detected outliers in `Units Sold` and `Demand Forecast` (removed using IQR)
- Identified correlations: strong between `Inventory Level` and `Units Sold`, `Price` and `Competitor Price`
- Seasonal trends: low demand on Monday/Saturday, peaks in Feb/Jul/Nov
- Categorical feature analysis using visualizations

---

## 4. Data Processing Based on EDA  
- Outliers removed using IQR
- Data normalized and cleaned

---

## 5. Feature Engineering  
### 5a. Based on Covariance Analysis  
- Added features: `Sales Velocity`, `Effective Price`, etc.
- Only `Sales Velocity` was found significantly useful

### 5b. Based on Seasonal Trends  
- Added features derived from weekly/monthly demand patterns

---

## 6. Final Analysis and Preprocessing  
- Correlation analysis with all features
- Categorical encoding:
  - One-hot: `Store ID`, `Category`, `Region`, `Weather`, `Seasonality`, `Weekday`
  - Label Encoding: `Product ID`
- MinMaxScaler used for numerical features to normalize variance

---

## 7. Machine Learning Modeling  
### 7a. Models Used  
- **Linear Regression**: used due to strong correlations  
- **Random Forest Regressor**: to capture non-linear relationships and encoded features  
- **Bayesian Regressor**: captured seasonality and category features  
- **GradientBoost on Decision Tree Regressor**: balanced linear and non-linear, handled repeated seasonal patterns

### 7b. Results  
- **Bayesian Regressor Model** gave the best fit  
- Plots show high correlation between predictions and actual demand

---

## 8. Conclusion  
Successfully applied ML-based demand forecasting and inventory optimization.  
Results:
- Reduced overstocking and stockouts
- Improved demand accuracy
- Developed a usable dashboard

Future work includes:
- Advanced forecasting models
- Real-time data integration
- Wider retail sector testing

---

## 9. Contributions  
- **Data Preprocessing**: Nulls/outliers removed, distributions analyzed  
- **Trend Analysis**: Seasonal decomposition, outlier detection  
- **Feature Engineering**: Added new variables based on EDA  
- **ML Modeling**: Multiple regressors built and tested  
- **Team Collaboration**: Continuous meetings and mutual feedback during EDA, modeling, and validation
