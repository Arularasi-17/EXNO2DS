# NAME: ARULARASI U
# REG: 212223100002
# DEP: CSE[CYBER SECURITY]
# EX 2
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
dt=pd.read_csv("titanic_dataset.csv")
dt
```
![image](https://github.com/user-attachments/assets/14a4d423-616e-4319-bb3d-45f59fdc00a9)
```
dt.info()
```
![image](https://github.com/user-attachments/assets/5f7fdb2c-87ac-41f7-b24c-e9ff292e54f0)

```
dt.shape
```
![image](https://github.com/user-attachments/assets/ae1bd2ac-9652-4aa9-ab1d-9185372e47a1)

```
#dt.set_index[("PassengerId",inplace=True)]
dt
```
![image](https://github.com/user-attachments/assets/82755722-f31f-4de1-86c7-d3e09ab28527)

```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/31336ddd-e91a-4e85-bcf4-313f9b02fe93)

```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/1bdd8fb4-d83c-48e4-a592-9828262cd0d2)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/c7475a63-0b5a-4b56-8bc0-2ba4968d7739)

```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/10ee6987-6c0d-498b-89f6-6b10eec67ab3)

```
dt.Pclass.unique()#to fine unique values in passenger class
```
![image](https://github.com/user-attachments/assets/192e5cb3-9c49-479d-8e22-d6334aebdcb2)

```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/user-attachments/assets/759b70e8-0bd3-4221-a645-ca2aa0eb26ab)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=0.7)
```
![image](https://github.com/user-attachments/assets/f3a0bdb6-4d0a-4bf0-8eda-6ab3ad2b77a0)

```
sns.catplot(x='Survived',hue='Gender',data=dt,kind='count')
```
![image](https://github.com/user-attachments/assets/caf31a39-6cee-417b-a59d-b73e9bc12b90)

```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/ef424953-4c8f-493b-991d-55641f80d581)

```
sns.scatterplot(x=dt['Age'],y=dt['Fare'])
```
![image](https://github.com/user-attachments/assets/e742e6b4-6c25-41c0-ba44-e91e2deec6b2)

```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![Screenshot 2024-09-03 181646](https://github.com/user-attachments/assets/68e2a8f0-3b75-4696-9fe3-a2fe3bc4cc6f)

```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/c758fb79-8a75-46e4-9575-de5e104b4cbd)

```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/7fec69ac-9f20-482f-af93-4408809d8557)

```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/f29cce45-4bee-4d89-a1d8-2c4055caf0ba)

# RESULT
      Exploratory Data Analysis on the given data set had performed successfully.
