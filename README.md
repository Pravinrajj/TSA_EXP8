# Ex.No: 08     MOVINTG AVERAGE MODEL AND EXPONENTIAL SMOOTHING
### Date: 

### DEVELOPED BY: PRAVINRAJJ G.K
### REGISTER NO: 212222240080
### AIM:
To implement Moving Average Model and Exponential smoothing Using Python.
### ALGORITHM:
1. Import necessary libraries
2. Read the XAUUSD time series data from a CSV file,Display the shape and the first 20 rows of
the dataset
3. Set the figure size for plots
4. Suppress warnings
5. Plot the first 50 values of the 'Value' column
6. Perform rolling average transformation with a window size of 5
7. Display the first 10 values of the rolling mean
8. Perform rolling average transformation with a window size of 10
9. Create a new figure for plotting,Plot the original data and fitted value
10. Show the plot
11. Also perform exponential smoothing and plot the graph
### PROGRAM:
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import warnings

data = pd.read_csv('XAUUSD_2010-2023.csv')

print("Dataset Shape:", data.shape)
print("First 20 Rows of the Dataset:\n", data.head(20))

plt.figure(figsize=(12, 6))

warnings.filterwarnings('ignore')

plt.plot(data['close'][:50], label='Original Data')
plt.title('First 50 Values of the Time Series (Close Prices)')
plt.xlabel('Time')
plt.ylabel('Close Price')
plt.legend()
plt.show()

rolling_mean_5 = data['close'].rolling(window=5).mean()

print("First 10 Values of Rolling Mean (Window Size 5):\n", rolling_mean_5.head(10))

rolling_mean_10 = data['close'].rolling(window=10).mean()

plt.figure(figsize=(12, 6))

plt.plot(data['close'], label='Original Data', alpha=0.6)
plt.plot(rolling_mean_5, label='Rolling Mean (Window Size 5)', color='red')
plt.plot(rolling_mean_10, label='Rolling Mean (Window Size 10)', color='green')
plt.title('Original Data and Rolling Mean')
plt.xlabel('Time')
plt.ylabel('Close Price')
plt.legend()
plt.show()

exp_smoothing = data['close'].ewm(alpha=alpha).mean()

plt.figure(figsize=(12, 6))
plt.plot(data['close'], label='Original Data', alpha=0.6)
plt.plot(exp_smoothing, label='Exponential Smoothing', color='purple')
plt.title('Original Data and Exponential Smoothing')
plt.xlabel('Time')
plt.ylabel('Close Price')
plt.legend()
plt.show()

```
### OUTPUT:
Moving Average
![image](https://github.com/user-attachments/assets/8ee2a2c1-9378-4b9b-92c3-3b98e4e88712)

Plot Transform Dataset
![image](https://github.com/user-attachments/assets/a2fc8b2b-c112-448e-9f55-cf40c8d93383)

Exponential Smoothing
![image](https://github.com/user-attachments/assets/7c29bfba-497c-4aae-8d1e-5ab7d83a8e0e)

### RESULT:
Thus we have successfully implemented the Moving Average Model and Exponential smoothing using python.
