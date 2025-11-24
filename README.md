# 🏡 House Price Prediction

Predicting house prices using Linear Regression with features like square footage, number of rooms, location, and house quality. This project demonstrates data cleaning, feature engineering, model building, evaluation, and interpretation.

## Project Overview

Goal: Predict house prices and understand which features most influence value.

Dataset: Housing dataset with columns like sqft_living, sqft_basement, bedrooms, bathrooms, grade, view, zipcode, etc.

Techniques Used:

* Data Cleaning & EDA

* Feature Engineering (total_sqft, house_age, price_per_sqft, total_bathrooms)

* Train/Test Split

* Feature Scaling (StandardScaler)

* Linear Regression

* Cross-Validation

* Model Evaluation (MAE, RMSE, R²)

* Feature Interpretation (coefficients)

## Exploratory Data Analysis (EDA)

- Distribution of house prices

<img width="400" height="250" alt="Histplot - SalePrice distribution" src="https://github.com/user-attachments/assets/0a0da942-6f56-438b-8b68-36e7c1440bf6" />

- Correlation heatmap between features and price

<img width="400" height="250" alt="Heatmap - Top Correlations with Price" src="https://github.com/user-attachments/assets/0a9496a6-0b17-46b0-96a9-c522e1a82aee" />

- Scatter plot: sqft_living vs price

<img width="400" height="250" alt="Scatterplot - Area vs Price" src="https://github.com/user-attachments/assets/972516e8-0eff-490b-8ddc-76b22bc58693" />

- Boxplot: grade vs price

<img width="400" height="250" alt="Boxplot - Zipcode vs Price" src="https://github.com/user-attachments/assets/a2e453b5-84d7-4218-9587-5e8338da4f41" />

These visuals show which features are most correlated with price and highlight outliers.

## Feature Engineering

Created meaningful features to improve model performance:

* price_per_sqft = price / sqft_living

* house_age = year_sold - yr_built

* total_sqft = sqft_living + sqft_basement

* total_bathrooms = full + 0.5 * half baths

* Dropped irrelevant columns like id, date, yr_built, yr_renovated.

## Modeling

Linear Regression was used as the baseline and final model:

MAE: $52,251
RMSE: $80,107
R² Score: 0.91
Cross-validation R²: 0.91 (stable across folds)

* Predicted vs Actual Plot:

<img width="400" height="250" alt="Scatterplot - Predicted vs Actual House Prices" src="https://github.com/user-attachments/assets/0e546913-9991-49ae-93bc-6a783fe58737" />

* Residual Distribution:
<img width="400" height="250" alt="Histplot - Residual distribution" src="https://github.com/user-attachments/assets/52581719-9cfa-4aa4-a69c-c922b4b034c5" />

## Feature Importance (Top Coefficients)

**Top Positive (increase price):**

+ price_per_sqft
+ sqft_living
+ sqft_above
+ sqft_basement
+ grade

**Top Negative (decrease price):**

+ zipcode
+ sqft_lot
+ floors
+ bedrooms

**Insights:**

* Larger houses and higher-quality grades strongly increase price.

* Location and view matter significantly.

* Lot size and number of rooms are less predictive when controlling for overall size and quality.

## Conclusion

Linear Regression provides a simple yet effective model for predicting house prices. Feature engineering and coefficient interpretation offer actionable insights for buyers, sellers, or real estate investors.

**Portfolio Value:**

* Demonstrates end-to-end ML workflow

* Highlights data-driven insights

* Includes visualizations and interpretability
