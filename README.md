# EX 9 Implementation of K Means Clustering for Customer Segmentation
## DATE:
## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Data Preprocessing
2. Initialize Centroids
3. Assign Clusters
4. Update Centroids

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: HARISH GOWTHAM E
RegisterNumber:2305002009
*/
import numpy as np
import pandas as pd
from sklearn.cluster import KMeans
from sklearn.metrics.pairwise import euclidean_distances
import matplotlib.pyplot as plt
data=pd.read_csv('/content/Mall_Customers_EX8.csv')
data
X = data[['Annual Income (k$)', 'Spending Score (1-100)']]
plt.figure(figsize=(4,4))
plt.scatter(X['Annual Income (k$)'],X['Spending Score (1-100)'])
plt.xlabel('Annual Income (k$)')
plt.ylabel('Spending Score (1-100)')
plt.show()
k=3
Kmeans=KMeans(n_clusters=k)
Kmeans.fit(X)
centroids=Kmeans.cluster_centers_
labels=Kmeans.labels_
print("Centroids:")
print(centroids)
print("Labels:")
print(labels)
colors=['r','g','b']
for i in range(k):
  cluster_points=X[labels==i]
  plt.scatter(cluster_points['Annual Income (k$)'],cluster_points['Spending Score (1-100)'],color=colors[i],label=f'Cluster{i+1}')
  distances=euclidean_distances(cluster_points,[centroids[i]])
  radius=np.max(distances)
  circle=plt.Circle(centroids[i],radius,color=colors[i],fill=False)
  plt.gca().add_patch(circle)
plt.scatter(centroids[:,0],centroids[:,1],marker='*',s=200,color='k',label='Centroids')
plt.title('K-means Clustering')
plt.xlabel('Annual Income (k$)')
plt.ylabel('Spending Score (1-100)')
plt.legend()
plt.grid(True)
plt.axis('equal')
plt.show()
```

## Output:
![Screenshot 2024-10-24 144554](https://github.com/user-attachments/assets/27cf5689-5334-4c2d-9537-d8cf8aced28c)
![Screenshot 2024-10-24 144649](https://github.com/user-attachments/assets/edb336ef-1f54-418f-aaa4-d30eec402406)
![Screenshot 2024-10-24 144738](https://github.com/user-attachments/assets/a03a5768-d1d8-48da-9150-94675b3a6a36)
![Screenshot 2024-10-24 144853](https://github.com/user-attachments/assets/28f029f9-93cc-4cea-8154-3f786264c210)






## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
