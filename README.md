# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 11-03-2025

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

data=pd.read_csv("C:/Users/SEC/Downloads/dc.csv")

#original data
x=data['Date']
y=data['high_USD']
plt.xlabel('Date')
plt.ylabel('Cost on particular date')
plt.plot(x,y)

#regular differencing
data3=data
data3['diff']=data3['high_USD'].diff()
data3=data3.dropna()
x=data3['Date']
y=data3['diff']
plt.xlabel('Date')
plt.ylabel('Cost on particular date')
plt.plot(x,y)

#seasonal adjustment
data1=data
data1['SeasonalAdjustment'] = data1['high_USD'].rolling(window=12).mean()
data1['SeasonalAdjustment'].dropna()
x=data1['Date']
y=data1["SeasonalAdjustment"]
plt.xlabel('Date')
plt.ylabel('Cost on particular date')
plt.plot(x,y)

#log transformation
data2=data
data2['log']=np.log(data2['diff']).dropna()
data2=data2.dropna()
x=data2['Date']
y=data2['log']
plt.xlabel('Date')
plt.ylabel('Cost on particular date')
plt.plot(x,y)
```

### OUTPUT:


REGULAR DIFFERENCING:
![image](https://github.com/user-attachments/assets/1df80d7f-bae2-4ee5-b70d-297744a0dbc4)


SEASONAL ADJUSTMENT:
![image](https://github.com/user-attachments/assets/1f207341-c463-4d5a-a3ce-2a3ea54e369b)


LOG TRANSFORMATION:
![image](https://github.com/user-attachments/assets/98e2f7e0-68af-4725-af5e-9b28f16a19a9)



### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
