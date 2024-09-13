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
```
dt["Survived"].value_counts()
```
![311644271-a547fdac-8e3f-43f2-9932-fa2c2a265134](https://github.com/user-attachments/assets/74000cf1-bcd9-448b-bf17-ba440ca8c7b8)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![311644581-8eced09f-2a18-4e3f-bd13-243701048fc5](https://github.com/user-attachments/assets/3422f459-b11b-4bec-9777-2602cbca8774)
```
sns.countplot(data=dt,x="Survived")
```
![311644875-34adfa76-c868-440d-b0c6-d97ebe93e351](https://github.com/user-attachments/assets/ec265f32-44fd-4f74-a88d-b85eddf39590)
```
dt
```
![311645161-ff6a85fa-f2ce-4769-93c8-b596fcaaad17](https://github.com/user-attachments/assets/43465b98-ce6d-430e-94bb-d92e9610996d)
```
dt.Pclass.unique()
```
![311645596-58fef3e0-6e22-489a-a2b9-85fc559daffa](https://github.com/user-attachments/assets/e3cf38a7-0ca9-405f-966a-988252231f82)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![311645992-8bb0fc68-5f7a-4005-80c6-b4706fd4cd3b](https://github.com/user-attachments/assets/20f5e7d3-b963-477d-a452-978a529e4a48)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![311646333-9af5b685-0281-43c4-bcda-dff99e437f3c](https://github.com/user-attachments/assets/ad919f60-acd2-4eb3-8e06-881eb3a7bc01)
```
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
```
![311646701-8555cc95-07c9-4436-a2a7-f2eb918d171d](https://github.com/user-attachments/assets/da5f29c2-2910-4cc4-a5dc-94a3182d3096)
```
dt.boxplot(column="Age",by="Survived")
```
![311647054-472e3846-e3dc-4391-813e-cd7d2eaccaf9](https://github.com/user-attachments/assets/7e66471f-ec1e-4f16-a833-940ab27cee96)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![311647318-2d4244b8-65d1-46f3-a848-c4e5c57928f5](https://github.com/user-attachments/assets/f66e3636-3dfd-438d-9197-23d152fd545d)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![311647604-25fae9cf-16d8-46b0-b427-b9bd7b47f027](https://github.com/user-attachments/assets/7a49da8c-9a88-4904-a1a6-2735f5b84be6)
```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```
![311647871-839a046e-ac0d-483c-b09f-544f1608dde0](https://github.com/user-attachments/assets/51d1151b-956b-484a-9bb8-786a25873622)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![311648048-61b5359f-119c-41a3-bbc9-a301c5cc5196](https://github.com/user-attachments/assets/687508b4-e7a8-4d06-826d-8d47ebad3b67)
```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![311648301-1a358d7b-b6ed-45b6-8266-18c249421323](https://github.com/user-attachments/assets/77aab26d-4801-404a-a750-0b0ade248508)
```
sns.pairplot(dt)
```
![311648533-a32237e1-689e-43d6-8765-d5deed872071](https://github.com/user-attachments/assets/abbecba5-113b-4095-9001-aec1c5a0710d)

# RESULT
Thus, the Exploratory Data Analysis on the given data set was performed successfully.
     
