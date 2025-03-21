# EXNO2DS
### Name: Ezhil Nevedha K
### Reg.no: 212223230055
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

## CODING AND OUTPUT:

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("titanic_dataset.csv")
dt
dt.info()
dt.shape
dt.set_index("PassengerId",inplace=True)
dt.describe()
dt.nunique()
dt["Survived"].value_counts()
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
sns.countplot(data=dt,x="Survived")
dt
dt.Pclass.unique()
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
dt.boxplot(column="Age",by="Survived")
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
sns.jointplot(x="Age",y="Fare",data=dt)
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
corr=dt.corr()
sns.heatmap(corr,annot=True)
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/53789f1b-3925-41a5-b8c5-72ce8d14d466)
![image](https://github.com/user-attachments/assets/4ad7fc05-80ab-40b9-b6cd-469fac6cd37d)
![image](https://github.com/user-attachments/assets/53a8e6f0-6fb8-4f4c-a75b-793c43b84a6d)
![image](https://github.com/user-attachments/assets/ba604b17-5656-4688-a466-e20eaabd4fc6)
![image](https://github.com/user-attachments/assets/0a53b149-e568-4613-875e-634f0b828f90)
![image](https://github.com/user-attachments/assets/c3b3d1e3-c232-4fc9-9d76-376906147a01)
![image](https://github.com/user-attachments/assets/c17a1109-5410-431c-9933-7d5cf2e78820)
![image](https://github.com/user-attachments/assets/e168fab9-5779-49d4-a5da-3e7156a865c0)
![image](https://github.com/user-attachments/assets/ab2468f3-8625-4eae-823e-f0a86ac32b7e)


# RESULT:
Therefore, exploratory data analysis for the given titanic dataset has been successfully done and plots have been done thoroughly.
