# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm :
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program.
## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: G.Jayanth.
RegisterNumber:  212221230030.
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")

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
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:
1. Data.head() value :

 ![image](https://github.com/JayanthYadav123/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94836154/9f8d300a-a95c-4f4f-8a87-da2f4e9ba554)

2.Data.info() value :

![image](https://github.com/JayanthYadav123/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94836154/aeb98c0e-e1c8-4d8e-96a8-838b311bf17b)


3.Null values :

![image](https://github.com/JayanthYadav123/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94836154/a9488ab8-bee2-405f-8e7d-d5b0bdc05a1a)


4.Fit & append method for KMeans :

![image](https://github.com/JayanthYadav123/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94836154/cb9f0a67-ab3e-4776-8cbd-52f362b8b2b2)

5.Pyplot graph for Elbow method :

![image](https://github.com/JayanthYadav123/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94836154/c4a5aec7-ee70-4471-bccb-2b36104b2388)


6.Number of clusters in KMeans :

![image](https://github.com/JayanthYadav123/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94836154/72f5ccf7-a921-4026-b2e0-7859dacce59b)

7.y_pred values :

![image](https://github.com/JayanthYadav123/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94836154/cc0d68eb-494d-4850-a236-390969d80d2a)

8.Customer segments graph :

![image](https://github.com/JayanthYadav123/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/94836154/58a6da3d-4bee-4684-ac4c-d04bef4e32cc)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
