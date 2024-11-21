# Sales Forecasting for SKU-Store Combinations
## Project Overview
This project focuses on building a robust predictive model for forecasting weekly sales for specific SKU-Store combinations. The main goal was to accurately predict future sales while analyzing the underlying factors contributing to sales variability.

## Data Sources
The datasets used in this project are modified versions of those from the Sales Forecasting competition on Kaggle.

- beer_train.csv: This dataset contains historical sales data for various SKUs (products) across different stores, provided on a daily basis. It includes fields such as isPromo (indicating whether the product was on promotion) and Sales (sales amount).
- id_store_sku.csv: This dataset links store IDs to specific SKUs, allowing for the identification of which store and product were involved in each sales transaction using the ts_id (time series ID).

## Project Structure
#### 1. Data Preparation

- The raw data was cleaned and formatted to ensure consistency. Missing values were handled appropriately, and date columns were converted to datetime objects for time series analysis.

#### 2. Feature Engineering
- Various lagged values, rolling averages, promotional flags, and other features were engineered to capture trends, seasonality, and short-term fluctuations in sales.
- Key features included rolling_avg_7d, is_promo_high, lag_1w, and other temporal and promotional features.

#### 3. Model Selection and Training

- Multiple regression models were evaluated for their performance on predicting total sales:
   - **Ridge Regression**
   - **Random Forest Regressor**
   - **XGBoost Regressor**
   - **LSTM (Deep Learning Model)**
- Hyperparameter tuning was conducted using GridSearchCV to find the best-performing configurations for each model.

#### 4. Walk-Forward Validation

- Time series cross-validation was used to evaluate model performance and ensure reliable sales forecasting.

#### 5. Feature Importance Analysis

- Feature importance analysis was conducted to gain insights into key drivers of sales for different SKU-Store combinations.

#### 6. Forecasting Future Sales

- The best-performing model, **XGBoost**, was used to forecast weekly sales for each SKU-Store combination for the week starting three months after the final date in the dataset.

## Key Insights and Findings
#### Best Model Performance:

- The XGBoost model consistently outperformed other models in terms of Mean Absolute Error (MAE) and Root Mean Square Error (RMSE).

- This model's adaptability to non-linear data and its ability to capture intricate sales patterns made it an ideal choice for our prediction tasks.
#### Feature Importance Highlights:

- Important features across combinations included rolling averages, isPromo flags, rolling_std_7d, and cumulative sales history.
- Promotional activity (is_promo_high) often had a strong impact on sales fluctuations, as evidenced by its importance in many SKU-Store models.

## License

[MIT](https://choosealicense.com/licenses/mit/)