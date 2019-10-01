# RNN
We have use Recurrent Neural Networks for Building our Stock Prices Prediction of Google Dataset from 2012 to 2017.
We have divided the Dataset into Train and Test given filename such as Google_Stock_Price_Train.csv and Google_Stock_Price_Test.csv respectively.
Google_Stock_Price_Prediction_Train.csv file  as Stock Prices of Google from 1st January 2012 to 30th December 2016 and the stock prices is divided into 4 sections such Open i.e. Stock Prices at the Opening Time, High i.e. Stock Prices at the Highest Day, Low i.e. Stock Prices at the Lowest Day and Close i.e. Stock Prices at the Closest Time.

-------Part 1---------------

Step 1:- We have imported  libraries

Step 2:- We imported the Google_Stock_Price_Train.csv Training dataset using the pandas function and saved it in the dataset_train variable.
From the dataset_train we used index location to take only Open column bcoz we will only predict the Open Stock Price Prediction from the dataset and then we save in the variable called training_set.

Step 3:- We used the feature scaling to transform all the values in the range of 0 and 1 before we train our Neural Network.

Step 4:- We will use the previous 60 stock price values to predict the next values so that our model give some accurate result.

Step 5:- At this step we reshape our input X_train variable into 3-D format before start training the Neural Network. 3-D format gives more information about the stock prices.You can give more values according to your dataset.

--------Part 2--------------

Step 6:- We imported the necessary Keras libraries and packages which will help us build our RNN model

Step 7:- We first initalized our RNN model using Sequential and then save it in the regressor variable. We uses Sequential model bcoz all NN follows a sequential nature i.e. outputs from 1st layer will go as a inputs to the 2nd layer such that it follows a sequential nature.

Step 8:- We add our First LSTM layer with 0.2(20%) dropout i.e. it will ignore 20% of the neurons in the layer for reducing the overfitting.

Step 9,10,11:- Will follow as same as Step 8 but only difference is that there will be no input bcoz due to Sequential nature we only need to provide input only once i.e. at the first layer only.

Step 12:- The ouput layer will have only 1 unit of LSTM layer.

Step 13:- We will compile our RNN using Adam optimizer and our loss is mean_squared_error.The reason we chose mean_squared_error  as our loss function becoz here we are trying to solve Regression Classification i.e. we were trying to predict a continuous outcome (the Google Stock Price).

Step 14:- Here we run our model with epoch=100 and batch_size=32.

------Part 3-----------

Step 15:- Here we are importing the real stock price of 2017 and then save Open columns prices in a variable called real_stock_price.

Step 16:- At this step we will predict the first Stock price of our Test dataset using the previous 60 Stock Prices and so on.The model starts giving prediction about each Stock Price of our Test dataset and then save in a variable called predicted_stock_prices to differentiate it with real_stock_prices.

Step-17: You can Visualised the results of your real_stock_price and your predicted_stock_price using plot function to see the trend in the stock prices of the real stock prices between our predicted stock prices.
