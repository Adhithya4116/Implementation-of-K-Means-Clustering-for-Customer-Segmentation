# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the output and end the program.

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Adhithya Perumal.D
RegisterNumber:  212222230007
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1) (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No . of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")

km=KMeans(n_clusters = 5)
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
plt.title("Customer Segments   ")

```

## Output:
![279423192-d16401ee-0a7a-41c1-9da9-9a2b1d7023f8](https://github.com/Adhithya4116/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707079/a25c396b-c818-481d-ad27-49085ab85eb6)

![279423248-3e762761-9fa8-428d-81f4-6513a227b86b](https://github.com/Adhithya4116/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707079/c9293ecd-a76e-49d6-bcf5-e5ebb4c258c1)

![279423314-d6c2b1e5-5461-43a6-905a-4766fd44cc0c](https://github.com/Adhithya4116/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707079/767c1d30-bf37-4176-878a-a44d02196c96)

![279423405-dc1cc3ec-c98b-45cc-8644-7adc8890afac](https://github.com/Adhithya4116/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707079/96f57822-3ddf-4320-93f6-6cb73eacd555)

![279423484-c8bb3def-f5ff-42e8-a672-ef945fb09883](https://github.com/Adhithya4116/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707079/a6efe5de-ced4-4655-afa8-c9db91651d55)

![279423552-88f28979-9ebf-4376-b9ad-5fb06fdfe0cd](https://github.com/Adhithya4116/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707079/75284af8-4a50-4baa-9271-2e23eb52de36)

![279423618-80f2b622-1a6b-422f-98df-75a32afe60b8](https://github.com/Adhithya4116/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707079/cd45942d-c11b-422a-82bf-234189ef4322)

![279423666-e458fc92-fb10-43e8-8376-c47dd8522dd2](https://github.com/Adhithya4116/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118707079/1b47e8a4-1e58-49f7-85df-101da6051895)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
