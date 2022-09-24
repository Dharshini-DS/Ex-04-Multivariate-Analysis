# Ex-04-Multivariate-Analysis

## AIM
To perform Multivariate EDA on the given data set.

## Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:

### STEP 1
Import the built libraries required to perform EDA and outlier removal.

### STEP 2
Read the given csv file

### STEP 3
Convert the file into a dataframe and get information of the data.

### STEP 4
Return the objects containing counts of unique values using (value_counts()).

### STEP 5
Plot the counts in the form of Histogram or Bar Graph.

### STEP 6
Use seaborn the bar graph comparison of data can be viewed.

### STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

### STEP 8
Save the final data set into the file

## PROGRAM
```
Name : DHARSHINI DS
Register Number : 212221230022

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df=pd.read_csv("SuperStore.csv")
df
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sns.scatterplot(df['Row ID'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Row ID"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Row ID")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("ROW ID")
plt.show()
states=df.loc[:,["Segment","Row ID"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Row ID")
sns.barplot(x=states.index,y="Row ID",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("ROW ID")
plt.show()
sns.barplot(df['Sales'],df['Ship Mode'],hue=df['Region'])
df.corr()
sns.heatmap(df.corr(),annot=True)
```
## OUTPUT

### DATA
![ds1](https://user-images.githubusercontent.com/93427345/192081855-93a0a135-2e83-426c-bf0b-9a5cee4417ea.PNG)

### DATA INFORMATION
![ds2](https://user-images.githubusercontent.com/93427345/192081863-502f4e6f-dbc0-43ac-a56a-b67cdfdeaacf.PNG)

### DATA DESCRIBE
![ds3](https://user-images.githubusercontent.com/93427345/192081866-1eaf8f71-77c1-4d44-9fbd-badc5eb54976.PNG)

### Checking the null values and Cleaning it
![ds4](https://user-images.githubusercontent.com/93427345/192081868-bb1c6a2b-c388-4297-8f9d-062a9a6382fa.PNG)

![ds5](https://user-images.githubusercontent.com/93427345/192081870-5a17f340-ca8e-4f27-9d52-00c8c5b6f0b0.PNG)

### DATA TYPES
![ds6](https://user-images.githubusercontent.com/93427345/192081875-cd5f61b7-a6e7-4b7d-a747-dc97b19dea7a.PNG)

### SCATTERPLOT
![ds7](https://user-images.githubusercontent.com/93427345/192081882-1b088cb0-ee09-4334-8fa6-77464adbf84a.PNG)

### BARPLOT
![ds8](https://user-images.githubusercontent.com/93427345/192081890-828a4d08-bdce-4c45-b4cc-902510b8e335.PNG)
![ds9](https://user-images.githubusercontent.com/93427345/192081895-94ab27ad-2785-4f74-b928-efb3244f4f07.PNG)
![ds10](https://user-images.githubusercontent.com/93427345/192081899-53b88f37-48b0-4e53-9f2c-8ad7cc70fc20.PNG)
![ds11](https://user-images.githubusercontent.com/93427345/192081915-7ed8001c-8c90-46a6-a7d9-d94d5c680e5d.PNG)

### CORRELATION COEFFICIENT INTERPRETATION
![ds12](https://user-images.githubusercontent.com/93427345/192081924-97ec7304-77c5-48d0-be48-1c62862c7cef.PNG)

### HEATMAP
![ds13](https://user-images.githubusercontent.com/93427345/192081930-9ee4f96a-9dad-47e3-be5a-7560aae588e1.PNG)

## RESULT
Thus we have read the given data and performed the multivariate analysis with different types of
plots.
