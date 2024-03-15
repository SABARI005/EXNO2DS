# Data Analysis Using Python
## AIM:
To perform Exploratory Data Analysis on the given data set.
      
## EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
## ALGORITHM:
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
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```

![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/3a364212-1500-4f79-b1ca-1e20dd6548e2)

```
dt.info()
```

![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/58de8378-2183-4133-9d26-841837dc6d4e)

```
dt.shape
```

![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/b04e276e-6377-41fa-a9d7-775af6f936b9)

```
dt.set_index("PassengerId",inplace=True)

dt.describe()
```
![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/ad3eafa2-5bf1-48fb-9245-523c3077e676)


```
dt.nunique()
```

![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/b4dc15f2-4e53-4582-bbee-ce493338259a)


```
dt["Survived"].value_counts()
```

![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/77e68e03-88e7-4b01-8377-c3cc48583f8a)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/4e73f2ed-7bd4-4acf-8786-ff0379cdc583)

```
sns.countplot(data=dt,x="Survived")
```

![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/95fc8f80-45ad-4bd5-ba84-2fa7d9fbedd4)

```
dt
```

![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/778231b7-0348-40d9-bbd1-0f29502b21d9)

```
dt.Pclass.unique()
```

![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/82d82ba2-37d3-4511-b4cf-9b0d5152f590)

```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```

![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/0cb58196-b677-4e41-a3df-f88fb462d5da)


```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5, aspect=.7)
```

![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/4f81485c-da08-4000-922d-caa570e702fa)

```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```

![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/a082c136-fe29-4a35-8f06-cf92c59d1533)

```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/b1651552-69c6-4eb1-8a25-166e3099d171)

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```

![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/cc3bec5c-fb41-4f52-84fa-6678e27663d2)

```
sns.jointplot(x="Age",y="Fare",data=dt)
```

![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/003e5728-4972-43b0-8159-012e2b218852)

```
import matplotlib.pyplot as plt
fig, ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```

![image](https://github.com/SABARI005/EXNO2DS/assets/118660461/5adc4b31-766c-4ff5-ab34-86a115a5ed0d)

```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/7b72bb3b-6824-479c-8703-3d5378b2023e)
```
#co-relation
import seaborn as sns
corr=dt.corr()
sns.heatmap(corr,annot=True)
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/6b0e3e5a-85cc-489e-92dc-235451d57476)
```
sns.pairplot(dt)
```

![image](https://github.com/23006823/EXNO2DS/assets/138971409/eb83a5af-b99a-41fd-9c84-e0c828434964)

# RESULT

The code successfully excuted
