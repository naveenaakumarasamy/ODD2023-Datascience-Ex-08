# Ex-08-Data-Visualization-
# AIM
To Perform Data Visualization on a complex dataset and save the data to a file.

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
## STEP 1
Read the given Data

## STEP 2
Clean the Data Set using Data Cleaning Process

## STEP 3
Apply Feature generation and selection techniques to all the features of the data set

## STEP 4
Apply data visualization techniques to identify the patterns of the data.

# CODE:
```
NAME:Naveenaa A K
REGISTER NUMBER:212222230094

#Import required libraries

import pandas as pd

import seaborn as sns

import matplotlib.pyplot as plt

#Load the dataset

df = pd.read_csv('Superstore2.csv', encoding='unicode_escape')

#Data Cleaning: Drop unnecessary columns

df.drop(['Row ID', 'Order ID', 'Ship Date', 'Customer ID', 'Postal Code', 'Product ID'], axis=1, inplace=True)

#Feature Generation: Extract Year and Month from Order Date

df['Year'] = pd.DatetimeIndex(df['Order Date']).year

df['Month'] = pd.DatetimeIndex(df['Order Date']).month_name()

#1. Which Segment has Highest sales?

segment_sales = df.groupby('Segment')['Sales'].sum().reset_index()

plt.figure(figsize=(8,5))

sns.barplot(x='Segment', y='Sales', data=segment_sales)

plt.title('Segment-wise Sales')

plt.show()

#2. Which City has Highest profit?

city_profit = df.groupby('City')['Profit'].sum().reset_index().sort_values(by='Profit', ascending=False)

plt.figure(figsize=(12,8))

sns.barplot(x='City', y='Profit', data=city_profit.head(10))

plt.title('Top 10 Cities by Profit')

plt.show()

#3. Which ship mode is profitable?

shipmode_profit = df.groupby('Ship Mode')['Profit'].sum().reset_index()

plt.figure(figsize=(8,5))

sns.barplot(x='Ship Mode', y='Profit', data=shipmode_profit)

plt.title('Ship Mode-wise Profit')

plt.show()

#4. Sales of the product based on region

region_sales = df.groupby('Region')['Sales'].sum().reset_index()

plt.figure(figsize=(8,5))

sns.barplot(x='Region', y='Sales', data=region_sales)

plt.title('Region-wise Sales')

plt.show()

#5. Find the relation between sales and profit

plt.figure(figsize=(8,5))

sns.scatterplot(x='Sales', y='Profit', data=df)

plt.title('Sales vs. Profit')

plt.show()

#6. Find the relation between sales and profit based on the following category.

#i) Segment

segment_sales_profit = df.groupby('Segment')['Sales', 'Profit'].mean().reset_index()

plt.figure(figsize=(8,5))

sns.barplot(x='Segment', y='Sales', data=segment_sales_profit, color='blue', alpha=0.5, label='Sales')

sns.barplot(x='Segment', y='Profit', data=segment_sales_profit, color='green', alpha=0.5, label='Profit')

plt.title('Segment-wise Sales and Profit')

plt.legend()

plt.show()

#ii) City

city_sales_profit = df.groupby('City')['Sales', 'Profit'].mean().reset_index().sort_values(by='Profit', ascending=False).head(10)

plt.figure(figsize=(12,8))

sns.barplot(x='City', y='Sales', data=city_sales_profit, color='blue', alpha=0.5, label='Sales')

sns.barplot(x='City', y='Profit', data=city_sales_profit, color='green', alpha=0.5, label='Profit')

plt.title('Top 10 Cities by Sales and Profit')

plt.legend()

plt.show()

#iii) States

plt.figure(figsize=(8,5))

sns.scatterplot(x='Sales', y='Profit', hue='State', data=df)

plt.title('Sales vs. Profit based on State')

plt.show()

#iv) Segment and Ship Mode

plt.figure(figsize=(8,5))

sns.scatterplot(x='Sales', y='Profit', hue='Segment', style='Ship Mode', data=df)

plt.title('Sales vs. Profit based on Segment and Ship Mode')

plt.show()

#v) Segment, Ship mode and Region

plt.figure(figsize=(8,5))

sns.scatterplot(x='Sales', y='Profit', hue='Segment', style='Ship Mode', size='Region', data=df)

plt.title('Sales vs. Profit based on Segment, Ship Mode and Region')

plt.show()
```
# OUTPUT:

![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-08/assets/113497406/7d0bc8d2-352f-47ca-80c0-372b1be2128d)
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-08/assets/113497406/b82cf55b-c3dd-41d1-995d-be4022459f68)
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-08/assets/113497406/9c51c0a0-8e6a-485f-a1f9-cdddc026f946)
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-08/assets/113497406/35461bfd-d3d9-4890-9eff-3c48188d081b)
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-08/assets/113497406/8ace0d6a-61c0-4837-96e5-556a1bf724fb)
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-08/assets/113497406/c84d8f11-c162-4431-97a0-19d7f4222d1a)
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-08/assets/113497406/66ae5619-b770-4ffa-91c8-9a5d38922793)
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-08/assets/113497406/ec6746f2-a2ce-4173-b1a7-68d5f477bcee)
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-08/assets/113497406/08123974-481a-4550-8a41-d1b629466973)
![image](https://github.com/naveenaakumarasamy/ODD2023-Datascience-Ex-08/assets/113497406/4701e0d8-e400-446e-acc2-c4e9fa905981)
# RESULT:
Hence the data visualization method for the given dataset applied successfully.
