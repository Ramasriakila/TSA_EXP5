### DEVELOPED BY    : RAMASRI K
### REGISTER NUMBER : 212224040267
### DATE            : 10/03/2026

# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION

### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Step 1: Load the dataset, Convert 'date' column to datetime format, Set it as index
data = pd.read_csv('/content/silver_prices_data.csv', parse_dates=['Date'], index_col='Date') 

# Step 2: Perform seasonal decomposition using the correct column name
decomposition = seasonal_decompose(data['Open'], model='additive', period=12)

# Step 3: Plot the decomposition
plt.figure(figsize=(10, 12))  # Adjust the figure size

# Original Data
plt.subplot(411)
plt.plot(data['Open'], label='Open')
plt.legend(loc='upper left')
plt.title('silver prices')

# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Trend')

# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality')

# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residuals')

plt.tight_layout()
plt.show()
```

### OUTPUT:

Original Time series data:
<img width="810" height="190" alt="image" src="https://github.com/user-attachments/assets/97c91507-b330-43e8-81ed-da6665f4c373" />

TREND PLOT:
<img width="1005" height="200" alt="image" src="https://github.com/user-attachments/assets/6c9e4930-29a4-45ce-ad9d-af3eeb158daf" />

SEASONAL PLOT :
<img width="957" height="187" alt="image" src="https://github.com/user-attachments/assets/814fb60e-5f9d-4ae0-89eb-e110022df8dc" />


RESUIDAL PLOT  :
<img width="1194" height="197" alt="image" src="https://github.com/user-attachments/assets/f8890849-55c9-4419-bed1-1660b4976d92" />



### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
