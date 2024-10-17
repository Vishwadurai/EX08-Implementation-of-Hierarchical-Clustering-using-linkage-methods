# EX8-Implementation of Hierarchical Clustering using linkage methods
## DATE:
## AIM:
To implement Hierarchical Clustering using single and complete linkage method

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.compute the distance between every pair of data points,resulting in a distance matrix

2.assign each data point to its own individual cluster

3.using a linkage criterion,find the two closest cluster and merge them

4.visualize the hierarchical clustering as a dendrogram


## Program:
```
/*
Program to implement Hierarchical Clustering using single and complete linkage method
Developed by: D.Vishwa
RegisterNumber:  2305001034
*/
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import dendrogram, linkage,fcluster
from sklearn.preprocessing import StandardScaler
df = pd.read_csv("/content/Hclus_EX8.csv")
df.head()
x = df[['StudentID','Marks']].values
x
z=linkage(x,method='complete')
plt.figure(figsize=(5,2))
plt.title("Dendogram for student segmentation")
labels=range(1,len(df)+1)
dendrogram(z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
max_cluster=2
clusters=fcluster(z,max_cluster,criterion='maxclust')
clusters
plt.figure(figsize=(5,2))
plt.scatter(x[:,0],x[:,1],c=clusters,cmap='rainbow',s=100)
plt.title("Student segmented(Hierarchical clustering)")
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
z=linkage(x,method='single')
plt.figure(figsize=(5,2))
plt.title("Dendogram for student segmentation")
labels=range(1,len(df)+1)
dendrogram(z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()
```

## Output:
![Screenshot 2024-10-17 110212](https://github.com/user-attachments/assets/09eaeb0b-63a9-488e-a078-5c6be8d524c7)
![Screenshot 2024-10-17 110222](https://github.com/user-attachments/assets/cdb25b7f-b36d-496e-b8ff-1c568116bc7e)
![Screenshot 2024-10-17 110222](https://github.com/user-attachments/assets/cdb25b7f-b36d-496e-b8ff-1c568116bc7e)
![Screenshot 2024-10-17 110251](https://github.com/user-attachments/assets/1865002d-148b-48ba-adf9-db74b0a4a1f2)
![Screenshot 2024-10-17 110304](https://github.com/user-attachments/assets/dac4e0a2-2944-42ef-89f9-62d81ae11273)
![Screenshot 2024-10-17 110312](https://github.com/user-attachments/assets/ea314984-4ce3-4f47-a052-fe8468aa62f8)
![Screenshot 2024-10-17 110321](https://github.com/user-attachments/assets/79df47d5-db7c-48db-ad58-0b2b834584b1)
![Screenshot 2024-10-17 110329](https://github.com/user-attachments/assets/a3e86c4d-103d-481f-9056-940b5c50d645)



## Result:
Thus the implementation of Hierarchical Clustering using single and complete linkage method in python programming and verified successfully.
