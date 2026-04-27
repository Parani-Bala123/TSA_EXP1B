# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 27/04/26

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

# Load dataset
df = pd.read_csv("airline_passengers_dataset.csv")

# Convert Date column
df["Date"] = pd.to_datetime(df["Date"])

# Set Date as index
df.set_index("Date", inplace=True)

# Original Data Plot
plt.figure(figsize=(10,5))
plt.plot(df["Passengers"], label="Original Data")
plt.title("Original Time Series Data")
plt.legend()
plt.show()

# -------------------------------
# 1. Regular Differencing
# -------------------------------
df["Diff"] = df["Passengers"].diff()

plt.figure(figsize=(10,5))
plt.plot(df["Diff"], label="Regular Differencing")
plt.title("After Regular Differencing")
plt.legend()
plt.show()

# -------------------------------
# 2. Seasonal Adjustment
# -------------------------------
df["Seasonal_Diff"] = df["Passengers"].diff(12)

plt.figure(figsize=(10,5))
plt.plot(df["Seasonal_Diff"], label="Seasonal Differencing (Lag 12)")
plt.title("After Seasonal Adjustment")
plt.legend()
plt.show()

# -------------------------------
# 3. Log Transformation
# -------------------------------
df["Log"] = np.log(df["Passengers"])

plt.figure(figsize=(10,5))
plt.plot(df["Log"], label="Log Transformation")
plt.title("After Log Transformation")
plt.legend()
plt.show()

# Display results
print(df.head())
```

### OUTPUT:

<img width="1171" height="572" alt="image" src="https://github.com/user-attachments/assets/7623a32f-56fa-4d7e-bd45-efa86fa9e53d" />

REGULAR DIFFERENCING:
<img width="1132" height="590" alt="image" src="https://github.com/user-attachments/assets/0aaa712f-d570-4b7b-b808-53f7f01f798f" />


SEASONAL ADJUSTMENT:

<img width="1149" height="589" alt="image" src="https://github.com/user-attachments/assets/2abc7b93-b1f4-4906-ae64-e2c4799782ee" />

LOG TRANSFORMATION:

<img width="1160" height="563" alt="image" src="https://github.com/user-attachments/assets/4c0e5867-3a88-4d62-8b55-918cfce64dfa" />


### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
