# Ex-04-Multivariate-Analysis

## Aim
To perform Multivariate EDA on the given data set.

##Explanation
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## Algorithm

### Step1
Import the built libraries required to perform EDA and outlier removal.

### Step2
Read the given csv file.

### Step3
Convert the file into a dataframe and get information of the data.

### Step4
Return the objects containing counts of unique values using (value_counts()).

### Step5
Plot the counts in the form of Histogram or Bar Graph.

### Step6
Use seaborn the bar graph comparison of data can be viewed.

### Step7
Find the pairwise correlation of all columns in the dataframe.corr()

### Step8
Save the final data set into the file.

## Code

```
Developed by : Naveen Kumar.M
Registration Number : 212221040113
```

```
import pandas as pd
import numpy as py
import seaborn as sns
import matplotlib.pyplot as plt

df=pd.read_csv('SuperStore.csv')
df
df.head()
df.info()
df.describe()
df.isnull().sum()
df.dtypes

sns.scatterplot(x='Postal Code',y='Sales',data=df)

sns.barplot(x=df['Row ID'],y=df['Segment'],data=df)

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()

sns.barplot(x='Category',y='Postal Code',data=df)

df.corr()
sns.heatmap(df.corr(),annot=True)
```

## Output

### Data

![](./1.png)

### Data head

![](./2.png)

### Data Information

![](./3.png)

### Data describe

![](./4.png)

### Data Null Values

![](./5.png)

### Data Types

![](./6.png)

### Scatterplot

![ex 4 1](https://user-images.githubusercontent.com/128135244/229702193-6cd2eeef-b028-462b-b789-e488e8375a90.png)

### Barplot

![ex 4 2](https://user-images.githubusercontent.com/128135244/229702278-48114dc7-734f-4982-9714-db11a9b2dd73.png)

![ex 4 3](https://user-images.githubusercontent.com/128135244/229702347-2bd2e2fc-735b-435c-88af-831937a3fd46.png)

![ex 4 4](https://user-images.githubusercontent.com/128135244/229702365-221fc1e7-ffa9-4931-b777-d1692246d95b.png)

### Correlation and Heatmap
![ex 4 6](https://user-images.githubusercontent.com/128135244/229702401-e34b4c36-46c7-46f9-a814-98137b4a8571.png)

![ex 4 5](https://user-images.githubusercontent.com/128135244/229702440-d1863824-d3dd-4d09-97c5-0bbb2a89c800.png)

## Result
Thus the program to perform EDA on the given data set is successfully executed.
