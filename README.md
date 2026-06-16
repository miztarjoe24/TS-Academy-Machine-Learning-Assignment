Assignment Summary — Okafor Joachin Topic: Housing Price Prediction using Machine Learning Dataset The assignment used the California Housing dataset (Housing Pinky.csv) with 20,640 records and 10 columns covering longitude, latitude, housing median age, total rooms, total bedrooms, population, households, median income, median house value, and ocean proximity. Steps Carried Out

1. Data Exploration • Loaded and previewed the dataset using df.head() and df.info() • Identified 9 numeric columns and 1 categorical column (ocean proximity) • Checked descriptive statistics for median income and median house value

2. Data Visualization • Plotted histograms for median income and median house value • Filtered out capped 500,000 house values for a cleaner distribution • Created a scatter plot confirming a positive correlation between median income and house value • Plotted the distribution of ocean proximity categories

3. Data Cleaning • Found 207 missing values in total bedrooms • Fixed using median imputation: fillna(median) • Confirmed all missing values resolved • Handled categorical column using one-hot encoding (get dummies)

4. Model Training Model R² Score RMSE Linear Regression 0.65 (train) / 0.63 (test) 70060.52 Random Forest 0.82 (test) 48977.75

5. Model Evaluation • Mean Absolute Error (MAE): 50670.74 • MAE as % of average house price: 24.5% — meaning predictions were off by about 24% on average • Plotted Actual vs Predicted house values showing Random Forest closely tracking real values

Key Finding: Random Forest significantly outperformed Linear Regression, explaining 82% of the variation in house prices with an average prediction error of about 32 on a mean house value of 207.

A few things to keep in mind:

Random Forest (your current results: Train R² 0.98, Test R² 0.82) is a powerful ensemble model that handles non-linear relationships well.

Linear Regression assumes a straight-line relationship between features and target. R² scores may likely be lower if the data has non-linear patterns.

The high gap between Train R² (0.98) and Test R² (0.82) in your Random Forest suggests some overfitting — Linear Regression might actually generalise better in some cases, but with lower overall accuracy.

Note:

Random Forest is clearly the better model for this dataset. It explains 82% of the variance vs Linear Regression's 63%.

Linear Regression's RMSE and MAE are significantly higher, meaning its predictions are further off on average. The fact that Linear Regression's Train and Test R² are close (0.65 vs 0.63) shows it's consistent but weak — it's underfitting the data.

Random Forest handles the non-linear relationships in this data much better.
