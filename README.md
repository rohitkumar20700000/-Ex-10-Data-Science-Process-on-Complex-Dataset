# Flight information -analysis

## AIM :

To Perform Bivariate/Multivariate Analysis

## DATE:

GITHUB LINK:https://github.com/Hariharan5354/EX-10-Data-Science-process-on-Complex-Dataset.git

COLAB LINK:https://colab.research.google.com/drive/1NVXuiyaSNIa2AyA1-P9UxAfYcm096ZPl?usp=sharing

## ALGORITHM :

1.Read the given data

2.Get information from the data

3.Perform the Multivariate Analysis

4.Save the clean data to file

## PROGRAM :

Developed by: Rohit Kumar.M
Reg no: 212221220045

import pandas as pd

import numpy as np

import seaborn as sns

import matplotlib.pyplot as plt

import io

from google.colab import files

uploaded = files.upload()

dd = pd.read_csv(io.BytesIO(uploaded['FlightInformation.csv']))

print(dd)

## TYPES OF BIVARIATE ANALYSIS:

### (i) Numerical & Numerical

sns.scatterplot (dd['Date_of_Journey'],dd['Dep_Time'])

![image]

### (ii) Numerical & Categorical

sns.barplot (x=dd['Duration'],y=dd['Price'])

![image]

sns.barplot(x=dd["Arrival_Time"],y=dd["Price"],data=dd)

![image]

states=dd.loc[:,["Duration","Price"]]

states=states.groupby(by=["Duration"]).sum().sort_values(by="Price")

sns.barplot(x=states.index,y="Price",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Duration")

plt.ylabel=("Price")

plt.show()

![image]

## Multivariate Analysis :

dd.corr()

data = np.random.randint(low = 1, high = 100, size = (10, 10))

print("The data to be plotted:\n")

print(data)

hm = sns.heatmap(data = data)

plt.show()

![image]

## RESULT:

Thus, Bivariate/Multivariate Analysis is performed successfully.
