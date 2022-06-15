# mini-Project--Regression-Prediction-of-stock-analysis 
  
 ## Group Members Name 
 * Gokul.R 
 * Hari Shanker.V 
 * Kabileshwaran.V 
 * Mohamed Mustafa.J 
  
 ## About project 
  
 What is Linear Regression? 
  
 Linear Regression is an approach for modelling the 
 relationship between sealar dependent variable y and one or more explanatory 
 variables (or independent variables) denoted X. 
  
 #### Dataset explanation which as chose 
  
 1.The date - "Date" 
  
 2.The opening price of the stock - "Open" 
  
 3.The high price of that day - "High" 
  
 4.The low price of that day - "Low" 
  
 5.The closed price of that day - "Close" 
  
 6.The amount of stocks traded during that day - "Volume" 
  
 7.The stock's closing price that has been amended to include any distributions/corporate actions that occurs before next days open - "Adj[usted] Close" 
  
 ## Performance metrics 
  
 #### 1.Mean Absolute Error (MAE) 
  
 It is the simplest error metric used in regression problems. It is basically the sum of average of the absolute difference between the predicted and actual values. 
 In simple words, with MAE, we can get an idea of how wrong the predictions were. MAE does not indicate the direction of the model i.e. no indication about  
 underperformance or overperformance of the model. 
  
 #### 2.Mean Square Error (MSE) 
  
 MSE is like the MAE, but the only difference is that the it squares the difference of actual and predicted output values before summing them all instead of  
 using the absolute value. 
  
 ### 3.R Squared (R2) 
  
 R Squared metric is generally used for explanatory purpose and provides an indication of the goodness 
 or fit of a set of predicted output values to the actual output values. 
  
 ## Python code Explanation 
  
 import libraries 
  
 import numpy as np 
 import pandas as pd 
  
  
 import matpotlib.pyplot as plt fot visualize the data 
  
 import matplotlib.pyplot as plt 
 %matplotlib inline 
  
  
 import the dataset which has .csv format 
  
 data=pd.read_csv("C:/Users/GOKUL/Downloads/Tesla.csv - Tesla.csv.csv") 
  
  
 If we want to Know the shape of data use data.shape 
  
 data.shape 
  
  
 use data.head() to display the five rows of data 
  
 data.head() 
  
  
 dada.info() is used for know the datatype and memory usage 
  
 data.info() 
  
  
 I dropped Date and adj volume with the help of drop command 
  
 data.drop('Date',axis=1, inplace=True) 
  
  
 data.drop('Adj Close',axis=1,inplace=True) 
  
  
 X denoted as open,low,high 
 y denoted as close 
  
 x=data.iloc[:,0:3].values 
 y=data.iloc[:,-2].values.reshape(-1,1) 
  
  
 from sklearn.model_selection import train_test_split 
  
 from sklearn.model_selection import train_test_split 
  
  
 x_train, x_test, y_train, y_test = train_test_split(x,y,test_size=0.2,random_state=0) 
  
  
 from sklearn.linear_model import LinearRegression 
  
 from sklearn.linear_model import LinearRegression 
  
  
 regr = LinearRegression() 
  
 regr = LinearRegression() 
  
  
 fit the x_train,y_train variable 
  
 regr.fit(x_train,y_train) 
  
  
 predict the x_test 
  
 regr.fit(x_train,y_train) 
  
  
 Create dataframe for actual price and new price 
  
 check = pd.DataFrame(y_test,columns=['Actual price']) 
  
  
 check['Predicted price'] = predict 
  
  
 visualize the data using plt 
  
 plt.figure(figsize=(15,10)) 
 plt.scatter(y_test,predict) 
 plt.xlabel('Actual price') 
 plt.ylabel('Predicted price') 
 plt.show() 
  
  
 performance the metrics   
  
 from sklearn.metrics import mean_squared_error, mean_absolute_error, r2_score 
  
  
 mean_squared_error(y_test,predict) 
 mean_absolute_error(y_test,predict) 
 r2_score(y_test,predict) 
 
