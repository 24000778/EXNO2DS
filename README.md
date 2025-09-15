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
df=pd.read_csv("/content/titanic_dataset.csv")
df

```

<img width="1334" height="602" alt="Screenshot 2025-09-15 215843" src="https://github.com/user-attachments/assets/a3b903e3-47a2-4cca-ab89-0a18de0ab871" />

```
df.info()

```
<img width="1374" height="422" alt="Screenshot 2025-09-15 215934" src="https://github.com/user-attachments/assets/e775d0c8-d2a0-41d0-912a-054e547e93b3" />

```
df.dtypes

```

<img width="916" height="570" alt="Screenshot 2025-09-15 220033" src="https://github.com/user-attachments/assets/5d80290b-741c-4208-8e8a-db8f7ab91264" />

```
df.describe()

```
<img width="912" height="372" alt="Screenshot 2025-09-15 220227" src="https://github.com/user-attachments/assets/08fc2bfa-1c32-4bee-8466-85e294a36741" />

```
df.shape

```
<img width="818" height="33" alt="Screenshot 2025-09-15 220335" src="https://github.com/user-attachments/assets/044154a6-e622-4168-94a7-1b2a07d191c5" />

```
df.value_counts()

```
<img width="1354" height="712" alt="Screenshot 2025-09-15 220729" src="https://github.com/user-attachments/assets/b2441886-92ce-4ca9-8b22-8480476a14de" />

```
df['Age'].value_counts()

```
<img width="1355" height="591" alt="Screenshot 2025-09-15 220852" src="https://github.com/user-attachments/assets/f25e8763-6c08-494d-a39c-f007c87c7a2c" />

```
df.set_index("PassengerId",inplace=True)
df

```
<img width="1362" height="659" alt="Screenshot 2025-09-15 221000" src="https://github.com/user-attachments/assets/980e6313-c38e-40c2-b350-8b53c48b022b" />

```
df.nunique()

```

<img width="1273" height="540" alt="Screenshot 2025-09-15 221053" src="https://github.com/user-attachments/assets/98d82fa7-4970-4fa6-948c-2b2b221cbf84" />

```
sns.countplot(data=df,x="Survived")

```

<img width="1010" height="571" alt="Screenshot 2025-09-15 221618" src="https://github.com/user-attachments/assets/3377e290-f9ac-404f-a0f3-02bf325df964" />

```

df.Pclass.unique()

```

<img width="1259" height="46" alt="Screenshot 2025-09-15 221711" src="https://github.com/user-attachments/assets/c24e143e-5a20-46af-9166-9962323108ed" />

```

df.rename(columns={'Sex':'Gender'},inplace=True)
df

```
<img width="1412" height="667" alt="Screenshot 2025-09-15 221801" src="https://github.com/user-attachments/assets/ee6804a7-ca0e-46fc-bace-2418ceec1fb4" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=0.7)

```
<img width="1163" height="645" alt="Screenshot 2025-09-15 221846" src="https://github.com/user-attachments/assets/e1f51492-8c92-481a-ae08-0d75fb872e7d" />

```
df.boxplot(column="Age",by="Survived")

```
<img width="1201" height="596" alt="Screenshot 2025-09-15 221924" src="https://github.com/user-attachments/assets/d5e0f817-4ad6-46d3-a0b6-d36be845dfdf" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])

```
<img width="1405" height="561" alt="image" src="https://github.com/user-attachments/assets/43d409db-8563-4a5e-9a6d-863e04f704aa" />

```

#fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(x="Pclass",y="Age",hue="Gender",data=df)

```
<img width="1364" height="573" alt="Screenshot 2025-09-15 222053" src="https://github.com/user-attachments/assets/adac5a78-d326-4ad8-86fe-c6aee2f1d29b" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")

```
<img width="1349" height="651" alt="Screenshot 2025-09-15 222207" src="https://github.com/user-attachments/assets/27724a0c-a173-47ef-8f2c-0cbefa9ce84b" />


```

numeric_df = df.select_dtypes(include=np.number)
corr = numeric_df.corr()
sns.heatmap(corr, annot=True)

```

<img width="1179" height="543" alt="Screenshot 2025-09-15 222301" src="https://github.com/user-attachments/assets/45070bce-b27d-431e-995c-fdf951f52b11" />



# RESULT
        
Thus, the Exploratory Data Analysis on the given data set was performed successfully.
