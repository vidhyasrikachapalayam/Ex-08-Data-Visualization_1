# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
NAME:vidhyasri.k

REG.NO.:212222230170

import seaborn as sns

import pandas as pd

import matplotlib.pyplot as plt

df = sns.load_dataset("tips")

print(df)

df.isnull().sum()

Handling Outliers

plt.figure(figsize=(8,8))

plt.title("Data with Outliers")

df.boxplot()

plt.show()

Removing Outliers

plt.figure(figsize=(8,8))

cols = ['size','tip','total_bill']

Q1 = df[cols].quantile(0.25)

Q3 = df[cols].quantile(0.75)

IQR = Q3 - Q1

df = df[~((df[cols] < (Q1 - 1.5 * IQR)) |(df[cols] > (Q3 + 1.5 * IQR))).any(axis=1)]

plt.title("Dataset after removing outliers")

df.boxplot()

plt.show()

Which day of the week has the highest total bill amount?

sns.barplot(x=df['day'], y=df['total_bill'], hue=df['day'])

plt.legend(loc="center")

plt.title("Highest Total Bill Amount by day of the week")

plt.show()

What is the average tip amount given by smokers and non-smokers?

sns.boxplot(x=df['smoker'], y=df['tip'], hue=df['smoker'])

plt.title("Average Tip Amount given by smokers and non-smokers")


How does the tip percentage vary based on the size of the dining party?

df["tip_percent"] = df["tip"] / df["total_bill"]

sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)

plt.title("Tip Percentage by Dining Party Size")

Which gender tends to leave higher tips?

sns.boxplot(x=df['sex'], y=df['tip'],hue=df['sex'])

plt.title("Tips based on gender")

Is there any relationship between the total bill amount and the day of the week?

sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])

plt.legend(loc="best")

plt.title("Total bill amount by day of the week")

How does the distribution of total bill amounts vary across different time periods (lunch vs. dinner)?

sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")

plt.title("Distribution of Total Bill Amounts by Time of Day")

plt.show()

Which dining party size group tends to have the highest average total bill amount?

sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])

plt.title("Average Total Bill Amount by Dining Party Size")

plt.show()

What is the distribution of tip amounts for each day of the week?
sns.boxplot(x="day", y="tip", data=df)

plt.title("Tip Amount by Day of Week")

plt.show()

How does the tip amount vary based on the type of service (lunch vs. dinner)?

sns.violinplot(x="time", y="tip", data=df)

plt.title("Tip Amount by Time of Day")

plt.show()

Is there any correlation between the total bill amount and the tip amount?

sns.scatterplot(x="total_bill", y="tip", data=df)

plt.title("Correlation between Tip Amount and Total Bill Amount")

plt.show()



# OUPUT
![image](https://github.com/vidhyasrikachapalayam/Ex-08-Data-Visualization_1/assets/119477817/5b57cab0-993f-4fef-8e88-71426b3540f5)

![image](https://github.com/vidhyasrikachapalayam/Ex-08-Data-Visualization_1/assets/119477817/693e1ff3-624d-4221-b91c-0ef1fcc57275)

![image](https://github.com/vidhyasrikachapalayam/Ex-08-Data-Visualization_1/assets/119477817/193b8a8a-f210-426f-8961-382d87d68b73)

![image](https://github.com/vidhyasrikachapalayam/Ex-08-Data-Visualization_1/assets/119477817/e05e927f-be78-4199-8569-67c15c5afbe8)

![image](https://github.com/vidhyasrikachapalayam/Ex-08-Data-Visualization_1/assets/119477817/b818f900-806b-4bcb-acff-be480c818292)

![image](https://github.com/vidhyasrikachapalayam/Ex-08-Data-Visualization_1/assets/119477817/10dd3411-fe1e-4c2d-8ee0-cc8a8faacfa5)

![image](https://github.com/vidhyasrikachapalayam/Ex-08-Data-Visualization_1/assets/119477817/04786743-3c63-45b6-bdda-343b0c127d2a)

![image](https://github.com/vidhyasrikachapalayam/Ex-08-Data-Visualization_1/assets/119477817/52f06575-c702-4f9f-aee1-b23fb6737597)

![image](https://github.com/vidhyasrikachapalayam/Ex-08-Data-Visualization_1/assets/119477817/308f7d6e-1629-409c-b7ec-a960a9e5566f)

![image](https://github.com/vidhyasrikachapalayam/Ex-08-Data-Visualization_1/assets/119477817/56c1e644-339a-4d47-b45e-7872d8dd1c11)

![image](https://github.com/vidhyasrikachapalayam/Ex-08-Data-Visualization_1/assets/119477817/26dcf4cd-b2eb-4484-9398-cb4650da8ae1)

![image](https://github.com/vidhyasrikachapalayam/Ex-08-Data-Visualization_1/assets/119477817/e5b492d3-8aea-4f1b-b96b-5b22191c21b7)

![image](https://github.com/vidhyasrikachapalayam/Ex-08-Data-Visualization_1/assets/119477817/d645ce1d-5c45-4d54-a7ab-dfb1aa2f7077)

![image](https://github.com/vidhyasrikachapalayam/Ex-08-Data-Visualization_1/assets/119477817/c3a9af9d-5bed-48bd-b46b-064ab67b04ee)

# RESULT
Thus the Data Visualization method is performed to the given data and to predict the outcome for the given questions.

