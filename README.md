# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import pandas and matplot libraries.
2. import Kmeans algorithm to solve customer segmentation.
3. Using the for loop cluster the given data
4. Predict the output and plot data graphs.
5. Display the outputs

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by:GOKUL SACHIIN K
RegisterNumber:212223220025
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []  #Within-Cluster sum of square. 
for i in range(1,11):
  kmeans=KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
```
```
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
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
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")




```

## Output:
### DATA.HEAD() FUNCTION

![243089956-4ddf5cc1-60a4-4f52-9101-d0c664fef559](https://github.com/vksachin2018/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/149366019/1acb83d9-51d5-4bde-a60b-3813ca49d713)



### DATA.INFO()

![243089973-c980ee78-5b2d-4787-a428-599f1c6a1a9a](https://github.com/vksachin2018/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/149366019/c4bc3b91-a0ae-4e20-85e5-8dc1e90c06ab)

## Data.isnull().sum() function:

![243089988-e32c9584-db05-47f7-8953-c573ab2bd24b](https://github.com/vksachin2018/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/149366019/d79a9c2d-bae9-4472-a72e-2ef1983abb29)

## Elbow method Graph:

![243090005-12f65900-41fe-4ea8-8a3e-23b53f3ddd63](https://github.com/vksachin2018/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/149366019/c3190c46-2ff6-45af-93bd-cd8c5c6bffb3)

## KMeans clusters:
![243090030-c8cda73d-62dd-4850-a950-ffe8015453b9](https://github.com/vksachin2018/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/149366019/ca06dc7c-c6c1-4751-bfa9-824931eff5f7)

![243090101-24988003-5833-48d9-b5c6-bc95d368c31f](https://github.com/vksachin2018/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/149366019/fa837405-063d-495f-ba4e-2847882738bc)

## Customer segments Graph:

![243090050-f6c560cf-f5bb-4719-b6a4-eefd4cece1e0](https://github.com/vksachin2018/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/149366019/026dbc24-fcec-4f31-82a7-e126d5cd87bd)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
