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
![K Means Clustering for Customer Segmentation](sam.png)

## Data Head:
![image](https://github.com/JoyceBeulah/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343698/7eb6e04b-0b61-4156-b4e6-5b071d1ede9b)

## Checking For Null Data:
![image](https://github.com/JoyceBeulah/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343698/5dda8a64-573b-489e-b049-4f52672c6eb7)

## Data Information:
![image](https://github.com/JoyceBeulah/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343698/dafbcd94-4b34-4e64-9342-0de30c86123e)

## Elbow Method Graph:
![image](https://github.com/JoyceBeulah/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343698/241af4e6-ea19-40b5-a4db-664b86b3af8b)

## K-means Cluster:
![image](https://github.com/JoyceBeulah/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343698/b48ce1fa-aed0-46dd-ba1c-6d93743182e5)

## Customer Segments Graph:
![image](https://github.com/JoyceBeulah/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118343698/9fa17ecf-2310-49ee-bfe0-3089fddf19b5)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
