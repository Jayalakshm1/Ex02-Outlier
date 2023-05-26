# Ex02-Outlier

You are given bhp.csv which contains property prices in the city of banglore, India. You need to examine price_per_sqft column and do following,

(1) Remove outliers using IQR 

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

(4) for the data set height_weight.csv find the following

    (i) Using IQR detect weight outliers and print them

    (ii) Using IQR, detect height outliers and print them


#DEVELOPED BY:JAYALAKSHMI M
#REGISTER NUMBER:212221040066
# AIM:
To detect and remove the outlier in the given dataset and save the final
# PROGRAM
```
import pandas as pd
import numpy as np
import seaborn as sns
df=pd.read_csv ("bhp.csv")
df
df.head()
df.info()
df.describe()
df.isnull().sum()
df.shape
sns.boxplot(x="price_per_sqft",data=df)
q1=df['price_per_sqft'].quantile(0.25)
q3=df['price_per_sqft'].quantile(0.75)
print("First Quantile=",q1,"\nSecond Quantile=",q3)
IQR=q3-q1
u1=q3+1.5*IQR
l1=q1-1.5*IQR
df1=df[((df['price_per_sqft']>=l1)&(df['price_per_sqft']<=u1))]
df1
df1.shape
sns.boxplot(x="price_per_sqft",data=df1)
from scipy import stats
z=np.abs(stats.zscore(df['price_per_sqft' ]))
df2=df[(z<3)]
df2 
df2.head()
df2.info()
df2.describe()
df2.isnull().sum()
```
# OUTPUT
![EX02_OUTLIER](ex2(1).png)
![EX02_OUTLIER](ex2(2).png)
![EX02_OUTLIER](ex2(3).png)
![EX02_OUTLIER](ex2(4).png)
![EX02_OUTLIER](ex2(5).png)
![EX02_OUTLIER](ex2(6).png)
![EX02_OUTLIER](ex2(7).png)
![EX02_OUTLIER](ex2(8).png)
![EX02_OUTLIER](ex2(9).png)
# RESULT
To detect and remove the outlier in the given dataset and save the finalised