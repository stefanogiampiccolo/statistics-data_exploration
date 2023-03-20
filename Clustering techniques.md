**Def**: **Cluster analysis** or **clustering** is the task of grouping a set of objects in such a way that objects in the same group (called a **cluster**) are more similar (in some sense) to each other than to those in other groups (clusters).

The term refers to the problem, not to the technique used. It's important to notice that *cluster concept can't be exactly defined* and that's the *reason* why there are *so many algorithms* to solve this problem (giving different interpretation to the meaning of cluster)

# Cluster models

## Connectivity models - hierarchical clustering 
The main idea is that objects being more related to nearby objects than to objects farther away. The algorithms *form clusters connecting object based on their distance*.

At different distances, different couples will be connected, that can then be represented using a *dendogram*:  the goal is providing an extensive hierarchy of clusters that merge with each other at certain distances.

![[Pasted image 20230319155141.png | 500]]

The "hyper-parameters" of these algoithms are usually:
1. the **distance function** to be used
2. the **linkage criterion**, that tells how to compute distances between different groups.

Since one have to calculate all the distances between the full set of samples and this *becomes impractical for relatively big datasets*. 

### Cophanetic distance and correlation
**Def (COPHANETIC DISTANCE)**: The cophenetic distance between two objects is the height of the dendorgram where the two branches that include the two objects merge into a single branch.

**Def (COPHANETIC CORRELATION)**: measure of how faithfully a dendrogram preserves the pairwise distances between the original unmodeled data points. It's the correlation between empirical cophanetic distance and Euclidean distance.

## Centroid-based clustering 
Each cluster is **represented by a central vector (centroid)**, which is not necessarily a member of the data set. 

Given the number of clusters ($k$), the problem is an optimization problem: find the $k$ cluster centers and assign the objects to the nearest cluster center, such that the squared distances from the cluster are minimized.

### How to choose the exact number of clusters?
Since there is no definition of cluster, there is no easy answer to this question. You can:
1. rely on *domain knowledge*
2. analyze the plot of SSE (sum of squares) against the number of clusters. It's a decreasing function, and the traditional rule suggests to choose the flex point as the right number of clusters.

![[Pasted image 20230319160342.png | 500]]
