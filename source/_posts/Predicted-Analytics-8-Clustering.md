---
title: 10 Clustering

date: 2023-03-03

tags: [DS, Data Mining]

categories: "Predicted Analytics: Tools & Techniques"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303060126%20(1).png
---

# **Unsupervised Learning**

* Clustering
  * k-means clustering
  * Hierarchical Clustering
* Principal Component Analysis

**Unsupervised Learning in Predictive Analytics**

Unsupervised learning is part of Machine Learning family of methods

Although, it may not be as popular as supervised learning, it has a significant footprint in Analytics

**The Challenge of Unsupervised Learning**

Model assessment

* We cannot tell if the model we have built is good
* Because we do not have the test data with known response variable information
* We cannot do cross validation

# **Clustering**

Categorize objects into groups (or clusters) so that 

* Objects in each group are similar 
* Objects in each group are different from objects in other groups

**Clustering Applications**

* Decrease the size and complexity of problems for other data mining methods
* Identify outliers in a specific domain
  * Customer Segmentation

## Clustering Definition

* Suppose ‘n’ observations
* Let $𝐶1,𝐶2,...,𝐶𝑘$ are sets containing
* the indices of the observations in each other
  * $𝐶1 ∪ 𝐶2 ∪ 𝐶3 ...∪ 𝐶𝑘 = 1,...,𝑛$ . Each observation belongs to at least one of the ‘k’ clusters.
  * $𝐶𝑘 ∩ 𝐶𝑘′ = 0$ for all $𝑘≠𝑘$′. Clusters are non-overlapping: no observation belongs to more than one cluster.

## Compute the Distance between Clusters

![image-20230303111030606](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230303111030606.png)

## Clustering Assessment

A good cluster should have the within-cluster-variation is as small as possible.

* within - cluster - variation = $W(C_K)$
* Good cluster: $minimize(\sum_1^kW(C_k))$$\hat{i}$  
* $W(C_K) = \frac{1}{|C_k|} \sum_{i,\hat{i}}\sum_{j=1}^p(x_{ij}-x_{i^ij})^2$

# **K-Means**

## K-means Algorithm 

* Given a K, find a partition of K cluster
* Each cluster is represented by the center of the cluster and the algorithm converges to stable centers of clusters.
* the K-means algorithm is carried out in three steps:
  ![image-20230303095557785](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230303095557785.png)

## Example 

![image-20230303095421868](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230303095421868.png)

![image-20230303095038636](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230303095038636.png)

![image-20230303095058835](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230303095058835.png)

![image-20230303095357240](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230303095357240.png)

![image-20230303095344768](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230303095344768.png)

![image-20230303095333733](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230303095333733.png)

![image-20230303095510057](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230303095510057.png)

**Difference between kNN Classifier (k Nearest Neighbor) & k-Means Clustering**

![image-20230303092358992](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230303092358992.png)

## Example Code

### Load the Libraries

```python
import numpy as np
from sklearn import datasets
from sklearn.cluster import KMeans

import matplotlib.pyplot as plt
from matplotlib import style
style.use("ggplot") # grammar of graphic
```

### Read Data and Show the Scatterplot

```python
X = np.array([[1, 1],
            [2, 1],
            [4, 5],
            [5, 4]])

print(X)
plt.scatter(X[:,0], X[:,1], s=10, linewidth=5)
plt.show()
```

**Output:**

```
[[1 1]
 [2 1]
 [4 5]
 [5 4]]
```

![download](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/download.png)

### Build Clusters

```python
clf = KMeans(n_clusters=2)
clf.fit(X)

centroids = clf.cluster_centers_
labels = clf.labels_
print(centroids)
print("labels=", labels)
```

**Output:**

```
[[1.5 1. ]
 [4.5 4.5]]
labels= [0 0 1 1]
```

### Plot the Clusters

```python
colors = ["g.","r.","c.","b.","k.","g."]

for i in range(len(X)):
    plt.plot(X[i][0], X[i][1], colors[labels[i]], markersize = 10)
    
plt.scatter(centroids[:,0], centroids[:,1], marker='x', s=150, linewidth=5)
plt.show()
```

![download (1)](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/download%20(1).png)

## Parameter: `nstart`

Clustering algorithm will give slightly different results if we start with different initial values

The `kmeans` algorithm implemented in R has a parameter `nstart` which indicates multiple random initial assignments

Suppose `nstart` = n

* Algorithm builds ‘n’ clusters and only the best cluster is reported
* Best cluster is the one which has minimum within-
  cluster-variation

**Disadvantage of K-means clustering** 

* You have specify the number of clusters

# Hierarchical Clustering

Hierarchical clustering solves this problem – no specification of number of clusters

Hierarchical structure also creates a hierarchical structure of data called **Dendrogram**

## Strategy to build Hierarchical Clustering
Bottom-up approach

* Agglomerative clustering

Compute the Euclidean distance between data points

* Shortest distance observations should be in a 
  single cluster
* Next we compute the distance between cluster 
  that we have created and the next point closets to 
  it
* Include that point in that cluster

## Hierarchical Clustering Algorithm
![image-20230303111410608](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230303111410608.png)

## Example code

[Mall_Customers.csv](https://uciunex.instructure.com/courses/16600/files/2324830?wrap=1)

### Load the Libraries

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
```

### Read Data

```python
'''
Since we are performing clustering
we only need X variable

Clustering is a unsupervised method, 
that's why we do NOT need the response variable or the 'y' variable
'''
dataset = pd.read_csv("Mall_Customers.csv")
X = dataset.iloc[:,[3,4]].values
```

### Plot the Dendrogram

```python
'''
Plot the dendrogram
The plot will determine how many clusters we should need
'''
import scipy.cluster.hierarchy as sch

dendrogram = sch.dendrogram(sch.linkage(X,method='ward'))
plt.title('Dendrogram')
plt.xlabel('Customers')
plt.ylabel('Eucledian Distance')

plt.show()
```

![download3](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/download3.png)

```python
'''
We can have 3 clusters as standard
Or we can have 5 clusters
Find the longest line which is not crossed by horizontal line

This shows total number of clusters = 5
'''
 
from sklearn.cluster import AgglomerativeClustering
hc = AgglomerativeClustering(n_clusters=5, affinity='euclidean',linkage='average')

y_hc = hc.fit_predict(X)
```

```python
plt.scatter(X[y_hc==0,0],X[y_hc==0,1],s=50,c='red',label='Cluster1')
plt.scatter(X[y_hc==1,0],X[y_hc==1,1],s=50,c='blue',label='Cluster2')
plt.scatter(X[y_hc==2,0],X[y_hc==2,1],s=50,c='green',label='Cluster3')
plt.scatter(X[y_hc==3,0],X[y_hc==3,1],s=50,c='cyan',label='Cluster4')
plt.scatter(X[y_hc==4,0],X[y_hc==4,1],s=50,c='magenta',label='Cluster5')

plt.title('Cluster of the Customers')
plt.xlabel('Annual Income (K$)')
plt.ylabel('Spending Score (1-100)')
plt.legend()
```

![download4](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/download4.png)
