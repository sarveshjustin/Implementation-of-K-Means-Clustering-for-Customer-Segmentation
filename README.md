# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages.
2.Read the given csv file and display the few contents of the data.
3.Import KMeans and use for loop to calculate the within cluster sum of squares the data.
4.Plot the wcss for each iteration, also known as the elbow method plot.
5.Predict the clusters and plot them.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: sarvesh.s
RegisterNumber:  212222230135
*/
import pandas as pd
import matplotlib.pyplot as plt
df=pd.read_csv("Mall_Customers.csv")
df.head()
#checking the data information and null presence
df.info()
df.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
   kmeans = KMeans(n_clusters = i,init = "k-means++")
   kmeans.fit(df.iloc[:,3:])
   wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
plt.show()
km = KMeans(n_clusters = 5)
km.fit(df.iloc[:,3:])
y_pred = km.predict(df.iloc[:,3:])
df["cluster"] = y_pred
df0 = df[df["cluster"]==0]
df1 = df[df["cluster"]==1]
df2 = df[df["cluster"]==2]
df3 = df[df["cluster"]==3]
df4 = df[df["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-
100)"],c="yellow",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-
100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-
100)"],c="cyan",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-
100)"],c="skyblue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-
100)"],c="violet",label="cluster4")
plt.legend()
plt.title("Customer Segments")
plt.show()
```

## Output:
1.data.head()
![image](https://github.com/Afsarjumail/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343395/777e1fab-671a-4df1-b5e7-d645c93e50c3)


2.data.info()
![image](https://github.com/Afsarjumail/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343395/f8277bf1-f521-4fe0-9346-6e10f6bdd806)


3.data.isnull().sum()
![image](https://github.com/Afsarjumail/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343395/96fc98a3-99e3-4b7d-bfa2-a8b4359f74f5)

4.Elbow method
![image](https://github.com/Afsarjumail/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343395/04b49b6f-6575-473d-9198-bc1ff2daf64f)


KMeans clusters
![282255443-d37f64a4-47eb-4d9c-9758-b6ca015e312f](https://github.com/Afsarjumail/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343395/8540b455-5782-4a80-975d-1ee8dc6d4ab6)


array
![image](https://github.com/Afsarjumail/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343395/d05d5667-da53-46d8-bdf5-c4b10ab19be8)


Customer Segment graph
![image](https://github.com/Afsarjumail/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343395/7f7cf4d2-d0ed-40ea-b460-e847a8a35de8)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
