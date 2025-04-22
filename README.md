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
REG NO: 212224040239
NAME  : PRANAV BHARGAV M
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset (2).csv")        
dt
```
![image](https://github.com/user-attachments/assets/b0785025-b1be-497b-bdd0-9166deb02919)
```
dt.info()
```
![image](https://github.com/user-attachments/assets/19b2785f-8305-4fe7-a16b-1aa743620251)
```
dt.shape
```
![image](https://github.com/user-attachments/assets/ddccf450-1882-48ba-a13c-8974867ad934)
```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![image](https://github.com/user-attachments/assets/7f854990-dfec-49df-a03d-c6e48b3d2592)
```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/7389d0ba-96b3-460f-a79b-d798559ef9a9)
```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/47ab152f-63f6-44c8-97ce-b5905764c14e)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/e6617829-44fd-4f55-abc3-61fdbe9c3ead)
```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/68b309cb-aa38-4b63-86de-17c4e5b1823c)
```
dt.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/d780bfc3-9d77-4399-bedb-820f331af4ff)
```
dt.rename(columns={"Sex":"Gender"},inplace=True)
dt
```
![image](https://github.com/user-attachments/assets/caf0e0d5-b445-4c09-8a95-46ac88f040bd)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/2b7894a7-d791-4626-8aed-ebaddc8a6a81)
```
sns.catplot(x="Survived",hue="Gender",data=dt,kind="count")
```
![image](https://github.com/user-attachments/assets/9b8d34f2-37bf-4c4c-9d8f-2b3f1f7346ce)
```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/11182a5b-4abc-47c1-9175-11ce1e13886e)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/user-attachments/assets/c43d5094-da52-4baa-8da9-348583f56fcd)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/user-attachments/assets/2acb22b0-ca11-428d-9234-e9a5f0255974)
```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```
![image](https://github.com/user-attachments/assets/0828890e-1229-40da-94bc-d0a05e67a337)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/2a90e37b-7cbd-4e90-8fe9-896da5996a30)
```
numeric_dt = dt.select_dtypes(include=['int64','float64'])
corr=numeric_dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/1f5b6e77-2561-486b-af3d-df4e29325753)
```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/cffcd64e-ade0-4a99-9f51-7c35d1be4f6f)
![image](https://github.com/user-attachments/assets/4c30e4d8-0206-41da-9639-2d70e290220f)

# RESULT
```
Exploratory Data Analysis on the given data set was performed successfully.
```
