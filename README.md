# bike_sharing_ml
Predict hourly bike rentals using historical data from the UCI Bike Sharing Dataset.  
This project demonstrates **EDA, preprocessing, feature engineering, multiple ML models, and model evaluation** for a regression problem.

---

## Dataset
- **Source:** [UCI Bike Sharing Dataset](https://archive.ics.uci.edu/ml/datasets/Bike+Sharing+Dataset)  
- **Columns include:** season, hour, temperature, humidity, weather, and bike rental counts.

---

## Project Workflow

1. **Exploratory Data Analysis (EDA)**
   - Analyzed bike rental trends over hours, days, seasons
   - Observed relationships between temperature, weather, and rental counts
   - Detected peak hours and seasonal patterns

2. **Preprocessing**
   - Handle missing values 
   - Scale numeric features (temperature, humidity, windspeed)
   - Encode categorical variables (season, weather)
   - Generate cyclical features for hour and day of week

3. **Modeling**
   - Linear Regression
   - Random Forest Regressor
   - Gradient Boosting Regressor
   - XGBoost Regressor
   - Neural Network (MLPRegressor)

4. **Evaluation Metrics**
   - RMSE
   - MAE
   - R²
   - MAPE

5. **Visualizations**
   - Actual vs Predicted plots for each model
   - Feature importance for tree-based models
   - Distribution of rentals over hours, seasons, and weather conditions

---

## Plots

**Correlation Heatmap of Features**

![Correlation Heatmap](images/correlation_heatmap.png)


**Distribution of Bike Rental Counts**

![Distribtion of Bike Rental](images/distribution_of_bike_rental_count.png)


**Bike Rentals by Season**

![Bike Rental by Season](images/bike_rental_by_season.png)


**Hourly Bike Rentals(Workingday vs Non-Workingday)]**

![Hourly Bike Rentals](images/hourly_bike_rentals.png)


**Bike Rentals by Weather Situation**

![Bike Rentals by Weather](images/bike_rental_by_weather.png)


**Temperature vs Bike Rentals**

![Temperature vs Bike Rentals](images/temperature_vs_bike_rental.png)

---

 ## Exploratory Data Analysis & Key Insights

This project focuses on forecasting hourly bike rental demand using machine learning models. Prior to model development, extensive exploratory data analysis (EDA) was conducted to understand the underlying patterns, relationships, and drivers of demand.



1.**Correlation Analysis**

A correlation heatmap was created to analyze linear relationships between numerical features and the target variable (count).

- *Key Findings:*

  - Hour of the day shows the strongest correlation with rental demand, highlighting the importance of time-based behavioral patterns.

  - Temperature has a high positive correlation with demand, indicating increased bike usage during warmer conditions.

  - Features such as humidity and wind speed exhibit weaker or negative correlations, suggesting a lesser influence on rental volume.

- *Interpretation:*

   -  Rental demand is heavily influenced by daily routines and weather comfort, making temporal and temperature features critical for accurate forecasting.

2.**Seasonal Demand Distribution (Box Plot)**

Box plots were used to visualize demand distribution across seasons.

- *Observed Trend:*

  - Summer exhibits the highest median and overall rental demand

  - Followed by Spring, Fall, and Winter

  - Winter shows lower medians with higher variability, indicating inconsistent usage due to adverse weather conditions

- *Interpretation:*

   - Seasonality plays a significant role in demand fluctuations, and seasonal indicators should be incorporated into the model to capture long-term trends.

3.**Hourly Demand Patterns (Line Plots)**

Hourly demand trends were analyzed separately for working days and weekends.

- Working Days

  - Two distinct peaks observed:

  - Morning peak: 6–9 AM

  - Evening peak: 4–8 PM

These peaks align with commuting hours

- Weekends

   - Demand is more evenly distributed throughout the day

   - Highest usage occurs between 12–5 PM

   - Overall demand spread is wider compared to weekdays

- *Interpretation:*

  - Weekday demand is driven by commuter behavior, while weekend demand reflects leisure and recreational usage, leading to flatter but broader demand curves.

4. **Temperature vs Demand Relationship (Scatter Plot)**

A scatter plot was used to analyze the relationship between temperature and rental demand.

- *Key Observations:*

  - Rental demand increases steadily with temperature

  - At higher temperatures, low rental counts are rare

  - Indicates a strong monotonic relationship between comfort and usage

- *Interpretation:*

  - Temperature acts as a critical enabling factor for bike usage. Once favorable weather conditions are met, demand remains consistently high.

---

## Model Development

- Multiple regression models were trained and evaluated:

- XGBoost

- Random Forest

- Gradient Boosting

- Neural Network

---

## Model Performance

**Linear Regression: Actual vs Predicted**

![Linear Regression plot](images/linear_regression_actual_vs_predicted.png)


**Random Forest: Actual vs Predicted**

![Random Forest plot](images/random_forest_actual_vs_predicted.png)


**Gradient Boosting: Actual vs Predicted**

![Gradient Boosting plot](images/gradient_boosting_actual_vs_predicted.png)


**XGBoost: Actual vs Predicted**

![XGBoost plot](images/xgboost_actual_vs_predicted.png)


**Neural Network: Actual vs Predicted**

![Neural Network plot](images/neural_network_actual_vs_predicted.png)


**Performance Comparison of all Models**

![Model Performace - all](images/model_performance.png)

---

## Model Key Insights

1.**Linear Regression**

  - Worst performance (R² ≈ 0.40, very high RMSE & MAE).

  - Fails to capture nonlinear relationships in bike rentals.

2.**Tree-based models (Random Forest, Gradient Boosting, XGBoost)**

  - XGBoost slightly outperforms others on R² and RMSE.

  - Random Forest is very strong too (slightly higher RMSE than XGBoost).

  - These models handle nonlinearities and interactions between features (hour, temperature, weather) very well.

3.**Neural Network**

  - Decent performance (R² ≈ 0.93).

  - RMSE & MAPE higher than XGBoost/Random Forest → may need more tuning or feature scaling adjustments.

4.**MAPE insights**

  - Linear Regression has huge MAPE (~356%) → predicts poorly for small or extreme rental counts.

  - Random Forest & XGBoost have low MAPE (~31–38%) → predictions are relatively accurate.

  - Gradient Boosting & Neural Network have higher MAPE (~78–85%) → may struggle with extremes.

---

## Summary

Exploratory data analysis revealed that hour of the day and temperature are the strongest drivers of bike-sharing demand. Demand peaks during weekday commute hours (6–9 AM and 4–8 PM), while weekend usage is more evenly distributed with higher activity between 12–5 PM. Seasonal analysis showed summer has the highest demand, followed by spring, fall, and winter, and demand increases consistently with rising temperature, with few low-demand observations at high temperatures.


Among all models tested for predicting bike-sharing demand, XGBoost and Random Forest performed best, achieving R² above 0.94, low RMSE (~40), and MAPE around 30–38%. Linear Regression underperformed due to its inability to capture nonlinear relationships. Neural Networks and Gradient Boosting showed decent performance but were less consistent for extreme demand values. Tree-based ensemble methods proved most effective for this real-world regression task


