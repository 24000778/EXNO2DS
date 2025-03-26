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
        <<INCLUDE YOUR CODING AND OUTPUT SCREENSHOTS>>
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![image](https://github.com/user-attachments/assets/67192cb4-d87a-4e58-a6e6-d9546cfab66a)
```
dt.info()
```
![image](https://github.com/user-attachments/assets/fa89e61e-1fe0-4bce-bb03-5a6a650102c0)
```
dt.shape
```
![image](https://github.com/user-attachments/assets/a44a57ea-1915-4030-866b-2ceb1fd214f5)
```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![image](https://github.com/user-attachments/assets/ab070be7-3d37-4c54-a9ad-4e6e858fadf3)
```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/eb179d3c-fae9-435d-89a4-b8d6ba60a00f)
```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/59feccd9-697f-48fe-bee0-104b2f23c771)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/c41cfa88-c080-4952-9b2b-9bbcac73315c)
```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/f82ed1f7-bb05-46ee-8cbd-02dacdc23cf5)
```
dt
```
![image](https://github.com/user-attachments/assets/512180bf-2146-41b4-ac9e-a9221718693e)
```
dt.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/527e0eeb-1846-464b-bda8-39c0c7a4c8e3)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/user-attachments/assets/23335e18-621a-444d-8e35-d645f1a0aede)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/0cc0ff83-67a2-4b81-895d-8855aae1f38e)
```
sns.catplot(x='Survived',hue="Gender",data=dt,kind='count')
```
![image](https://github.com/user-attachments/assets/215e067f-5359-4135-9eee-b2789d13a4f2)
```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/c087907c-61ea-4fe1-871d-78d2a7386e0c)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/user-attachments/assets/4bbf7617-2f24-4742-b4cb-adf8fe18aa4f)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/user-attachments/assets/231299d0-54ee-4c63-ac3c-4212b6f70501)
```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)
```
![image](https://github.com/user-attachments/assets/ea347369-84d3-4299-9f61-dd0f986fa3c1)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/9c66a5a1-d63a-4d9e-aafe-142cec0ded97)
```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/fb6cd1c6-356a-42ce-9d48-a0a6fb094b49)
```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/58a91c33-8743-43a3-8bdc-0357c484df7a)




















# RESULT
        <<INCLUDE YOUR RESULT HERE>>
        ```
        Thus, the Exploratory Data Analysis on the given data set was performed successfully.
