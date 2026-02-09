TSA Passenger Forecasting
Methodology

For this assessment, I built a Random Forest Regressor to predict daily TSA passenger volumes. Random Forest was chosen because it is robust, easy to implement, and handles non-linear relationships, making it well-suited for a time series problem.

The core features included in the model were:

Day_of_Week – numeric representation of the day (0 = Monday, 6 = Sunday)

Is_Weekend – binary indicator for Saturday/Sunday

Month – numeric month (1–12) to capture seasonal trends

Week_of_Year – numeric week (1–52) to capture weekly patterns

Holiday – binary indicator for days within ±2 days of a holiday

Lag_7 – passenger volume from 7 days prior to capture weekly correlation

Rolling_7day_Mean – average passenger volume over the previous 7 days

Data Analysis

The training and test datasets included Date and Volume, along with the engineered features listed above.

Key data handling steps included:

Feature Engineering

Created lag and rolling mean features to capture short-term temporal patterns.

Obtained day, week, month, weekend, and holiday indicators from the Date column.

Train/Validation Split

~90% of the training data was used for training, while 10% was reserved for validation to evaluate model performance.

Feature Alignment and Cleaning

Ensured training and test datasets had identical feature names and structure.

Dropped the Date column before model training since Random Forest requires numeric inputs.

Conclusion

This baseline model demonstrates an effective approach to TSA passenger forecasting using basic features and short-term trends. While more advanced time series models could further improve accuracy, this implementation provides a solid starting point and provides an insightful view on forecasting and machine learning.