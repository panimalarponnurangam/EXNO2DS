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
~~~~
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns 
df=pd.read_csv("titanic_dataset.csv")
df
~~~~
![image](https://github.com/user-attachments/assets/1c1ce4cc-03a7-4062-ab3b-42470b16d82d)
~~~~
df.info()
~~~~
![image](https://github.com/user-attachments/assets/22f3dc26-1e8e-4830-b5be-03f8f3dee53a)
~~~~
df.shape
~~~~
![image](https://github.com/user-attachments/assets/3e175af9-b4f8-4945-bae7-2eb1e885304f)
~~~~
df.set_index("PassengerId",inplace=True)
df.describe()
~~~~
![image](https://github.com/user-attachments/assets/c91961b3-1a2a-42d0-b944-839886ced96c)
~~~~

df.shape
~~~~
![image](https://github.com/user-attachments/assets/a20000d4-662b-449b-b0fa-f464df870270)

Categorical data analysis
~~~~
df.nunique()
~~~~
![image](https://github.com/user-attachments/assets/e2027408-803c-4425-943b-27e511c8ecfc)
~~~~

df["Survived"].value_counts()
~~~~

![image](https://github.com/user-attachments/assets/9e788512-04e2-4e2a-9cb0-8d02b56a5bf2)
~~~~
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
~~~~
![image](https://github.com/user-attachments/assets/31d1512c-4605-45e9-ba46-2240acc73ddc)

````
ns.countplot(data=df,x="Survived")

````
![366010095-c0cf2836-37f2-4375-8c23-4683bb745434](https://github.com/user-attachments/assets/b57cd8ec-f52b-4265-9630-1f5a052c6969)
`````
df
``````
![366072870-21973863-d4ef-4d5f-8b3e-b9a8bf6d6ac2](https://github.com/user-attachments/assets/a159688e-4d9b-4984-abee-0fac3dd51680)
````
df.Pclass.unique()

````
![366073242-f885d8c6-8853-4b1a-8e78-7f6067cb479c](https://github.com/user-attachments/assets/ffef46ee-c984-4ee2-b51e-51c466197d37)
````
df.rename(columns={'Sex':'Gender'},inplace=True)
df
````

![366073593-3d3614e7-1832-4802-8fca-d70a86df9369](https://github.com/user-attachments/assets/a714ff70-ecc7-4b50-b342-a1faa670d1ac)
Bivariate Analysis

````
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
````

![366073956-c8b44162-3a88-431b-b21f-29b467e3ecbc](https://github.com/user-attachments/assets/ddab587f-c246-4a16-b086-b035fc8f8df2)
````
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
````

![366074496-3abf2cac-ad2d-416d-8fa4-b6323a2b08fd](https://github.com/user-attachments/assets/641f279d-b7c9-4cbb-8832-5c973fe4102b)

````
df.boxplot(column="Age",by="Survived")
````
![366074811-42095543-8ea8-44cd-bb87-00896d5d65ae](https://github.com/user-attachments/assets/7843c714-de51-4665-9d0a-ed9cd07da27c)

````
sns.scatterplot(x=df["Age"],y=df["Fare"])
````

![366075170-be003743-cb0f-40df-b419-167c37da8b0e](https://github.com/user-attachments/assets/05c9efc1-f2d2-4bb3-81a6-59743547cd1a)
````
sns.jointplot(x="Age",y="Fare",data=df)
````


![366075601-9bc1238d-accf-4719-b6bc-f0d22508491e](https://github.com/user-attachments/assets/768442e7-52d7-46b1-92bc-130a39d46089)

Multivariate Analysis
````
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
````

![366077214-e8ae7471-ddf7-43f6-a837-e2fe2a51f3f0](https://github.com/user-attachments/assets/cd7ebddb-78db-4c2d-9eb9-d2ae2593c13c)
````
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
````
![366077992-3342116c-1702-434a-aadd-994dfc55974b](https://github.com/user-attachments/assets/90e1ac3c-b593-422b-b7e6-4e0b24d0517f)

Co-relation
````
corr=df.corr()
sns.heatmap(corr,annot=True)
````

![366078406-c2a9c49e-efb9-4232-900a-936c347ab084](https://github.com/user-attachments/assets/3289cbef-4f07-4c46-aa3e-930afcd08c83)
````
sns.pairplot(df)
`````
![366078866-c8a2e266-a4d2-4929-b52b-bf8109d5edd4](https://github.com/user-attachments/assets/cc6c5fb1-cd17-4e83-80cc-7a2446ea938e)





# RESULT
      Exploratory Data Analysis on the given data set successfully.
