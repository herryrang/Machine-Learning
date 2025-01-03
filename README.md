# README
This Capstone Project was conducted to make price prediction with machine learning model on Saudi Arabia Used Car which is a dataset containing 
Used Car Sales Data in Saudi Arabia.

# What I Did In Machine Learning Model?
Used Car Sales Data in Saudi Arabia 

The thing that I do in the machine learning is to found some price prediction that I can see from the dataset and transform it into graph or table so it can be easily to understand.

# Problems
- Understand the factors that influence used car prices in Saudi Arabia.
- Build a prediction model to describe car prices based on their attributes.
- Provide recommendations to the Company to help determine better pricing impacts.


# Objective 
The Objective of the Analysis that I do in this project are to provide recommendations for car sales in Saudi Arabia. 

# Step by Step for make a model

1. Data Understanding

In this process, first I need to understand the data contents. So, I write the code to see the data types, missing values, N unique, and the example of the unique. Below are the example of the table

![image](https://github.com/user-attachments/assets/8bc56c89-51c2-4708-abb7-0f5fa6851520)


2. Data Preprocessing

In this process, I make data preprocessing that the first thing to do is by checking the outliers so we can see the extreme amount and we can consider to remove it to make the results more acceptable.  

![image](https://github.com/user-attachments/assets/19e955a2-879e-47bb-90f3-018aaa83c4f9)

We can see in above that all the data have outliers. But we consider to just remove Price and Year. In Price we make the gap price between 3000 and 250000 SAR because we assume that the most of the buyers only buy the price of that car in that amount only. 

And the year we make that only after 1978 production code because its already segmented if the car is already below 1978.

And we just leave "mileage" and "engine_size" just as it is because engine_size doesnt matter and also mileage. 

![image](https://github.com/user-attachments/assets/72a82ae9-de55-4e55-8fa4-fb5505f3e29c)

And then we drop the duplicates data, and also the unknown origin because it will make confuse later. And also we drop "negotiable" column because we think that we dont need it as the factor
of price prediction.

![image](https://github.com/user-attachments/assets/a2cc2c27-9cde-4658-a529-0ec307c57e05)

And below are the correlation matrix, in correlation matrix we see that the factors that influenced the price is engine_size and year which is the correlation coefficient respectively at 0.38 and 0.31

![image](https://github.com/user-attachments/assets/d8887e4d-2238-4313-bbb2-93f80a778c1f)


3. Modeling

In this process, we change the categorical feature to numerical feature so we can train and test the data. And then in column "Gear_Type", "Origin", "Options" we make it as One Hot Encoder, and for "Type","Region","Make" we make it as Binary Encoder. 

After that we Split the data, and then for the Train:Test we make it 70:30 to make it proportional.

![image](https://github.com/user-attachments/assets/632b253b-f4fe-41d1-bb39-2db8ef7dc3c3)



After that we benchmarking the model, and then we get the best model which is RandomForestRegressor and XGBoost the best 2 models.

![image](https://github.com/user-attachments/assets/375f6e78-da61-48c3-a45c-843c8273c9cc)



After we compare, we get that XGB is the best model so we will do hyperparameter tuning with XGB

![image](https://github.com/user-attachments/assets/a74ff184-517e-49e8-b7eb-e2022974ce59)

  

After we do hyperparameter tuning, we can see that after the tuning the model less worsen

![image](https://github.com/user-attachments/assets/156fddbc-86a3-4f39-b00a-4086af0a97f2)

Below are the scatter plot of Actual vs. Prediction Price, we can see from the car price in range 0-100000 SAR, we can see the actual and prediction are almost the same, but when we see above that price, we can see that the actual and prediction are different. 

![image](https://github.com/user-attachments/assets/1945668d-8cf3-452b-8772-5d40ad224e56)

Below are the feature importances, we can see the 2 most feature that is important are "Year" and "Engine_Size"

![image](https://github.com/user-attachments/assets/e65146f3-561f-490d-9a7a-aafa22f393d0)


Below are feature importances that we see on the table from the highest to the lowest.

![image](https://github.com/user-attachments/assets/e849c7d4-7483-4e15-84d3-75ca05253a8f)


# Conclusions 

Based on the modeling that has been carried out, the 'Year', 'Engine Size' and 'Make' features are the features that have the most influence on 'Price'.

Maybe because the buyer wants the car to be relatively young, the optimal engine size and the particular car brand are things that influence the price of the car.
The evaluation metrics used in the model are RMSE, MAE & MAPE values. If we look at the MAPE value produced by the model after hyperparameter tuning, which is ~25%, where this figure is still sufficient and reasonable, we can conclude that if later the model we created is used to estimate car prices. 
However, it is also possible that the predictions are further off because the bias produced by the model is still quite high when seen from the visualization between actual and predicted prices. The bias produced by this model is due to the limited features in the dataset.

This model can of course still be imported to produce better predictions. However, we can carry out A/B testing on the models that have been created in this project to determine the level of effectiveness of using the model. Later, from the results of A/B testing, we can get other insights regarding things that can and should be improved in the model.

# Recommendations

In this research we have been able to build a model to predict the price of used cars with a price range of 30000 to 250000 SAR. This model can be used as supporting information  in determining selling and buying prices for companies and individuals who will carry out used car buying and selling transactions.
Based on the model results, it shows that the features that have the most significant influence are 'Year', 'Engine Size' and 'Make'. The performance of the regression model in this model is measured using RMSE, MAE, and MAPE. The final value after hyperparameter tuning for each evaluation metric is 20263.818831   12956.295689   0.257784
The RMSE value means that when the model is used to predict the price of a used car, the estimated average price will differ by approximately 20263 Riyals from the actual price. However, the resulting predictions can go further than they should due to bias in the model.

Further research can be carried out by increasing the price range, because there are also those interested in expensive used cars so that we can get the latest insight regarding price predictions and the buyer groups can be more varied.


























