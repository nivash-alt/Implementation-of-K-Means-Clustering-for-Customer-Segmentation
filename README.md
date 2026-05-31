# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Step1: Import the necessary packages using import statement.                                   
Step2: Read the given csv file using read_csv() method and print the number of contents to be
displayed using df.head().                               
Step3: Import KMeans and use for loop to cluster the data.                     
Step4: Predict the cluster and plot data graphs.                 
Step5: Print the outputs and end the program            

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Nivash P
RegisterNumber:  212225230203
*/

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers (1).csv")
data.head()
data.info()
data.isnull()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss= []
for i in range(1,11):
kmeans=KMeans(n_clusters = i,init = "k-means++")
kmeans.fit(data.iloc[:,3:])
wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km=KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
11/24/24, 6:00 PM Guhanandan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation
https://github.com/Guhanandan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation 1/4
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="black",label="clu
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="cyan",label="clust
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="yellow",label="cl
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="clust
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="green",label="clu
plt.legend()
plt.title("Customer Segments")
```

## Output:
<img width="784" height="361" alt="image" src="https://github.com/user-attachments/assets/4bcc71ea-80f8-4b8e-90ba-8abb81fb26cf" />

Checking for Null Data:
<img width="496" height="217" alt="image" src="https://github.com/user-attachments/assets/9c8ed2d7-699a-4da6-ae04-3b1ebe94608c" />
Data Information:
<img width="771" height="403" alt="image" src="https://github.com/user-attachments/assets/1f92e9d6-cbef-4868-8ae2-ef97461c2ebb" />
Within Cluster Sum of Squares:
<img width="669" height="222" alt="image" src="https://github.com/user-attachments/assets/152a3aa9-5e97-457d-9a0c-95228537cb20" />




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
