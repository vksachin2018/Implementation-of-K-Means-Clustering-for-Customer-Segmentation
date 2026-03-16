# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load the customer dataset and select relevant features such as Annual Income and Spending Score.
2. Determine the optimal number of clusters using the Elbow Method by computing WCSS for different values of k.
3. Initialize the K-Means algorithm with the chosen number of clusters and fit it to the dataset.
4. Assign each customer to the nearest cluster centroid based on distance.
5. Visualize the formed clusters to analyze and interpret customer segments.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Gokul sachin k
RegisterNumber:  212223220025
*/
```

```python
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

data = pd.read_csv("/content/Mall_Customers.csv")

print(data.head())

print(data.info())

print(data.isnull().sum())

wcss = []

for i in range(1, 11):
    kmeans = KMeans(n_clusters=i, init="k-means++", random_state=42)
    kmeans.fit(data.iloc[:, 3:5])   
    wcss.append(kmeans.inertia_)

plt.plot(range(1, 11), wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("WCSS")
plt.title("Elbow Method")
plt.show()

km = KMeans(n_clusters=5, init="k-means++", random_state=42)
km.fit(data.iloc[:, 3:5])

y_pred = km.predict(data.iloc[:, 3:5])

data["cluster"] = y_pred

df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]

plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"], c="red", label="Cluster 0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c="black", label="Cluster 1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c="blue", label="Cluster 2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"], c="green", label="Cluster 3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"], c="magenta", label="Cluster 4")

plt.xlabel("Annual Income (k$)")
plt.ylabel("Spending Score (1-100)")
plt.title("Customer Segments")
plt.legend()
plt.show()

```

## Output:

<img width="1220" height="540" alt="image" src="https://github.com/user-attachments/assets/71f0a452-fd89-435d-ba3a-33814000f168" />

<img width="1019" height="935" alt="image" src="https://github.com/user-attachments/assets/dda5cd1e-9137-45b9-8c90-113fc11a3cb8" />

<img width="1084" height="880" alt="image" src="https://github.com/user-attachments/assets/19a3fcdb-8a61-4379-b8ff-778b263e7471" />

<img width="1283" height="452" alt="image" src="https://github.com/user-attachments/assets/f5230770-a4b1-43fa-a0ed-df06eb738001" />

<img width="1283" height="452" alt="image" src="https://github.com/user-attachments/assets/ea991359-ca80-4ac7-955f-f65825f709cb" />

<img width="1230" height="895" alt="image" src="https://github.com/user-attachments/assets/a97bd672-0778-4ee9-b834-fc5facf7a33c" />


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.

