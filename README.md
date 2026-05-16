# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 11-05-2026


## AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

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

data = pd.read_csv('/content/nasa_exoplanet_intelligence.csv',parse_dates=['disc_year'],index_col='disc_year')
data = data.sort_values('disc_year')
decomposition = seasonal_decompose(data['n_planets'], model='additive',period=12)
plt.figure(figsize=(11,7))

# decomposition.plot() this plots all four of teh following graphs
# Original Data
plt.subplot(411)
plt.plot(data['n_planets'], label='Number of Planets')
plt.legend(loc='upper left')
plt.title('Number of Planets')
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
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')
plt.tight_layout()
plt.show()
```

## OUTPUT:
<img width="1079" height="682" alt="image" src="https://github.com/user-attachments/assets/62d5ec61-7b00-4820-aeb4-3f9c217a33c4" />

### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
