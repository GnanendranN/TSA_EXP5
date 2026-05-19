# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 19-05-2026


## AIM:
To Illustrates how to perform time series analysis and decomposition.

## ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

## PROGRAM:
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

data = pd.read_csv('/content/drive/MyDrive/Time_Series/tea_vs_coffee_global_final.csv',parse_dates=['year'],index_col='year')
data = data.sort_values('year')
decomposition = seasonal_decompose(data['cups_per_day'], model='additive',period=12)

# decomposition.plot() this plots all four of teh following graphs
# Original Data
plt.figure(figsize=(12,10))

plt.subplot(411)
plt.plot(data['cups_per_day'], label='Number of Cups')
plt.legend(loc='upper left')
plt.title('Number of Cups')
# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')
# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')
# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='black')
plt.legend(loc='upper left')
plt.title('Residual Plot')
plt.tight_layout()
plt.show()
```

## OUTPUT:
<img width="769" height="620" alt="image" src="https://github.com/user-attachments/assets/12f9178b-31d2-4c86-9734-1baaa6c99b06" />

### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
