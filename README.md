# Time Series Analysis
## Microsoft Stock
We made in group a time series analysis using the price of the microsoft stock.
### Microsoft Stock Price
![image](https://github.com/user-attachments/assets/dd561b89-bfeb-4179-8479-e3649239fb4c)
### Cumulative Microsoft Stock Price
![image](https://github.com/user-attachments/assets/583ab1cc-492f-4d68-bcb4-cfcf08f2f2e9)
### Moving Averages Calculation
![image](https://github.com/user-attachments/assets/9862f55c-a05b-4838-a4a9-99033aeed957)
## We made a Decomposition of the time serie
We got the trend, seasonal and trend.
![image](https://github.com/user-attachments/assets/e2196dca-1427-4b40-a1e6-669090abded2)
## Predictive model
We used an LSTM model taking the price of the last 60 days.
### Built Mode
The built model was:
```
model = Sequential()

# Define the input layer with the input shape
model.add(Input(shape=(x_train.shape[1], 1)))

model.add(LSTM(units=50, return_sequences=True))
model.add(Dropout(0.2))

model.add(LSTM(units=50, return_sequences=False))
model.add(Dropout(0.2))

model.add(Dense(units=1))

model.compile(optimizer='adam', loss='mean_squared_error')

history = model.fit(x_train, y_train, epochs=50, batch_size=32)
```
### Performance metrics
The performance metrics were:
```
Train Score: 101.32691566303714 MSE
Train Score: 10.066127143198477 RMAE
Train Score: 6.33542982706524 MAE 

Test Score: 91.87751574828734 MSE
Test Score: 9.5852759870693 RMAE
Test Score: 7.745469511047871 MAE
```
### Comparing the predicted prices and the real prices
![image](https://github.com/user-attachments/assets/0e7a0052-6270-486c-b4fa-dc54dc04d924)
