Model used:
We have many features and few data points and we need to predict continuous numeric value, we know it is regression problem. Because of greater number of factors (non-continuous) features and so few training set regression will not provide us good results as I had verified also. We can try using SVM or Random Forest for prediction.

Observations:
1. We have 137 data points in the training set.
2. Opening date, Type of restaurant, City, City Group and 37 demographic features.
3. There is no missing data in training data.
4. The City name in test and train data varies.
5. The demographics features, P1 to P37 can be highly correlated.
6. We need to predict a continuous variable using numeric values, so checking if there are outliers in the target variable would be good.

Feature Engineering:
1. Firstly, while opening the CSV file, using parse_dates = [1] makes the format of Opening date to timestamp format. 
2. Make new columns for month, year, date. 
3. Convert the object type of City Group and Type to integer type.
4. With a particular date subtract the opening date. Since how long a restaurant is running can give a good insight about the annual revenue. 
5. We can try using PCA for the 37 demographic variables.
6. Drop columns that are not to be used.

Conclusion:
1. Linear Regression gave poor score for this question.
2. Random Forest does not tune well to this, also we have memory error associated with it for greater values of estimators.
3. Using PCA does not bring about much change to the score. 
4. SVM gave the best results of all.
