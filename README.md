# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 25/02/2026


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

# Load the dataset
data = pd.read_csv('/content/bike_sales_india.csv')

# Convert Year column to datetime and set as index
data['Year'] = pd.to_datetime(data['Year'], format='%Y')
data.set_index('Year', inplace=True)

data.head()

# Perform decomposition on Resale Price
decomposition = seasonal_decompose(data['Resale Price (INR)'], model='additive', period=2)

# Plot the decomposition
plt.figure(figsize=(10, 12))

# Original Data
plt.subplot(411)
plt.plot(data['Resale Price (INR)'], label='Resale Price')
plt.legend(loc='upper left')
plt.title('Bike Resale Price')

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

### OUTPUT:
## FIRST FIVE ROWS:
<img width="767" height="270" alt="Screenshot 2026-03-14 110340" src="https://github.com/user-attachments/assets/a81e6595-f60b-4568-9ef8-db6f5ff1edf8" />



## PLOTTING THE DATA:
<img width="763" height="232" alt="Screenshot 2026-03-14 110426" src="https://github.com/user-attachments/assets/7e6cb99e-21f9-4834-a23b-a4525f0cd1cc" />



## SEASONAL PLOT REPRESENTATION :

<img width="762" height="230" alt="Screenshot 2026-03-14 110439" src="https://github.com/user-attachments/assets/6600d006-8884-4332-beea-098a128c5469" />


## TREND PLOT REPRESENTATION :
<img width="775" height="233" alt="Screenshot 2026-03-14 110432" src="https://github.com/user-attachments/assets/9f5e2454-406f-454b-983b-7009dce245e1" />

 
## OVERAL REPRESENTATION:

<img width="772" height="223" alt="Screenshot 2026-03-14 110446" src="https://github.com/user-attachments/assets/2f11da1c-04fa-46a4-b773-827832f4af0a" />


### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
