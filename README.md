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
df=pd.read_csv("titanic_dataset.csv")
df
```
<img width="1379" height="608" alt="image" src="https://github.com/user-attachments/assets/999b2f91-85aa-4e6c-9b9f-3c4f66716474" />

```
df.info()
```
<img width="1376" height="467" alt="image" src="https://github.com/user-attachments/assets/0e80e9d7-a563-4c05-96c8-2903e214526e" />

```
df.describe()
```
<img width="1422" height="378" alt="image" src="https://github.com/user-attachments/assets/1ca7dc59-538d-4c97-a15e-abe581f8a9e6" />

```
df.dtypes
```
<img width="1423" height="340" alt="image" src="https://github.com/user-attachments/assets/89a2c98b-6853-4247-b38e-dc438c9d5c12" />

```
df.shape
```
<img width="1418" height="92" alt="image" src="https://github.com/user-attachments/assets/ede9c460-cc84-4ecc-b1f3-078beab5b584" />

```
df.value_counts()
```
<img width="1418" height="586" alt="image" src="https://github.com/user-attachments/assets/1b721ff4-4115-45a1-87f8-6e68f9684f4a" />

```
df['Age'].value_counts()
```
<img width="1377" height="321" alt="image" src="https://github.com/user-attachments/assets/0a8b3b95-8735-486f-be45-44a92c70a11d" />

```
df_set.index("PassengerId",inplace=True)
df
```
<img width="1417" height="556" alt="image" src="https://github.com/user-attachments/assets/8dfb5a9a-d49c-49c1-b708-4d13cc40cfa1" />

```
df.nunique
```
<img width="1421" height="313" alt="image" src="https://github.com/user-attachments/assets/6ecc63c7-c52c-4abf-85a4-f30cc886f294" />

```
sns.countplot(data=df,x='Survived')
```
<img width="1397" height="641" alt="image" src="https://github.com/user-attachments/assets/834d29ca-ba7d-43e6-91b2-ccb21a7cc40b" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1415" height="559" alt="image" src="https://github.com/user-attachments/assets/5874bbf4-3bc0-4a4b-8406-8de192f8662e" />

```
sns.catplot(x='Gender',col='Survived',kind="count",data=df,height=5,aspect=1)
```
<img width="1420" height="695" alt="image" src="https://github.com/user-attachments/assets/6cf6a77b-9195-49b4-9aa4-1565d9ee77ec" />

```
df.boxplot(column='Age',by='Survived')
df
```
<img width="1068" height="844" alt="image" src="https://github.com/user-attachments/assets/d73a5aae-c4f7-4b88-b3e8-2539f8b5175b" />

```
sns.scatterplot(x=df['Age'],y=df['Fare'])
```
<img width="1135" height="506" alt="image" src="https://github.com/user-attachments/assets/5473c082-7753-45dc-b336-13460ff05e21" />


```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="1137" height="477" alt="image" src="https://github.com/user-attachments/assets/552cf64d-8593-4f8c-940d-203c3aa1e6b5" />

```
sns.catplot(x='Pclass',y='Age',hue='Gender',col='Survived',kind='box',data=df)
```
<img width="1133" height="517" alt="image" src="https://github.com/user-attachments/assets/f7b58050-eb8f-4739-bb6f-a3074ac1ba99" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="1140" height="510" alt="image" src="https://github.com/user-attachments/assets/34f7f30e-4998-4ba9-9253-b0a225266e05" />

```
corr=df.select_dtypes(include=np.number).corr
sns.heatmap(corr,annot=True)
```
<img width="1262" height="954" alt="image" src="https://github.com/user-attachments/assets/d3b97cfe-e29e-4390-9b1d-fbc0a63c87be" />



# RESULT
Exploratory Data Analysis on the given data set is successful
