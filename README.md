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
```
```
v=pd.read_csv("/content/titanic_dataset.csv")
v
```
<img width="864" height="304" alt="image" src="https://github.com/user-attachments/assets/d538fafb-38a3-4acc-92cd-d74ad4de0f02" />

```
v.info()
```
<img width="422" height="231" alt="image" src="https://github.com/user-attachments/assets/4c5a0ab0-efca-4480-a3c2-6441651d3af8" />

```
v.shape
```

```
v=pd.read_csv("/content/titanic_dataset.csv")
v.set_index("PassengerId",inplace=True)
print(v.set_index)
```
<img width="795" height="523" alt="image" src="https://github.com/user-attachments/assets/0a02b84f-56b1-4394-b548-a6d50644cc30" />

```
v.describe()
```
<img width="604" height="218" alt="image" src="https://github.com/user-attachments/assets/d94e1cad-217d-4c16-a5ca-b59a468b7c24" />

```
v.nunique()
```
<img width="378" height="315" alt="image" src="https://github.com/user-attachments/assets/7a910bed-ac7d-4592-9062-0d4d969ca337" />

```
v["Survived"].value_counts()
```
<img width="401" height="144" alt="image" src="https://github.com/user-attachments/assets/16bd5811-2ebf-4f57-8d92-f4b8c8be71c1" />

```
per=(v["Survived"].value_counts()/v.shape[0]*100).round(2)
per
```
<img width="449" height="149" alt="image" src="https://github.com/user-attachments/assets/a1873922-649c-49ca-b5ac-618c2e1edada" />

```
sns.countplot(data=v,x="Survived")
```
<img width="749" height="322" alt="image" src="https://github.com/user-attachments/assets/337f2e62-c907-494b-a68d-582df344426f" />

```
v
```
<img width="852" height="315" alt="image" src="https://github.com/user-attachments/assets/7f775a45-4d88-456c-8d89-ba991af5fecf" />
```
v.Pclass.unique()
```
<img width="352" height="53" alt="image" src="https://github.com/user-attachments/assets/962d6818-b761-4281-b5fd-0ab8f63d3d1c" />

```
v.rename(columns={'sex':'Gender'},inplace=True)
v
```
<img width="848" height="333" alt="image" src="https://github.com/user-attachments/assets/a5fe93f3-4c45-4bc0-9922-3782bf37a796" />

```
v=pd.read_csv("/content/titanic_dataset.csv")
sns.catplot(x="Sex",col='Survived',kind="count",data=df,height=5, aspect=.7)
```
<img width="819" height="371" alt="image" src="https://github.com/user-attachments/assets/f0bdd2aa-7684-4702-949b-6ace9a33001a" />

```
sns.catplot(x='Survived',hue='Sex',data=v,kind='count')
```
<img width="614" height="347" alt="image" src="https://github.com/user-attachments/assets/587ad89a-a15c-49fe-b9cc-4fcaa4ea34d8" />

```
v.boxplot(column='Age',by="Survived")
```
<img width="648" height="334" alt="image" src="https://github.com/user-attachments/assets/ca89a9d0-c600-4788-ad1a-94c8ce981d32" />

```
sns.scatterplot(x=v['Age'],y=v["Fare"])
```
<img width="727" height="316" alt="image" src="https://github.com/user-attachments/assets/c924a688-bf9e-46a4-b23e-968b738d532b" />

```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=v)
```
<img width="757" height="326" alt="image" src="https://github.com/user-attachments/assets/5b019e46-2d56-4695-8c07-c52a4afb5c39" />

```
sns.catplot(data=v,col='Survived',x='Sex',hue='Pclass',kind='count')
```
<img width="862" height="354" alt="image" src="https://github.com/user-attachments/assets/726e66ba-387f-44d4-8bb4-c35078960017" />

```
corr = v.corr(numeric_only=True)
sns.heatmap(corr, annot=True, cmap="coolwarm", linewidths=0.5)
```
<img width="736" height="377" alt="image" src="https://github.com/user-attachments/assets/dcb325d3-31c7-4c5a-baa4-e0b60a429593" />

```
sns.pairplot(v)
```
<img width="1375" height="679" alt="image" src="https://github.com/user-attachments/assets/98c95fb3-be4d-4d48-b414-9792d589da2f" />

# RESULT:
   Thus, the Exploratory Data Analysis (EDA) on the Titanic datase is Succesfully Executed
