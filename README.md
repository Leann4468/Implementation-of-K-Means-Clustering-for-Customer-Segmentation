# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Start the program
2. Import the necessary python libraries
3. Read the dataset of Mall_Customers csv file
4. From sklearn libraary select the cluster and import KMeans Clustering
5. Find the sum of squared distance between each points and the centroid in a cluster using Elbow Method
6. Plot the graph x and y as Number of Clusters and wcss respectively
7. Using the matplotlib library draw the scatter plot for the given number of clusters (ie. here n_clusters = 5)
8. Stop the program

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: LEANN JOBY MATHEW
RegisterNumber:  212222230074
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers.csv")

data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
data["cluster"] = y_pred

df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="olive",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="orange",label="cluster4")
```

## Output:

## Data Head:
![image](https://github.com/Leann4468/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121165979/dfc8bc85-3758-442a-b6e5-b5d856bd71aa)

## Checking For Null Data:
![image](https://github.com/Leann4468/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121165979/54136b02-9088-44f5-bef3-96f077beac0f)

## Data Information:
![image](https://github.com/Leann4468/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121165979/2e9f73e1-efef-4350-95a5-ca4e3a34f055)

## Elbow Method Graph:
![image](https://github.com/Leann4468/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121165979/6bbe22d8-e71a-4fed-a2cc-3285d447be6f)

## K-means Cluster:
![image](https://github.com/Leann4468/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121165979/cb1e87eb-fa81-4817-8ef6-1d6a80c420f4)

## Customer Segments Graph:
![image](https://github.com/Leann4468/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121165979/461d8ba8-8a6b-432c-9e5c-e7a459f2bf9c)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
