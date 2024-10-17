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
Program to implement Hierarchical Clustering using single and complete linkage method
Developed by:BASHA VENU
RegisterNumber:2305001005

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
![image](https://github.com/user-attachments/assets/73337105-c64f-4764-a646-7e69c0d4435a)
![image](https://github.com/user-attachments/assets/a40a0e8f-281e-4568-9cc1-1a6326fa27c1)
![image](https://github.com/user-attachments/assets/f5168e8c-73ab-434a-8b54-ef651c29feae)
![image](https://github.com/user-attachments/assets/ca195279-a73d-4291-8291-b00ce5bf46bf)
![image](https://github.com/user-attachments/assets/be04b5f9-3584-462f-b1ff-eb78344c7a28)



## Result:
Thus the implementation of Hierarchical Clustering using single and complete linkage method in python programming and verified successfully.
