# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
``` 
![311642720-1d9eff83-45dd-45f6-8e05-a60443a28c93](https://github.com/user-attachments/assets/54d3ce87-7ba4-46e0-849c-9dbb67447c5b)
```
dt.info()
```
![311643075-9d3a9f34-afc7-4575-9700-4a3a9d06bcf2](https://github.com/user-attachments/assets/fe627d59-e733-428b-bf5b-e2391a902b35)
```
dt.shape
```
![311643348-2e552cda-c340-4c14-81bb-ce0a638212c6](https://github.com/user-attachments/assets/1cb51533-1f4c-49ea-a9ad-dc5c9d7db00f)
```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![311643632-2e3db065-da65-4184-81e9-09b195e0b91d](https://github.com/user-attachments/assets/8694a0a1-c789-49f2-a954-1a877995a8a0)
```
dt.nunique()
```
![311644018-97151d1c-ef1a-44df-885a-15f77cade99a](https://github.com/user-attachments/assets/45d51c47-da87-432a-b084-133b35ec4f1b)

# RESULT

        <<INCLUDE YOUR RESULT HERE>>
