## Implementation-of-K-Means-Clustering-for-Customer-Segmentation
## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
Hardware – PCs
Anaconda – Python 3.7 Installation / Jupyter notebook
## Algorithm

Import pandas and matplot libraries.

import Kmeans algorithm to solve customer segmentation.

Using the for loop cluster the given data

Predict the output and plot data graphs.

Display the outputs

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Yuvabharathi.B
RegisterNumber:  212222230181

import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1) (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
WCSS=[]

for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  WCSS.append(kmeans.inertia_)

  plt.plot(range(1,11), WCSS)
plt.xlabel("No. of clusters")
plt.ylabel("WCSS")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
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
plt.title("Customer segments")
```
## Output:
### data.head() function
![image](https://github.com/yuvabharathib/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113497404/83a47574-5e5b-4ecf-b9fd-c38303dbbfd4)
### data.info
![image](https://github.com/yuvabharathib/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113497404/7edbf7f6-ed86-4280-b5e3-f333ee58fb96)
### data.isnull().sum() function
![image](https://github.com/yuvabharathib/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113497404/81f20899-76e1-4b0e-bf48-d40204eadf3f)
### Elbow Method Graph
![image](https://github.com/yuvabharathib/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113497404/f31a760e-461f-46da-bf6f-e85a50db46d6)
### KMeans clusters
![image](https://github.com/yuvabharathib/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113497404/531cb5d6-befa-465e-8d29-7f75e45e215b)
### array()
![image](https://github.com/yuvabharathib/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113497404/38ad9b5b-aeb7-4990-aaf8-9b116b1b71fb)
### Customers segments Graph
![image](https://github.com/yuvabharathib/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113497404/4a32f28b-f3ee-4164-9c87-12fa82fb9a07)
## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming
