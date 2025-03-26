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

DEVELOPED BY: SUDHARSAN S

REGISTRATION NO: 212224040335
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns  


df = pd.read_csv("titanic_dataset.csv")

df
```

![image](https://github.com/user-attachments/assets/e9140f2c-9b83-4887-b152-0ffbad64df98)

```
df.info()
```

![image](https://github.com/user-attachments/assets/49e587f5-ea3b-4974-a88b-b45819ddfd49)

```
df.shape
```

![image](https://github.com/user-attachments/assets/04f4fe19-ef9f-45cf-911b-94470790d9fd)

```
df.describe()
```

![image](https://github.com/user-attachments/assets/c094d27c-a04c-4ec9-8609-4b7c72563c91)


```
df.set_index("PassengerId", inplace=True)
df.describe()
```

![image](https://github.com/user-attachments/assets/622f218c-3ccd-4ee6-a32a-b3bc9a2a054c)


```
df.nunique()
```

![image](https://github.com/user-attachments/assets/12790b36-d0c5-4b33-a3d7-6f3ec201f54b)


```
df["Survived"].value_counts()
per = (df["Survived"].value_counts() / df.shape[0] * 100).round(2)
per
```

![image](https://github.com/user-attachments/assets/f7153c25-4abc-4305-acea-85b5dfccf1de)


```
df.Pclass.unique()
```


![image](https://github.com/user-attachments/assets/d2ab6daf-1939-4ef0-9fe1-c1ce275e1794)


```
df.rename(columns={'Sex': 'Gender'}, inplace=True)
sns.catplot(x="Gender", col="Survived", kind="count", data=df, height=5, aspect=.7)
```

![image](https://github.com/user-attachments/assets/7c69b5f0-4b85-430d-8417-eebbb4120298)

```
sns.catplot(x="Survived", hue="Gender", data=df, kind="count")
```
![image](https://github.com/user-attachments/assets/ed3fdf12-4b39-4b27-afff-a5dbc87dcaa7)

```
df.boxplot(column="Age", by="Survived")
```

![image](https://github.com/user-attachments/assets/d5501d0c-4daf-4dbc-b06c-ae7c2a6af583)

```
sns.scatterplot(x=df["Age"], y=df["Fare"])
```

![image](https://github.com/user-attachments/assets/79b81c38-19cd-4f34-9ab1-3aad6a53edc6)

```
sns.jointplot(x="Age", y="Fare", data=df)
```

![image](https://github.com/user-attachments/assets/e982b28f-5145-4695-a3e0-8a68f4c8856b)

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

![image](https://github.com/user-attachments/assets/7df4b92d-4c0b-43aa-80c4-c4b25dabdeb1)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![image](https://github.com/user-attachments/assets/9010cad5-a77e-40f9-8641-99dd156ea328)

```
corr = df.select_dtypes(include=['number']).corr()
sns.heatmap(corr, annot=True)
```

![image](https://github.com/user-attachments/assets/c4655d6e-7df6-4111-a02c-80b7c2bfbba5)

```
sns.pairplot(df)
```

![image](https://github.com/user-attachments/assets/dea0d6ee-54da-4b24-8e9a-35721ee69898)





# RESULT
We have performed Exploratory Data Analysis on the given data set successfully
