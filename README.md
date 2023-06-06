Ex-04-Multivariate-Analysis

AIM:

To perform Multivariate EDA on the given data set.

EXPLANATION:

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

ALGORITHM:

Step1:

Import the built libraries required to perform EDA and outlier removal.

Step2:

Read the given csv file.

Step3:

Convert the file into a dataframe and get information of the data.

Step4:

Return the objects containing counts of unique values using (value_counts()).

Step5:

Plot the counts in the form of Histogram or Bar Graph.

Step6:

Use seaborn the bar graph comparison of data can be viewed.

Step7:

Find the pairwise correlation of all columns in the dataframe.corr()

Step8:

Save the final data set into the file.

PROGRAM:

Developed by : JOEL P

Registration Number :212222230057

```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df.head(6)
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
sns.scatterplot (df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Postal Code"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Postal Code",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("Postal Code")
plt.show()
states=df.loc[:,["Segment","Sales"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")
#plt.figure(figsize=(10,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("SALES")
plt.show()
sns.barplot(df['Postal Code'])
df.corr()
sns.heatmap(df.corr(),annot=True)
```

OUTPUT:

SuperStore.csv

df.head()

![image](https://user-images.githubusercontent.com/118626456/231064494-73b48314-002d-4801-bf17-6e9815f08aff.png)

df.info()

![image](https://user-images.githubusercontent.com/118626456/231064636-9f191dc7-cde8-4657-92c1-ec2f39a72ad8.png)

df.describe()

![image](https://user-images.githubusercontent.com/118626456/231064693-00eedf54-d5f2-4abc-9d9e-c0d5f43fccff.png)

df.isnull().sum()

![image](https://user-images.githubusercontent.com/118626456/231064850-4ad037e3-bec6-4b0a-a2c8-fe6dae11c994.png)

AFTER CLEANING: df.isnull().sum()

![image](https://user-images.githubusercontent.com/118626456/231064917-bd3b8326-17b1-412a-a40e-f3d55e0de452.png)

Scatterplot

![image](https://user-images.githubusercontent.com/118626456/231065024-6e0a4404-07d2-4bb5-81d9-49e8752ed52e.png)

Barplot

![image](https://user-images.githubusercontent.com/118626456/231065429-9988a6e2-850e-4976-bb3a-0cac0f5159b5.png)

![image](https://user-images.githubusercontent.com/118626456/231065149-703307b0-94df-4da6-acfc-5a3e03d55af8.png)

![image](https://user-images.githubusercontent.com/118626456/231065476-500a4d57-2715-4c3d-8c0f-c8504a74e559.png)

HeatMap

![image](https://user-images.githubusercontent.com/118626456/231065545-5752e7c8-d5fc-4379-b35d-17d85935d225.png)

RESULT:

Thus the program to perform EDA on the given data set is successfully executed.
