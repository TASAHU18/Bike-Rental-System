Bike Rental System

Business Problem:  To build a Machine Learning model to predict the hourly count of bikes rented in a city bikeshare system. 

Data: 
The data provided contains the hourly bike rented count for a city for two years 2011 & 2012. The data consists of 9 categorical variables (date, season, year, month, hour, holiday, weekday, working day, weather) and 7 numerical variables (temp, atemp, humidity, windspeed, casual, registered, count). 

Data Preprocessing Steps: 
• Null Value Check: No Null values were found in any of the features. 
• Outlier Analysis: Data points that are beyond 3 Standard Deviations away from mean were considered as outliers and removed 
• Feature Selection: Checked for collinearity between the dependent variables. Features temp and atemp were found to be collinear So atemp was dropped. 
• Feature Engineering: Categorical features - Season, Year, Month and Hour were converted into dummy variables by One Hot Vector Encoding Method. 
• Feature Scaling: Continuous variables - Count, Temp, Humidity were standardized using Standard Scaler for improving model performance. 
• Test & Validation Set: The dataset was split into Train, Validation and Test sets. The Test set includes the last 30 days of the data while the rest of the data was split into Train and Validation data. 
Instead of splitting it randomly this method retains the seasonality and trend of data in both the Train and Test sets. 

Data Analysis Insights: 
• The plot of variable Count over the period of two years reveals that there is an increasing trend in bike share pattern implying higher demand in 2012 compared to 2011. As well as there is a seasonality pattern implying higher demand in some seasons. 
• During Weekdays, people are mostly using the bikes to go and come from work/school whereas on Weekends people are mostly using bikes during the afternoon time 
• Across different Seasons the demand for bikes is highest in Fall season, followed by Summer and Winter. In Spring season, the demand for bikes is the least. 
• Across different weather situations people are using the bikes mostly during the clear weather and very less when there is snow or rain. 

Data Modeling: 
From the data, we have the dependent variables and the independent variable, so we can classify our problem as a Supervised Machine Learning problem and the task is to predict the count, that is a continuous variable, so we will be using Regression Techniques only. 

The models I have trained the data were Stochastic Gradient Descent, Lasso, Ridge, Support Vector Regressor and Random Forest Regressor. The performance of these models is measured using three metrics Mean Absolute Error (MAE), Root Mean Square Error (RMSE) and R Square. 
Random Forest Regressor performed better than others across all the three metrics. This is mainly due to fact that our data has a lot of categorical features Tree Based algorithms generally perform good on categorical data. The performance metrics of Random Forest model were as follows: 
Mean Absolute Error | Root Mean Squared Error | R² score 
0.44 		            | 0.64 		                | 0.69
