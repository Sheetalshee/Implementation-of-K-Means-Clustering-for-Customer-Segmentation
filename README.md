# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. 
2. 
3. 
4. 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: 
RegisterNumber:  
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers.csv")
```
```
data.head()
```
![Screenshot 2024-10-30 105321](https://github.com/user-attachments/assets/db8c773f-4dd4-4131-98ed-26bd03cc30cc)
```
data.info()
```
![Screenshot 2024-10-30 111035](https://github.com/user-attachments/assets/7b6b3f05-f67e-40bc-98fe-41007d652d94)
```
data.isnull().sum()
```
![Screenshot 2024-10-30 111448](https://github.com/user-attachments/assets/b13f8ee9-83e1-41e5-a992-d9253299c213)
```
from sklearn.cluster import KMeans
wcss = []
for i in range(1, 11):
    kmeans = KMeans(n_clusters = i, init = "k-means++")
    kmeans.fit(data.iloc[:, 3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1, 11), wcss)
plt.title("The Elbow Method")
plt.xlabel("Number of clusters")
plt.ylabel("WCSS")
plt.show()
```
![Screenshot 2024-10-30 112213](https://github.com/user-attachments/assets/20c4c4ae-5220-4aaf-93dc-5fd28a791cc3)

```
km = KMeans(n_clusters=5) 
km.fit(data.iloc[:, 3:])
```
![Screenshot 2024-10-30 111615](https://github.com/user-attachments/assets/d5e9c657-fcd3-4dd0-8100-3d7733dae0a4)

```
y_pred=km.predict(data.iloc[:,3:])
y_pred
```
![Screenshot 2024-10-30 111655](https://github.com/user-attachments/assets/bb52ac82-b9a8-47e9-a9f2-56e531595b18)
```
data["cluster_id"]=y_pred
data
```

![Screenshot 2024-10-30 111802](https://github.com/user-attachments/assets/4343b0d3-be48-4a4c-9657-478d75af2e61)
```
f0=data[data["cluster_id"]==0]
df1=data[data["cluster_id"]==1]
df2=data[data["cluster_id"]==2]
df3=data[data["cluster_id"]==3]
df4=data[data["cluster_id"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],color="red",label="cluster1")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],color="pink",label="cluster2")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],color="green",label="cluster3")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],color="blue",label="cluster4")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],color="black",label="cluster5")
plt.legend()
plt.title("Customer segment")
```
![Screenshot 2024-10-30 111901](https://github.com/user-attachments/assets/4bda912f-f326-4787-90a1-f68c8ef3811c)
```

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
